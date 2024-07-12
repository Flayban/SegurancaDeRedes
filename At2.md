# **Atividade - Técnicas clássicas de encriptação**

### **1. Responda (de forma objetiva) as questões a seguir:**

#### **(a) Quais são os elementos essenciais de uma cifra simétrica?**

>  Algoritmo de criptografia: Define como a mensagem original é transformada em texto cifrado.
>
> * Chave: Sequência de bits usada pelo algoritmo para criptografar e descriptografar.
> * Texto claro: Mensagem original a ser criptografada.
> * Texto cifrado: Mensagem resultante da criptografia do texto claro.

#### **(b) Quais são as duas funções básicas usadas nos algoritmos de encriptação?**

> Criptografia: Transformação do texto claro em texto cifrado.
>
> Descriptografia: Transformação do texto cifrado em texto claro.

#### **(c) Qual é a diferença entre uma cifra de bloco e uma cifra de fluxo?**

> Cifra de bloco: Opera em blocos fixos de texto claro, independentemente do conteúdo.
>
> Cifra de fluxo: Opera em um fluxo contínuo de bits, adaptando-se ao conteúdo.

#### **(d) Quais são as duas técnicas gerais para atacar uma cifra?**

> Análise criptoanalítica: Explorar vulnerabilidades matemáticas do algoritmo para obter a chave.
>
> Ataque de força bruta: Tentar todas as chaves possíveis até encontrar a correta.

#### **(e) Quais são os dois problemas com o one-time pad?**

> Distribuição da chave: Dificuldade em distribuir chaves únicas e seguras para todos os participantes.
>
> Armazenamento da chave: Necessidade de armazenar cópias seguras da chave para futuros usos.

#### **(f) O que é uma cifra de transposição?**

> Técnica que reorganiza a ordem das letras em um texto, sem alterar os caracteres em si. Exemplo: "OLÁ MUNDO" se torna "OULM DANO".

#### **(g) O que é esteganografia?**

> Arte de esconder mensagens secretas dentro de outras mídias, como imagens ou áudio, sem que a mensagem oculta seja perceptível.

### 2. Uma generalização da cifra de César, conhecida como cifra de César afim, tem a seguinte forma: a cada letra de texto claro p, substitua-a pela letra de texto cifrado C :

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXeQH_tuTXS6o6kIAPn6lgNFshYQS7YPqs_1mboZs3GqxNOP0CothkZNqS8PX5KrIa6FkfOYLrRShmxDDRu0TI07O5Df-dSQpB4HShJ6FUqqgdowtguZ6ImMUMXFcH39sUOeC64UUx7AD-MENxRqu92v7MU?key=riDdooNDxjxI4PbQoi4mLw)

### Um requisito básico de qualquer algoritmo de encriptação é que ele seja um para um. Ou seja, se p ̸= q, então E(k, p) ̸= E(k, q). Caso contrário, a decriptação é impossível, pois mais de um caractere de texto claro é mapeado no mesmo caractere de texto cifrado. A cifra de César afim não é um-para-um para todos os valores de a. Por exemplo, para a = 2 e b = 3, então E([a, b], 0) = E([a, b], 13) = 3.

#### **(a) Existem limitações sobre o valor de b? Explique por que sim ou por que não.**

> Não há limitações para o valor de 'b'. Pois, independentemente do valor de 'b', o resultado da soma ap + b será sempre mapeado para um valor dentro do alfabeto de 26 letras, garantindo que cada caractere de texto claro tenha um correspondente único de texto cifrado.
>
> Exemplo: Se 'b' for 100, 'ap + b' será sempre reduzido mod 26, o que garante que o resultado esteja entre 0 e 25.

#### **(b) Determine quais valores de a não são permitidos.**

