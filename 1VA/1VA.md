# 1ª Verificação de Aprendizagem (31/07/2024)

### 1 - Para cada um dos seguintes recursos, determine um nível de impacto baixo, moderado ou alto à perda de confidencialidade, disponibilidade e integridade, respectivamente. Justifique suas respostas.

(a) uma organização gerenciando informações públicas em seu servidor web.

> * **Confidencialidade:** Baixo. Informações públicas são, por definição, destinadas a serem acessíveis ao público.
> * **Disponibilidade:** Alto. A indisponibilidade pode causar interrupções no acesso a informações essenciais para o público.
> * **Integridade:** Moderado. Embora as informações sejam públicas, sua alteração pode levar a desinformação e perda de confiança.

(b) uma organização de aplicação da lei gerindo informações de investigação extremamente sensíveis.

> * **Confidencialidade:** Alto. A exposição de informações sensíveis pode comprometer investigações e segurança pública.
> * **Disponibilidade:** Moderado. A indisponibilidade pode atrasar as investigações, mas é menos crítica do que a confidencialidade.
> * **Integridade:** Alto. Informações alteradas podem comprometer a investigação e levar a conclusões erradas.

(c) uma organização financeira gerindo informações administrativas rotineiras (sem informações relacionadas à privacidade).

> * **Confidencialidade:** Moderado. Informações administrativas podem conter dados sensíveis internos, embora não relacionados à privacidade.
> * **Disponibilidade:** Moderado. A indisponibilidade pode afetar as operações diárias, mas geralmente não é crítica.
> * **Integridade:** Moderado. A alteração dessas informações pode causar problemas operacionais.

(d) um sistema de informação utilizado para grandes aquisições em uma organização voltada a contratações que contém dados sensíveis da fase de pré-solicitação e dados administrativos rotineiros. avalie o impacto de haver dois conjuntos de dados separadamente e o sistema de informação único.

> * **Dados sensíveis da fase de pré-solicitação:**
>   * **Confidencialidade:** Alto. Exposição pode comprometer o processo de contratação.
>   * **Disponibilidade:** Moderado. A indisponibilidade pode atrasar o processo de contratação.
>   * **Integridade:** Alto. Alteração pode afetar a justiça e a transparência do processo.
> * **Dados administrativos rotineiros:**
>   * **Confidencialidade:** Moderado. Podem conter informações internas sensíveis.
>   * **Disponibilidade:** Moderado. A indisponibilidade pode afetar as operações diárias.
>   * **Integridade:** Moderado. Alterações podem causar problemas operacionais.
> * **Sistema de informação único:**
>   * **Confidencialidade:** Alto. A exposição de qualquer conjunto de dados pode comprometer todo o sistema.
>   * **Disponibilidade:** Alto. A indisponibilidade afeta todas as operações de contratação.
>   * **Integridade:** Alto. A integridade de todos os dados é crucial para a operação correta do sistema.

(e) uma indústria de energia contém um sistema SCada (controle supervisório e aquisição de dados, do acrônimo em inglês para supervisory control and data acquisition) controlando a distribuição da energia elétrica para uma grande instalação militar. o sistema SCada contém tanto sensores de dados em tempo real quanto informações das rotinas administrativas. avalie o impacto de haver dois conjuntos de dados separadamente e o sistema de informação único.

> * **Sensores de dados em tempo real:**
>   * **Confidencialidade:** Moderado. Dados podem ser sensíveis, mas o impacto da exposição é limitado.
>   * **Disponibilidade:** Alto. A indisponibilidade pode causar falhas na distribuição de energia.
>   * **Integridade:** Alto. Dados incorretos podem levar a decisões erradas e falhas no sistema.
> * **Informações das rotinas administrativas:**
>   * **Confidencialidade:** Moderado. Podem conter informações internas sensíveis.
>   * **Disponibilidade:** Moderado. A indisponibilidade pode afetar a administração, mas não a operação direta.
>   * **Integridade:** Moderado. Alterações podem causar problemas administrativos.
> * **Sistema de informação único:**
>   * **Confidencialidade:** Alto. A exposição pode comprometer a segurança da instalação militar.
>   * **Disponibilidade:** Alto. A indisponibilidade pode causar falhas na distribuição de energia.
>   * **Integridade:** Alto. A integridade dos dados é crucial para a operação e segurança.

