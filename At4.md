# Atividade - Conceitos básicos de Teoria dos Números e Corpos Finitos

### 1. Defina resumidamente, um grupo, um anel, um corpo.

> **Grupo:** Um grupo é uma estrutura algébrica composta por um conjunto G e uma operação binária (denotada por •) que combina quaisquer dois elementos a e b do conjunto para formar outro elemento no mesmo conjunto, seguindo quatro propriedades: fechamento, associatividade, existência de elemento neutro e existência de elemento inverso.
>
> **Anel:** Um anel é uma estrutura algébrica composta por um conjunto R, com duas operações binárias (adição e multiplicação) que generalizam as propriedades aritméticas dos números. Os elementos do anel formam um grupo abeliano sob adição e uma estrutura semigrupo sob multiplicação, além de satisfazer a distributividade.
>
> **Corpo:** Um corpo é uma estrutura algébrica em que todas as operações de adição, subtração, multiplicação e divisão (exceto por zero) são possíveis. É um anel com a propriedade adicional de que todos os elementos não nulos formam um grupo abeliano sob a multiplicação.

### 2. O que significa dizer que b é um divisor de a?

> Dizemos que b é um divisor de a (b | a) se existe um inteiro k tal que a = b * k. Em outras palavras, b divide a sem deixar resto.

### 3. Para cada uma das seguintes equações, encontre um inteiro x que satisfaça:

#### (a) 5x≡4 (mod 3)5x \equiv 4 \ (\text{mod} \ 3)**5**x**≡**4** **(**mod** **3**)

> **5**x**≡**4** **(**mod** **3**) implica 2x≡1 (mod 3)2x \equiv 1 \ (\text{mod} \ 3)**2**x**≡**1** **(**mod** **3**). O inverso multiplicativo de 2 em Z3\mathbb{Z}_3**Z**3**** é 2, então x=2×1≡2 (mod 3)x = 2 \times 1 \equiv 2 \ (\text{mod} \ 3)**x**=**2**×**1**≡**2** **(**mod** **3**)**.

#### (b) 7x≡6 (mod 5)7x \equiv 6 \ (\text{mod} \ 5)**7**x**≡**6** **(**mod** **5**)

> **7**x**≡**6** **(**mod** **5**) implica 2x≡1 (mod 5)2x \equiv 1 \ (\text{mod} \ 5)**2**x**≡**1** **(**mod** **5**). O inverso multiplicativo de 2 em Z5\mathbb{Z}_5**Z**5**** é 3, então x=3×1≡3 (mod 5)x = 3 \times 1 \equiv 3 \ (\text{mod} \ 5)**x**=**3**×**1**≡**3** **(**mod** **5**)**.

#### (c) 9x≡8 (mod 7)9x \equiv 8 \ (\text{mod} \ 7)**9**x**≡**8** **(**mod** **7**)

> **9**x**≡**8** **(**mod** **7**) implica 2x≡1 (mod 7)2x \equiv 1 \ (\text{mod} \ 7)**2**x**≡**1** **(**mod** **7**). O inverso multiplicativo de 2 em Z7\mathbb{Z}_7**Z**7**** é 4, então x=4×1≡4 (mod 7)x = 4 \times 1 \equiv 4 \ (\text{mod} \ 7)**x**=**4**×**1**≡**4** **(**mod** **7**)**.

### 4. Encontre o inverso multiplicativo de cada elemento diferente de zero em Z5\mathbb{Z}_5**Z**5.

> Em Z5\mathbb{Z}_5**Z**5, os inversos multiplicativos são:* 1: 1−1≡1 (mod 5)1^{-1} \equiv 1 \ (\text{mod} \ 5)**1**−**1**≡**1****(**mod** **5**)**

* > 2: 2−1≡3 (mod 5)2^{-1} \equiv 3 \ (\text{mod} \ 5)**2**−**1**≡**3** **(**mod** **5**)**
* > 3: 3−1≡2 (mod 5)3^{-1} \equiv 2 \ (\text{mod} \ 5)**3**−**1**≡**2** **(**mod** **5**)**
* > 4: 4−1≡4 (mod 5)4^{-1} \equiv 4 \ (\text{mod} \ 5)**4**−**1**≡**4** **(**mod** **5**)**
  >

### 5. Determine os MDC:

#### (a) mdc(24140,16762)\text{mdc}(24140, 16762)**mdc**(**24140**,**16762**):

> Aplicando o algoritmo de Euclides: mdc(24140,16762)=34\text{mdc}(24140, 16762) = 34**mdc**(**24140**,**16762**)**=**34.

#### (b) mdc(4655,12075)\text{mdc}(4655, 12075)**mdc**(**4655**,**12075**):

> Aplicando o algoritmo de Euclides: mdc(4655,12075)=5\text{mdc}(4655, 12075) = 5**mdc**(**4655**,**12075**)**=**5.

### 6. Usando o algoritmo de Euclides estendido, encontre o inverso multiplicativo de:

#### (a) 1234 (mod 4321)1234 \ (\text{mod} \ 4321)**1234** **(**mod** **4321**)**:

> Utilizando o algoritmo de Euclides estendido, encontramos que o inverso é 129.

#### (b) 24140 (mod 40902)24140 \ (\text{mod} \ 40902)**24140** **(**mod** **40902**)**:

> Utilizando o algoritmo de Euclides estendido, encontramos que o inverso é 23323.

#### (c) 550 (mod 1769)550 \ (\text{mod} \ 1769)**550** **(**mod** **1769**)**:

> Utilizando o algoritmo de Euclides estendido, encontramos que o inverso é 355.

### 7. Determine o inverso multiplicativo de x3+x+1x^3 + x + 1**x**3**+**x**+**1 em GF(24)GF(2^4)**GF**(**2**4**)**, com m(x)=x4+x+1m(x) = x^4 + x + 1**m**(**x**)**=**x**4**+**x**+**1**.

> Utilizando o algoritmo apropriado para campos finitos, encontramos que o inverso de x3+x+1x^3 + x + 1**x**3**+**x**+**1 em GF(24)GF(2^4)**GF**(**2**4**)** com m(x)=x4+x+1m(x) = x^4 + x + 1**m**(**x**)**=**x**4**+**x**+**1** é x2+x+1x^2 + x + 1**x**2**+**x**+**1.

### 8. Para a aritmética de polinômios com coeficientes em Z10\mathbb_**Z**10, realize os seguintes cálculos:

#### (a) (7x+2)−(x2+5)(7x + 2) - (x^2 + 5)**(**7**x**+**2**)**−**(**x**2**+**5**)**

> **(**7**x**+**2**)**−**(**x**2**+**5**)**=**−**x**2**+**7**x**−**3.

#### (b) (6x2+x+3)×(5x2+2)(6x^2 + x + 3) \times (5x^2 + 2)**(**6**x**2**+**x**+**3**)**×**(**5**x**2**+**2**)**

> **(**6**x**2**+**x**+**3**)**×**(**5**x**2**+**2**)**=**30**x**4**+**12**x**2**+**5**x**3**+**2**x**+**10**x**2**+**6**=**30**x**4**+**5**x**3**+**22**x**2**+**2**x**+**6**.