> Os valores não permitidos de 'a' são aqueles que resultam em um fator multiplicativo nulo na função de criptografia E([a, b], p) = (ap + b) mod 26.
>
> Um fator multiplicativo nulo significa que a é igual a 0. Se a for 0, a função de criptografia se torna E([0, b], p) = b + p mod 26. Nesta situação, a criptografia se resume à adição de 'b' a cada caractere de texto claro, o que não fornece nenhuma segurança real. Qualquer pessoa com acesso ao texto cifrado pode facilmente subtrair 'b' de cada caractere para recuperar o texto original.

#### **(c) Ofereça uma afirmação geral sobre quais valores de a são e não são permitidos. Justifique-a.**

> a={R} - {0}
>
> Como explicado anteriormente, o único valor de 'a' que causa problemas é 0, pois resulta em uma criptografia trivial e insegura. Para qualquer outro valor de 'a' (positivo ou negativo), a função de criptografia opera de forma correta, mapeando cada caractere de texto claro para um único caractere de texto cifrado, preservando a propriedade um-para-um necessária para a decriptação.

### 3.

#### (a) Encripte a mensagem “meet me at the usual place at ten rather than eight o clock” usando a cifra de Hill com a chave [(9 4)(5 7)]. Mostre seus cálculos e o resultado.

```
# Função para encriptar um texto plano usando a cifra de Hill
def hill_encrypt(plain_text, key_matrix):
    modulus = 26  # Número de letras no alfabeto inglês
    plain_text = plain_text.upper().replace(" ", "")  # Converte para maiúsculas e remove espaços
  
    # Adiciona um caractere de preenchimento 'X' se o comprimento do texto não for par
    if len(plain_text) % 2 != 0:
        plain_text += 'X'
  
    # Converte o texto plano em uma lista de números (A=0, B=1, ..., Z=25)
    plain_numbers = [ord(char) - ord('A') for char in plain_text]
    cipher_numbers = []

    # Encripta cada par de números usando a matriz chave
    for i in range(0, len(plain_numbers), 2):
        vector = np.array(plain_numbers[i:i+2])  # Pega um par de números
        cipher_vector = np.dot(key_matrix, vector) % modulus  # Multiplica pela matriz chave e aplica o módulo
        cipher_numbers.extend(cipher_vector)  # Adiciona os números encriptados à lista

    # Converte a lista de números encriptados de volta para letras
    cipher_text = ''.join(chr(num + ord('A')) for num in cipher_numbers)
    return cipher_text

```

Resultado:

> **UKIXUKYDROMEIWSZXWIOKUNUKHXHROAJROANQYEBTLKJEGAD**

#### **(b) Mostre os cálculos para a decriptação correspondente do texto cifrado a fim de recuperar o texto claro original.**

```
# Função para desencriptar um texto cifrado usando a cifra de Hill
def hill_decrypt(cipher_text, key_matrix):
    modulus = 26  # Número de letras no alfabeto inglês
    cipher_text = cipher_text.upper().replace(" ", "")  # Converte para maiúsculas e remove espaços
  
    # Converte o texto cifrado em uma lista de números (A=0, B=1, ..., Z=25)
    cipher_numbers = [ord(char) - ord('A') for char in cipher_text]
    plain_numbers = []

    # Calcula a inversa da matriz chave
    inverse_key_matrix = mod_inverse(key_matrix, modulus)

    # Desencripta cada par de números usando a inversa da matriz chave
    for i in range(0, len(cipher_numbers), 2):
        vector = np.array(cipher_numbers[i:i+2])  # Pega um par de números
        plain_vector = np.dot(inverse_key_matrix, vector) % modulus  # Multiplica pela inversa da matriz chave e aplica o módulo
        plain_numbers.extend(plain_vector)  # Adiciona os números desencriptados à lista

    # Converte a lista de números desencriptados de volta para letras
    plain_text = ''.join(chr(num + ord('A')) for num in plain_numbers)
    return plain_text
```

Resultado:

> **MEETMEATTHEUSUALPLACEATTENRATHERTHANEIGHTOCLOCKX**

### **4. Elabore um programa que possa encriptar e decriptar usando a cifra de César geral, também conhecida como cifra aditiva.**

