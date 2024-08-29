# Atividade: Cap. 09

### 1 - Quais são os principais elementos de um criptossistema de chave pública?

>
> * **Chave pública (e, N):** Usada para encriptação e é conhecida por todos.
> * **Chave privada (d):** Mantida em segredo pelo destinatário e usada para decriptação.
> * **Algoritmo de encriptação:** Permite que um remetente encripte uma mensagem usando a chave pública do destinatário.
> * **Algoritmo de decriptação:** Permite que o destinatário recupere a mensagem original usando sua chave privada.
> * **Algoritmo de geração de chave:** Produz um par de chaves, pública e privada.

### 2 - Quais são os papéis da chave pública e da privada? Descreva-os com detalhes e com exemplos.

>
> * **Chave Pública (e, N):** Utilizada para encriptar mensagens. Por exemplo, Alice usa a chave pública de Bob para encriptar uma mensagem. A segurança reside no fato de que, mesmo que a chave pública seja conhecida, sem a chave privada (d), é computacionalmente impraticável decriptar a mensagem.
> * **Chave Privada (d):** Utilizada para decriptar mensagens. Apenas Bob, que possui a chave privada, pode decriptar a mensagem enviada por Alice.
> * **Exemplo:** Utilizando RSA, se e = 7 e N = 33, Alice encripta uma mensagem M calculando C = M^e mod N. Bob decripta calculando M = C^d mod N.

### 3 - Quais requisitos os criptossistemas de chave pública precisam cumprir para serem considerados como um algoritmo seguro?

>
> * **Facilidade de chave pública:** Deve ser fácil computar chaves públicas e privadas.
> * **Dificuldade de decriptação sem chave privada:** Impraticável calcular a chave privada com base na chave pública.
> * **Algoritmo de encriptação e decriptação:** Deve ser eficiente tanto em termos de encriptação quanto de decriptação.

### 4 - Descreva, em termos gerais, um procedimento eficiente para se escolher um número primo.

>
>  **Método Geral:** * Escolha um número aleatório grande.
>
> * Use um teste de primalidade, como o Teste de Miller-Rabin.
> * Repita o teste até que o número seja considerado primo com alta probabilidade.

### 5 -

#### a - Descreva o uso desse conjunto de tabelas para realizar a encriptação e decriptação entre dois usuários.

> O objetivo é mostrar a possibilidade teórica de criptografia de chave pública usando funções permutacionais representadas por tabelas. A construção das tabelas permite o mapeamento bidirecional necessário para encriptação e decriptação.

#### b - Demonstre que esse é um esquema seguro

> A segurança do esquema baseia-se na premissa de que sem o conhecimento das tabelas completas M1M1**M**1, M2M2**M**2, e M3M3**M**3, um invasor não pode reverter facilmente o processo de encriptação para obter o texto claro. A combinação aleatória e a permutação das entradas em M1M1**M**1, M2M2**M**2, e M3M3**M**3 garantem que o mapeamento inverso não seja trivial.

### 6 - Realize a encriptação e decriptação usando o algoritmo RSA, como na Figura 9.5, para o seguinte:

#### a - p = 3; q = 11, e = 7; M = 5;

```
# (a) p = 3; q = 11, e = 7; M = 5
p, q, e, M = 3, 11, 7, 5
N = p * q
phi_N = (p - 1) * (q - 1)
d = xgcd(e, phi_N)[1] % phi_N
C = Mod(M, N)^e
M_decrypted = Mod(C, N)^d
C, M_decrypted
```

Resultado: (14, 5)

#### b - p = 5; q = 11, e = 3; M = 9;

```
# (b) p = 5; q = 11, e = 3; M = 9
p, q, e, M = 5, 11, 3, 9
N = p * q
phi_N = (p - 1) * (q - 1)
d = xgcd(e, phi_N)[1] % phi_N
C = Mod(M, N)^e
M_decrypted = Mod(C, N)^d
C, M_decrypted
```

Resultado:(14, 9)

#### c - p = 7; q = 11, e = 17; M = 8;

```
# (c) p = 7; q = 11, e = 17; M = 8
p, q, e, M = 7, 11, 17, 8
N = p * q
phi_N = (p - 1) * (q - 1)
d = xgcd(e, phi_N)[1] % phi_N
C = Mod(M, N)^e
M_decrypted = Mod(C, N)^d
C, M_decrypted
```

Resultado: (57, 8)

#### d - p = 11; q = 13, e = 11; M = 7;

```
# (d) p = 11; q = 13, e = 11; M = 7
p, q, e, M = 11, 13, 11, 7
N = p * q
phi_N = (p - 1) * (q - 1)
d = xgcd(e, phi_N)[1] % phi_N
C = Mod(M, N)^e
M_decrypted = Mod(C, N)^d
C, M_decrypted
```

Resultado: (106, 7)

#### e - p = 17; q = 31, e = 7; M = 2.

```
# (e) p = 17; q = 31, e = 7; M = 2
p, q, e, M = 17, 31, 7, 2
N = p * q
phi_N = (p - 1) * (q - 1)
d = xgcd(e, phi_N)[1] % phi_N
C = Mod(M, N)^e
M_decrypted = Mod(C, N)^d
C, M_decrypted
```

Resultado: (128, 2)

### 7 - Em um sistema de chave pública usando RSA, você intercepta o texto cifrado C = 10 enviado a um usuário cuja chave pública é e = 5, n = 35. Qual é o texto claro M?

```
e, n, C = 5, 35, 10
p, q = 5, 7  # Fatores de n
phi_n = (p - 1) * (q - 1)
d = xgcd(e, phi_n)[1] % phi_n
M = Mod(C, n)^d
M
```

Resultado: 5
