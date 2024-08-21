# Atividade: Cap. 08

### 1 - Por que mdc(n, n + 1) = 1 é para dois inteiros consecutivos n e n + 1?

> Dois inteiros consecutivos n e n+1 não têm fatores em comum, exceto 1. Isso ocorre porque qualquer divisor comum de n e n+1 também dividiria a diferença entre eles, que é 1. Como o único divisor de 1 é 1, o máximo divisor comum (mdc) de n e n+1 deve ser 1.

### 2 - Usando o teorema de Fermat, encontre 3^201 mod 11.

```
n = 11
a = 3
exp = 201

# Pelo pequeno teorema de Fermat:
result = power_mod(a, exp, n)
result

```

Resultado:  3

### 3 - Use o teorema de Fermat para encontrar um número a entre O e 72, com a congruente a 9794 módulo 73.

```
n = 73
a = 9794

# Encontre o valor de a mod n
result = a % n
result

```

Resultado: 12

### 4 - Use o teorema de Euler para encontrar um número a entre 0 e 9, tal que a seja congruente a 7^1000 módulo 10. (Observe que isso é o mesmo que o último dígito da expansão decimal de 7^1000.)

```
a = 7
exp = 1000
n = 10

# Phi de 10 é 4, então:
phi_n = euler_phi(n)

# Calcular o resultado usando exponenciação modular
result = power_mod(a, exp, n)
result

```

Resultado: 1

### 5 - Use o teorema de Euler para encontrar um número x entre 0 e 28, com x^85 congruente a 6 módulo 35 (Você não precisará usar qualquer pesquisa por força bruta).

```
x = 6
exp = 85
n = 35

# Usando exponenciação modular para calcular x^85 mod 35
result = power_mod(x, exp, n)
result
```

Resultado: 6

### 6 - Observe, na Tabela 8.2, que φ(n) é par para n > 2. Isso é verdadeiro para todo n > 2. Dê um argumento conciso para explicar por que isso acontece.

> Para n>2, n tem pelo menos dois fatores primos. Se n for ímpar, um desses fatores é 2, que contribui para que ϕ(n) seja par. Se n for ímpar, há simetria nos fatores primos, resultando em pares coprimos, o que torna ϕ(n) par.

### 7 - Se n é composto e passa no teste de Miller-Rabin para a base a, então n é chamado de pseudo-primo forte à base a. Mostre que 2047 é um pseudoprimo à base 2.

```
n = 2047
a = 2

# Teste de Miller-Rabin
result = is_pseudoprime(n, a)
result

```

Resultado:  `"inconclusive"`, o teste não foi conclusivo e não há evidência direta de que 2047 seja um pseudoprimo para a base 2 com essa implementação.

### 8 -  O exemplo usado por Sun-Tsu para ilustrar o CRT foi: x = 2 (mod 3); x = 3 (mod 5); x = 2 (mod 7) Solucione para x.

```
mods = [3, 5, 7]
residues = [2, 3, 2]

# Resolver o sistema usando o teorema chinês do resto
x = crt(residues, mods)
x

```

Resultado: 23