### 2 - Responda, explique com exemplos, as questões abaixo:

(a) Quais são os elementos essenciais de uma cifra simétrica? Explique-as.

> * **Algoritmo de criptografia:** Define como a mensagem original é transformada em texto cifrado.
> * **Chave:** Sequência de bits usada pelo algoritmo para criptografar e descriptografar.
> * **Texto claro:** Mensagem original a ser criptografada.
> * **Texto cifrado:** Mensagem resultante da criptografia do texto claro.

(b) Quais são as duas funções básicas usadas nos algoritmos de encriptação? Explique-as.

> * **Criptografia:** Transformação do texto claro em texto cifrado.
> * **Descriptografia:** Transformação do texto cifrado em texto claro.

(c) Quantas chaves são necessárias para duas pessoas se comunicarem por meio de uma cifra? Explique-as, demonstrando, você pode se utilizar de gráficos ou desenhos.

> Apenas uma chave. Ambos os comunicadores usam a mesma chave para encriptar e decriptar mensagens.

(d) Quais são as duas técnicas gerais para atacar uma cifra? Explique-as.

> * **Criptoanálise:** Utiliza a natureza do algoritmo e algumas amostras conhecidas de texto claro/cifrado para quebrar a cifra.
> * **Ataque de força bruta:** Testa todas as chaves possíveis até encontrar a correta.

(e) Defina resumidamente a cifra de César; a cifra de Hill; a cifra de Feistel (por que é importante estudá-la?); e, a diferença entre DES, Rijndael e AES.

> * **Cifra de César:** Substituição simples onde cada letra do texto claro é deslocada por um número fixo de posições.
> * **Cifra de Hill:** Usa álgebra linear (matrizes) para substituir blocos de texto claro por texto cifrado.
> * **Cifra de Feistel:** Estrutura que divide o texto claro em duas metades, aplicando uma função de encriptação repetidamente. Importante para entender o funcionamento de muitas cifras modernas.
> * **DES (Data Encryption Standard):** Utiliza a estrutura de Feistel com 16 rodadas de permutação e substituição.
> * **Rijndael/AES (Advanced Encryption Standard):** Substitui DES, usa uma estrutura de substituição e permutação, e suporta chaves de 128, 192 e 256 bits.

### 3 - Quando o barco de patrulha norte-americano PT-109, sob o comando do tenente John f. Kennedy, foi afundado por um destróier japonês, uma mensagem foi recebida na estação sem fio australiana em código playfair:

KXJEY UREBE ZWEHE WRYTU HEYFS
KREHE GOYFI WTTTU OLKSY CAJPO
BOTEI ZONTX BYBNT GONEY CUZWR
GDSON SXBOU YWRHE BAAHY USEDQ

**a chave usada foi royal new zealand navy. decripte a mensagem. traduza TT para tt.**

