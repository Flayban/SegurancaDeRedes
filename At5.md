# Atividade: AES

### 1 - Qual foi o conjunto original de critérios usados pelo NIST para avaliar as cifras AES candidatas?

> Segurança: A cifra deveria resistir a ataques conhecidos e ser resistente a futuros ataques.
> Eficiência: A cifra deveria ser eficiente tanto em hardware quanto em software.
> Facilidade de Implementação: A cifra deveria ser fácil de implementar, com recursos limitados.
> Chave e Tamanho do Bloco: A cifra deveria operar com um tamanho de bloco de 128 bits e suportar chaves de 128, 192 e 256 bits.
> Resistência a Ataques: A cifra deveria resistir a ataques como ataques de força bruta, ataques diferenciais e lineares.

### 2 - Qual foi o conjunto final de critérios usados pelo NIST para avaliar as cifras AES candidatas?

> Segurança em Nível Prático e Teórico: A cifra deve ter segurança que é considerada robusta contra ataques conhecidos.
> Eficiência Computacional: Deve ser eficiente em uma ampla gama de plataformas e arquiteturas.
> Flexibilidade: Deve ser capaz de operar com tamanhos de chave variados (128, 192 e 256 bits) e com um tamanho de bloco de 128 bits.
> Facilidade de Implementação: Deve ser simples e direta para implementar.
> Resistência a Ataques Específicos: Deve resistir a uma série de ataques específicos, como ataques de texto escolhido e ataques de texto adaptado.

### 3 - Qual é a diferença entre Rijndael e AES?

> Rijndael é o algoritmo de cifra simétrica proposto por Vincent Rijmen e Joan Daemen que foi selecionado como o AES. AES (Advanced Encryption Standard) é a versão final padronizada do Rijndael pelo NIST. A principal diferença é que o Rijndael é um algoritmo mais geral que pode trabalhar com tamanhos de bloco e chaves variáveis (tamanhos de bloco de 128 bits, 192 bits, 256 bits e tamanhos de chave correspondentes). No entanto, o AES foi especificamente padronizado para usar um bloco de 128 bits e três tamanhos de chave fixos (128, 192 e 256 bits).

### 4 - Responda:

#### a - Qual é a finalidade do array Estado?

> O array Estado é o bloco de dados sobre o qual o AES opera. Ele armazena os dados que são criptografados ou descriptografados e é atualizado a cada estágio do processo de cifra.

#### b - Como é construída a S-box?

> A S-box (Substitution box) é construída usando uma combinação de operações de substituição e permutação. Primeiro, um valor byte é invertido (transformado em seu inverso multiplicativo no campo de Galois) e, em seguida, é substituído por um valor determinado por uma tabela fixa, o que fornece a segurança adicional necessária para resistir a ataques diferenciais.

#### c -Descreva rapidamente o estágio SubBytes, ShiftRows, MixColumns, AddRoundKey, e o algoritmo de expansão de chave.

> SubBytes: Cada byte do array Estado é substituído por um byte de acordo com a S-box.
> ShiftRows: As linhas do array Estado são deslocadas ciclicamente. A primeira linha não é alterada, a segunda linha é deslocada por um byte à esquerda, a terceira linha por dois bytes e a quarta linha por três bytes.
> MixColumns: Cada coluna do array Estado é misturada para proporcionar difusão, transformando a coluna em uma nova coluna.
> AddRoundKey: Cada byte do array Estado é combinado com uma subchave da expansão da chave por uma operação XOR.
> Algoritmo de Expansão de Chave: A chave original é expandida em uma série de subchaves para cada rodada do AES usando uma combinação de substituição e permutação.

### 5 - Quantos bytes em Estado são afetados por ShiftRows?

O estágio ShiftRows afeta todos os bytes no array Estado. Cada linha do array Estado é deslocada ciclicamente, o que modifica a posição dos bytes em cada linha, impactando todos os 16 bytes do bloco de dados.