```
def caesar_encrypt(plain_text, shift, alphabet="abcdefghijklmnopqrstuvwxyz"):
    plain_text = plain_text.lower()  # Converte o texto para minúsculas
    encrypted_text = ""
  
    for char in plain_text:
        if char in alphabet:
            # Encontra a posição da letra no alfabeto
            new_position = (alphabet.index(char) + shift) % len(alphabet)
            encrypted_text += alphabet[new_position]
        else:
            # Preserva os caracteres que não estão no alfabeto (como espaços)
            encrypted_text += char
  
    return encrypted_text

def caesar_decrypt(cipher_text, shift, alphabet="abcdefghijklmnopqrstuvwxyz"):
    cipher_text = cipher_text.lower()  # Converte o texto para minúsculas
    decrypted_text = ""
  
    for char in cipher_text:
        if char in alphabet:
            # Encontra a posição da letra no alfabeto
            new_position = (alphabet.index(char) - shift) % len(alphabet)
            decrypted_text += alphabet[new_position]
        else:
            # Preserva os caracteres que não estão no alfabeto (como espaços)
            decrypted_text += char
  
    return decrypted_text


plain_text = "meet me at the usual place at ten rather than eight o clock"
shift = 3  # Define o valor do deslocamento

encrypted = caesar_encrypt(plain_text, shift)
print("Encrypted:", encrypted)  # Exibe o texto encriptado

decrypted = caesar_decrypt(encrypted, shift)
print("Decrypted:", decrypted)  # Exibe o texto desencriptado

```

Resultado:

### **5. Elabore um programa que possa realizar um ataque de frequência de letra em uma cifra aditiva sem intervenção humana. Seu software deverá produzir textos claros possíveis em ordem aproximada de probabilidade. Seria bom se a sua interface com o usuário permitisse que ele especificasse “mostre os 10 textos claros mais prováveis”.**

```
import string
from collections import Counter

# Frequência de letras em português (em porcentagem)
frequencias_pt = {
    'a': 14.63, 'b': 1.04, 'c': 3.88, 'd': 4.99, 'e': 12.57, 'f': 1.02, 'g': 1.30, 
    'h': 1.28, 'i': 6.18, 'j': 0.40, 'k': 0.02, 'l': 2.78, 'm': 4.74, 'n': 5.05, 
    'o': 10.73, 'p': 2.52, 'q': 1.20, 'r': 6.53, 's': 7.81, 't': 4.34, 'u': 4.63, 
    'v': 1.67, 'w': 0.01, 'x': 0.21, 'y': 0.01, 'z': 0.47
}

def caesar_decrypt(cipher_text, shift, alphabet="abcdefghijklmnopqrstuvwxyz"):
    decrypted_text = ""
  
    for char in cipher_text.lower():
        if char in alphabet:
            new_position = (alphabet.index(char) - shift) % len(alphabet)
            decrypted_text += alphabet[new_position]
        else:
            decrypted_text += char
  
    return decrypted_text

def get_letter_frequencies(text, alphabet="abcdefghijklmnopqrstuvwxyz"):
    counter = Counter([char for char in text.lower() if char in alphabet])
    total_chars = sum(counter.values())
    frequencies = {char: (count / total_chars) * 100 for char, count in counter.items()}
    return frequencies

def score_text(text, alphabet="abcdefghijklmnopqrstuvwxyz"):
    letter_freqs = get_letter_frequencies(text, alphabet)
    score = sum(abs(letter_freqs.get(char, 0) - frequencias_pt.get(char, 0)) for char in alphabet)
    return score

def attack_caesar(cipher_text, top_n=10, alphabet="abcdefghijklmnopqrstuvwxyz"):
    potential_plain_texts = []
    for shift in range(len(alphabet)):
        decrypted_text = caesar_decrypt(cipher_text, shift, alphabet)
        score = score_text(decrypted_text, alphabet)
        potential_plain_texts.append((score, decrypted_text, shift))
  
    potential_plain_texts.sort()
    return potential_plain_texts[:top_n]


cipher_text = "phhw ph dw wkh xvxdo sodfh dw whq udwkhu wkdq hljkw r forfn"  # Texto cifrado
top_n = 10  # Número de textos claros mais prováveis para mostrar

results = attack_caesar(cipher_text, top_n)

print(f"Os {top_n} textos claros mais prováveis são:")
for score, text, shift in results:
    print(f"Deslocamento: {shift}, Score: {score:.2f}, Texto: {text}")

```