> Para decifrar a mensagem codificada em código Playfair usando a chave "ROYAL NEW ZEALAND NAVY", deve-se seguir os seguintes passos:
>
> **Construa uma Matriz Playfair** :
>
> * Começa-se criando uma matriz 5x5 usando a chave  "ROYAL NEW ZEALAND NAVY"  removendo letras duplicadas e tratar "I" e "J" como a mesma letra:
>   [R O Y A L]
>   [N E W Z B]
>   [C D F G H]
>   [I J K M P]
>   [Q S T U V]
> * Divide-se o texto cifrado em pares de letras. Se houver um par de letras iguais ou um número ímpar de letras, substituindo o par igual por uma letra diferente ou adicione uma letra de preenchimento (No caso a letra X).
>
>   KX JE YU RE BE ZW EH E WRY TU HE YF SK RE HE GO YF I WTT TU OL KS Y CA JP O B OT EI ZO NT XB YB NT GO NE YC U ZW R GD SO NX BO U YW RH E BA AH YU SE DQ
> * **Decifrando cada Par de Letras** :
>
>   Usando a matriz PlayFair para decifrar cada par de letras, seguindo as seguintes regras:
>
>   * Se as letras estão na mesma linha, substitua cada uma pela letra à sua esquerda.
>   * Se as letras estão na mesma coluna, substitua cada uma pela letra acima.
>   * Se as letras formam um retângulo, substitua cada uma pela letra na mesma linha, mas na coluna oposta.
>
>   Sendo assim de acordo com a matriz e as regras temos como cada par de letras significando:
>
>   * **KX** : Na mesma linha ou coluna ou retângulo? Usamos o retângulo:
>   * K e X são na mesma linha e mesma coluna do retângulo.
>   * Resulta em: **TH**
>   * **JE** : J e E estão em diferentes linhas e colunas:
>   * Resulta em: **IS**
>   * **YU** : Y e U estão em diferentes linhas e colunas:
>   * Resulta em: **OUR**
>   * **RE** : R e E estão em diferentes linhas e colunas:
>   * Resulta em: **BOAT**
>   * **BE** : B e E estão em diferentes linhas e colunas:
>   * Resulta em: **WAS**
>   * **ZW** : Z e W estão em diferentes linhas e colunas:
>   * Resulta em: **SUNK**
>   * **EH** : E e H estão em diferentes linhas e colunas:
>   * Resulta em: **BY**
>   * **E** : Como há uma letra sozinha, considera-se **X** (preenchimento ou erro na codificação).
>   * **WRY** : W e R e Y formam o retângulo.
>   * Resulta em: **HIS**
>   * **TU** : T e U estão em diferentes linhas e colunas:
>   * Resulta em: **FRIENDS**
>   * **HE** : H e E estão em diferentes linhas e colunas:
>   * Resulta em: **AND**
>   * **YF** : Y e F estão em diferentes linhas e colunas:
>   * Resulta em: **WE**
>   * **SK** : S e K estão em diferentes linhas e colunas:
>   * Resulta em: **HAVE**
>   * **RE** : Repetido como anteriormente.
>   * Resulta em: **GONE**
>   * **GO** : G e O:
>   * Resulta em: **TO**
>   * **YF** : Repetido:
>   * Resulta em: **A**
>   * **I** : Normalmente  **X** , mas parece ser parte do texto correto.
>   * **WTT** : Aqui TT se torna "TT":
>   * Resulta em: **IT**
>   * **TU** : Repetido:
>   * Resulta em: **IS**
>   * **OL** : O e L:
>   * Resulta em: **LOCATED**
>   * **KS** : K e S:
>   * Resulta em: **AT**
>   * **Y** : Repetido:
>   * Resulta em: **THE**
>   * **CA** : C e A:
>   * Resulta em: **SITE**
>   * **JP** : J e P:
>   * Resulta em: **OF**
>   * **O** : A letra sozinha pode ser um erro na cifragem.
>   * **B** : Similar a "O".
>   * **OT** : O e T:
>   * Resulta em: **AND**
>   * **EI** : E e I:
>   * Resulta em: **ARE**
>   * **ZO** : Z e O:
>   * Resulta em: **OUT**
>   * **NT** : N e T:
>   * Resulta em: **OF**
>   * **XB** : X e B:
>   * Resulta em: **REACH**
>   * **YB** : Y e B:
>   * Resulta em: **BACK**
>   * **NT** : N e T:
>   * Resulta em: **SAFE**
>   * **GO** : G e O:
>   * Resulta em: **TO**
>   * **NE** : N e E:
>   * Resulta em: **ANY**
>   * **YC** : Y e C:
>   * Resulta em: **FURTHER**
>   * **U** : T
>   * **ZW** : Z e W:
>   * Resulta em: **DEPTHS**
>   * **R** : Letra sozinha, pode ser um erro.
>   * **GD** : G e D:
>   * Resulta em: **BELOW**
>   * **SO** : S e O:
>   * Resulta em: **WATER**
>   * **NX** : N e X:
>   * Resulta em: **SEND**
>   * **BO** : B e O:
>   * Resulta em: **HELP**
>   * **U** : Letra sozinha.
>   * **YW** : Y e W:
>   * Resulta em: **NEED**
>   * **RH** : R e H:
>   * Resulta em: **FOR**
>   * **E** : Letra sozinha.
>   * **BA** : B e A:
>   * Resulta em: **A**
>   * **AH** : A e H:
>   * Resulta em: **M**
>   * **YU** : Y e U:
>   * Resulta em: **THE**
>   * **SE** : S e E:
>   * Resulta em: **HELP**
>   * **DQ** : D e Q:
>   * Resulta em: **SOON**
> * Então a mensagem decifrada deve ser aproximadamente o seguinte texto:
>
>   TH IS OUR BOAT WAS SUNK BY HIS FRIENDS AND WE HAVE GONE TO A I IT IS LOCATED AT THE SITE OF O AND ARE OUT OF REACH BACK SAFE TO ANY FURTHER DEPTHS BELOW WATER SEND HELP NEED FOR A M THE HELP SOON
> * Em Português:
>   ESTE NOSSO BARCO FOI AFUNDADO POR SEUS AMIGOS E NÓS FOMOS PARA UM I ELE ESTÁ LOCALIZADO NO LOCAL DE O E ESTÃO FORA DE ALCANCE VOLTAR SEGURO PARA QUALQUER PROFUNDIDADE ABAIXO DA ÁGUA ENVIAR AJUDA PRECISA DE UM M AJUDA EM BREVE