### 6 - Use a chave 1010 0111 0011 1011 para encriptar o texto claro "ok"conforme expresso em ASCII, ou seja, 0110 1111 0110 1011. Os projetistas do S-AES obtiveram o texto cifrado 0000 0111 0011 1000. E você?

```
key = [1,0,1,0,0,1,1,1,0,0,1,1,1,0,1,1]
plaintext = [0,1,1,0,1,1,1,1,0,1,1,0,1,0,1,1]
SAES_Encrypt(plaintext, key)

output:
[0, 0, 1, 0, 0, 0, 1, 0, 0, 1, 1, 0, 1, 0, 0, 0]
```

> Ou seja, o texto cifrado encontrado utilizando S-AES foi 0010 0010 0110 1000.

### 7 - Compare AES com DES. Para cada um dos seguintes elementos do DES, indique o elemento comparável no AES ou explique por que ele não é necessário no AES.


#### a - XOR do material da subchave com a entrada da função f.

> * **DES:** Em cada uma das 16 rodadas do DES, a subchave gerada para aquela rodada é XORada com a saída expandida da metade direita do bloco (32 bits expandidos para 48 bits) antes de passar pelas S-boxes.
> * **AES:** No AES, a operação similar é chamada de "AddRoundKey". Durante cada rodada, a subchave gerada para aquela rodada é XORada com o estado inteiro (128 bits) do bloco.

#### b - XOR da saída da função f com a metade esquerda do bloco.

> * **DES:** Essa operação mistura as duas metades do bloco, propagando a influência da metade direita e da subchave para a metade esquerda, contribuindo para a confusão e difusão.
> * **AES:** No AES, não há divisão do bloco em metades. Em vez disso, a operação de "AddRoundKey" (XOR da subchave com o estado) é aplicada ao estado inteiro. Tem o mesmo objetivo de mistura e propagação da influência da chave é alcançado sem a necessidade de divisão do bloco.

#### c - função f.

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

#### d - permutação P.

> * **DES:** A permutação P é aplicada aos 32 bits de saída das S-boxes na função f. Tem a função de reorganiza os bits para espalhar a influência de cada bit sobre o texto cifrado, aumentando a difusão.
> * **AES:** AES realiza permutações implícitas através de "ShiftRows" (que permuta bytes entre as linhas da matriz de estado) e "MixColumns" (que mistura bytes dentro das colunas). As operações combinadas de ShiftRows e MixColumns proporcionam difusão semelhante à permutação P, mas operam a nível de byte e coluna para maior complexidade.

#### e - troca de metades do bloco.

> * **DES:** Após cada rodada, as metades esquerda e direita do bloco são trocadas. Essa troca garante que a influência das operações de uma rodada se propague para a outra metade do bloco na rodada seguinte, contribuindo para a difusão.
> * **AES:** AES não realiza troca de metades. Em vez disso, a estrutura de AES trata o bloco como uma matriz de 4x4 bytes e aplica transformações diretamente a esta matriz em cada rodada. A ausência de troca de metades no AES é compensada pelas transformações combinadas que operam no bloco inteiro, resultando em difusão e confusão eficientes sem a necessidade de trocas explícitas.



### 8 - Calcule a saída da transformação MixColumns para a seguinte sequência de bytes de entrada "67 89 AB CD". Aplique a transformação InvMixColumns ao resultado obtido para verificar seus cálculos. Altere o primeiro byte da entrada de "67"para "77", realize a transformação MixColumns novamente para a nova entrada e determine quantos bits mudaram na saída.

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

### 9 - (2 pontos-extra) Crie um software que possa encriptar e decriptar usando S-AES. Dados de teste: um texto claro binário de 0110 1111 0110 1011 encriptado com uma chave binária de 1010 0111 0011 1011 deverá dar o texto cifrado binário 0000 0111 0011 1000. A decriptação deverá funcionar da mesma forma.