Resultado:

### **6. Crie um software que possa encriptar e decriptar usando uma cifra de Hill 2 × 2.**

```
import numpy as np

# Função para calcular a inversa modular de uma matriz
def mod_inverse(matrix, modulus):
    # Calcula o determinante da matriz
    det = int(np.round(np.linalg.det(matrix)))
    # Calcula o inverso do determinante no módulo especificado
    det_inv = pow(det, -1, modulus)
    # Calcula a inversa da matriz multiplicada pelo inverso do determinante
    matrix_inv = det_inv * np.round(det * np.linalg.inv(matrix)).astype(int) % modulus
    return matrix_inv

# Função para encriptar um texto plano usando a cifra de Hill
def hill_encrypt(plain_text, key_matrix):
    modulus = 26  # Número de letras no alfabeto inglês
    plain_text = plain_text.upper().replace(" ", "")  # Converte para maiúsculas e remove espaços
  
    # Adiciona um caractere de preenchimento 'X' se o comprimento do texto não for par
    if len(plain_text) % 2 != 0:
        plain_text += 'X'
  
    # Converte o texto plano em uma lista de números (A=0, B=1, ..., Z=25)
    plain_numbers = [ord(char) - ord('A') for char in plain_text]
    cipher_numbers = []

    # Encripta cada par de números usando a matriz chave
    for i in range(0, len(plain_numbers), 2):
        vector = np.array(plain_numbers[i:i+2])  # Pega um par de números
        cipher_vector = np.dot(key_matrix, vector) % modulus  # Multiplica pela matriz chave e aplica o módulo
        cipher_numbers.extend(cipher_vector)  # Adiciona os números encriptados à lista

    # Converte a lista de números encriptados de volta para letras
    cipher_text = ''.join(chr(num + ord('A')) for num in cipher_numbers)
    return cipher_text

# Função para desencriptar um texto cifrado usando a cifra de Hill
def hill_decrypt(cipher_text, key_matrix):
    modulus = 26  # Número de letras no alfabeto inglês
    cipher_text = cipher_text.upper().replace(" ", "")  # Converte para maiúsculas e remove espaços
  
    # Converte o texto cifrado em uma lista de números (A=0, B=1, ..., Z=25)
    cipher_numbers = [ord(char) - ord('A') for char in cipher_text]
    plain_numbers = []

    # Calcula a inversa da matriz chave
    inverse_key_matrix = mod_inverse(key_matrix, modulus)

    # Desencripta cada par de números usando a inversa da matriz chave
    for i in range(0, len(cipher_numbers), 2):
        vector = np.array(cipher_numbers[i:i+2])  # Pega um par de números
        plain_vector = np.dot(inverse_key_matrix, vector) % modulus  # Multiplica pela inversa da matriz chave e aplica o módulo
        plain_numbers.extend(plain_vector)  # Adiciona os números desencriptados à lista

    # Converte a lista de números desencriptados de volta para letras
    plain_text = ''.join(chr(num + ord('A')) for num in plain_numbers)
    return plain_text


key_matrix = np.array([[9, 4], [5, 7]])  # Define a matriz chave
plain_text = "meet me at the usual place at ten rather than eight o clock"  # Texto plano para encriptar

encrypted = hill_encrypt(plain_text, key_matrix)  # Encripta o texto plano
print("Encrypted:", encrypted)  # Exibe o texto encriptado

decrypted = hill_decrypt(encrypted, key_matrix)  # Desencripta o texto cifrado
print("Decrypted:", decrypted)  # Exibe o texto desencriptado

```