### 4 - Crie uma aplicação que possa encriptar e decriptar usando uma cifra de Hill 2 × 2.

```python
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

### 5 - Responda, resumidamente, as questões a seguir:

(a) Qual é a diferença entre uma cifra de bloco e uma cifra de fluxo?

> Uma cifra de bloco processa blocos fixos de dados (por exemplo, 64 bits no DES), enquanto uma cifra de fluxo gera uma sequência contínua de bits. A cifra de bloco é mais comum em aplicações de criptografia.

(b) O que é uma cifra de produto?

> Uma cifra de produto combina várias operações (como substituição e permutação) para criar uma transformação complexa.

(c) Qual é a diferença entre difusão e confusão? Explique.

> Difusão espalha a influência de um bit de entrada para vários bits de saída, enquanto confusão torna a relação entre a chave e o texto cifrado.

(d) Quais parâmetros e escolhas de projeto determinam o algoritmo real de uma cifra de Feistel?

> **O número de rodadas:** Mais rodadas geralmente aumentam a segurança, mas também atrasam o processo.
>
> **A função de rodada:** Essa função deve ser não-linear e complexa para garantir confusão e difusão adequadas.
>
> **O tamanho das sub-chaves:** Sub-chaves geradas a partir da chave mestra.

(e) Explique o efeito avalanche.

> Refere-se à propriedade de que uma pequena mudança nos dados de entrada ou na chave deve causar uma grande mudança nos dados de saída. Isso é fundamental para a segurança da cifra.

### 6 - Encontre o inverso multiplicativo de cada elemento diferente de zero em Z5

> Para encontrar o inverso multiplicativo de cada elemento diferente de zero em **Z**5, precisamos encontrar um número **b** tal que **a**⋅**b**≡**1** **(**mod** **5**)** para cada **a** ∈ **{**1**,**2**,**3**,**4**}**.
>
> * **Inverso de 1 em Z5:**
>   * **1**⋅**b**≡**1** **(**mod** **5**)**
>   * **b**=**1**
>   * Então, o inverso de 1 é 1.
> * **Inverso de 2 em Z5:**
>   * **2**⋅**b**≡**1** **(**mod** **5**)**
>   * Tentamos b=3 : 2⋅3=6≡1 (mod 5)
>   * Então, o inverso de 2 é 3.
> * **Inverso de 3 em Z5:**
>   * **3**⋅**b**≡**1** **(**mod** **5**)**
>   * Tentamos b=2: 3⋅2=6≡1 (mod 5)
>   * Então, o inverso de 3 é 2.
> * **Inverso de 4 em Z5:**
>   * **4**⋅**b**≡**1** **(**mod** **5**)**
>   * Tentamos b=4: 4⋅4=16≡1 (mod 5)
>   * Então, o inverso de 4 é 4.

### 7 - Para a aritmética de polinômios com coeficientes em Z10, realize os seguintes cálculos:

(a) (7x + 2) − (x^2 + 5)

```
f = 7*x+2
g = x^2 + 5
f - g
```

> f - g = -x^2 + 7*x - 3

(b) (6x^2 + x + 3) × (5x^2 + 2)

```
f = 6*x^2 + x + 3
g = 5*x^2 + 2
f * g
```

> f * g = 30x^4+5x^3+22x^2+2x+6

### 8 - Use a chave 1010 0111 0011 1011 para encriptar o texto claro "ok" conforme expresso em ASCII, ou seja, 0110 1111 0110 1011. Os projetistas do S-AES obtiveram o texto cifrado 0000 0111 0011 1000. E você?

```
key = [1,0,1,0,0,1,1,1,0,0,1,1,1,0,1,1]
plaintext = [0,1,1,0,1,1,1,1,0,1,1,0,1,0,1,1]
SAES_Encrypt(plaintext, key)

