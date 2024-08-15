# Atividade: Operação de Cifra de Bloco

### 1 - O que é encriptação tripla?

> A **encriptação tripla** (ou Triple DES, 3DES) é uma forma de aprimorar a segurança do algoritmo DES (Data Encryption Standard). Ela envolve a aplicação do algoritmo DES três vezes em cada bloco de dados com diferentes chaves, aumentando a resistência contra ataques. Existem duas principais versões:
>
> * **3DES com três chaves diferentes (DES-EDE3):** Cada passo usa uma chave diferente (K1, K2, K3).
> * **3DES com duas chaves (DES-EDE2):** A primeira e a terceira chaves são iguais (K1, K2, K1).

### 2 - O que é ataque meet-in-the-middle?

> O **ataque meet-in-the-middle** é uma técnica usada contra esquemas de encriptação de várias etapas, como o 3DES. Esse ataque explora o fato de que, se o criptanalista puder calcular uma parte intermediária da cifra a partir do texto claro e outra parte do texto cifrado, ele pode combinar esses resultados para quebrar a cifra com uma quantidade reduzida de operações, em vez de testar todas as combinações de chaves possíveis.

### 3 - Quantas chaves são usadas na encriptação tripla?

> A encriptação tripla pode usar duas ou três chaves:
>
> * No esquema de  **3DES com três chaves diferentes (DES-EDE3)** , são usadas três chaves (K1, K2, K3).
> * No esquema de  **3DES com duas chaves (DES-EDE2)** , são usadas apenas duas chaves (K1, K2).

### 4 - Por que a parte do meio do 3DES é decriptação, em vez de encriptação?

> O processo de **decriptação na parte intermediária** do 3DES (DES-EDE) é uma medida para garantir compatibilidade com o DES original. Dessa forma, ao usar a mesma chave para as três fases do 3DES (encriptação, decriptação e encriptação), o esquema é equivalente ao DES simples. Isso facilita a interoperabilidade entre sistemas que usam DES e 3DES.

### 5 - Por que alguns modos de operação de cifra de bloco só utilizam a encriptação, enquanto outros empregam encriptação e decriptação?

> Modos de operação de cifra de bloco como **Electronic Codebook (ECB)** e **Cipher Block Chaining (CBC)** aplicam encriptação e decriptação dependendo do objetivo e da segurança desejada. Alguns modos, como ECB, apenas encriptam cada bloco de maneira independente. Outros, como CBC, utilizam tanto encriptação quanto decriptação para garantir que a alteração de um bloco afete os subsequentes, aumentando a segurança.

### 6 - Você deseja construir um dispositivo de hardware para realizar encriptação de bloco no modo cipher block chaining (CBC) usando um algoritmo mais forte do que DES. 3DES é um bom candidato. A Figura 1 mostra duas possibilidades, ambas acompanhando a definição do CBC. Qual das duas você escolheria:

#### a - Por segurança?

> A opção **(b) CBC com três loops** seria mais segura. Isso ocorre porque cada estágio da operação é separado, aumentando a complexidade e a resistência contra ataques, como o ataque meet-in-the-middle. Como cada fase usa uma chave distinta (K1, K2, K3), o processo é mais robusto do que realizar as três operações dentro de um único bloco.

#### b - Por desempenho?

> A opção **(a) CBC com um loop** oferece melhor desempenho. Como todas as operações (EDE) são realizadas em um único bloco, o tempo de processamento é reduzido. Isso simplifica a implementação e diminui a quantidade de operações, tornando o dispositivo mais eficiente em termos de velocidade.

### 7 - Crie um software que possa encriptar e decriptar no modo cipher block chaining usando uma das seguintes cifras: módulo affine 256, módulo Hill 256, S-DES, DES. Teste os dados para S-DES usando um vetor de inicialização binário de 1010 1010. Um texto claro binário de 0000 0001 0010 0011 encriptado com uma chave binária de 01111 11101 deverá dar um texto claro binário de 1111 0100 0000 1011. A decriptação deverá funcionar de modo correspondente.