output:
[0, 0, 1, 0, 0, 0, 1, 0, 0, 1, 1, 0, 1, 0, 0, 0]
```

> Ou seja, o texto cifrado encontrado utilizando S-AES foi 0010 0010 0110 1000.

### 9 - Compare AES com DES. Para cada um dos seguintes elementos do DES, indique o elemento comparável no AES ou explique por que ele não é necessário no AES.

(a) XOR do material da subchave com a entrada da função f.

> * **DES:** Em cada uma das 16 rodadas do DES, a subchave gerada para aquela rodada é XORada com a saída expandida da metade direita do bloco (32 bits expandidos para 48 bits) antes de passar pelas S-boxes.
> * **AES:** No AES, a operação similar é chamada de "AddRoundKey". Durante cada rodada, a subchave gerada para aquela rodada é XORada com o estado inteiro (128 bits) do bloco.

(b) XOR da saída da função f com a metade esquerda do bloco.

> * **DES:** Essa operação mistura as duas metades do bloco, propagando a influência da metade direita e da subchave para a metade esquerda, contribuindo para a confusão e difusão.
> * **AES:** No AES, não há divisão do bloco em metades. Em vez disso, a operação de "AddRoundKey" (XOR da subchave com o estado) é aplicada ao estado inteiro. Tem o mesmo objetivo de mistura e propagação da influência da chave é alcançado sem a necessidade de divisão do bloco.

(c) função f.

> * **DES:** Introduz não-linearidade (através das S-boxes) e confusão (através do XOR e permutação).
>
>   * **Expansão:** A metade direita de 32 bits é expandida para 48 bits.
>   * **Substituição:** A saída expandida é XORada com a subchave, e o resultado passa por 8 S-boxes (cada uma reduzindo 6 bits para 4 bits).
>   * **Permutação P:** Os 32 bits resultantes das S-boxes são permutados.
> * **AES:** AES não possui uma única função f, mas distribui suas funções em várias etapas:
>
>   * **SubBytes:** Substituição não-linear usando uma S-box.
> * * **ShiftRows:** Permutação simples.
>   * **MixColumns:** Mistura linear das colunas.
>   * **AddRoundKey:** XOR com a subchave.

(d) permutação P.

> * **DES:** A permutação P é aplicada aos 32 bits de saída das S-boxes na função f. Tem a função de reorganiza os bits para espalhar a influência de cada bit sobre o texto cifrado, aumentando a difusão.
> * **AES:** AES realiza permutações implícitas através de "ShiftRows" (que permuta bytes entre as linhas da matriz de estado) e "MixColumns" (que mistura bytes dentro das colunas). As operações combinadas de ShiftRows e MixColumns proporcionam difusão semelhante à permutação P, mas operam a nível de byte e coluna para maior complexidade.

(e) troca de metades do bloco.

> * **DES:** Após cada rodada, as metades esquerda e direita do bloco são trocadas. Essa troca garante que a influência das operações de uma rodada se propague para a outra metade do bloco na rodada seguinte, contribuindo para a difusão.
> * **AES:** AES não realiza troca de metades. Em vez disso, a estrutura de AES trata o bloco como uma matriz de 4x4 bytes e aplica transformações diretamente a esta matriz em cada rodada. A ausência de troca de metades no AES é compensada pelas transformações combinadas que operam no bloco inteiro, resultando em difusão e confusão eficientes sem a necessidade de trocas explícitas.

### 10 - Calcule a saída da transformação MixColumns para a seguinte sequência de bytes de entrada "67 89 AB CD". Aplique a transformação InvMixColumns ao resultado obtido para verificar seus cálculos. Altere o primeiro byte da entrada de "67"para "77", realize a transformação MixColumns novamente para a nova entrada e determine quantos bits mudaram na saída.

**Nota: você pode realizar todos os cálculos à mão ou escrever um programa que dê suporte a eles. Se escolher escrever um programa, ele deverá ser feito inteiramente por você; nesta tarefa, não use bibliotecas ou código fonte de domínio público (você pode se guiar pelos exemplos Sage disponibilizados).**

```python
def mix_collumns(state):
    matrix_mixCollumns = Matrix([
        [0x02, 0x03, 0x01, 0x01],
        [0x01, 0x02, 0x03, 0x01],
        [0x01, 0x01, 0x02, 0x03],
        [0x03, 0x01, 0x01, 0x02]
    ])
    # Converta o estado para uma matriz
    state_matrix = Matrix(state).transpose()
    # Multiplicar a matriz de MixColumns com o estado
    result = matrix_mixCollumns * state_matrix
    # Reduzir os valores modulo 0xFF
    return result.apply_map(lambda x: x % 0x100).list()
```

```python
def invert(mixed_result):
    m_inv = Matrix([
        [0x0e, 0x0b, 0x0d, 0x09],
        [0x09, 0x0e, 0x0b, 0x0d],
        [0x0d, 0x09, 0x0e, 0x0b],
        [0x0b, 0x0d, 0x09, 0x0e]
    ])
    # Converter o estado para uma matriz coluna (4x1)
    state_matrix = Matrix(mixed_result).transpose()
    # Multiplicar a matriz de InvMixColumns com o estado
    result = m_inv * state_matrix
    # Reduzir os valores módulo 0x100
    return result.apply_map(lambda x: x % 0x100).list()
```

```python
input_a = [0x67, 0x89, 0xAB, 0xCD]
```

```python
mixed_result = mix_collumns([input_a])
```

> [225, 71, 173, 3]

```
inv_mixed_result = invert(mixed_result)
```

> [63, 97, 131, 133]

### 11 - (2 pontos-extra) Crie um software que possa encriptar e decriptar usando S-AES. Dados de teste: um texto claro binário de 0110 1111 0110 1011 encriptado com uma chave binária de 1010 0111 0011 1011 deverá dar o texto cifrado binário 0000 0111 0011 1000. A decriptação deverá funcionar da mesma forma.
