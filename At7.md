# Atividade: Cap. 07


### 1 - Qual é a diferença entre aleatoriedades estatísticas e imprevisibilidade?

> **Aleatoriedade estatística** refere-se à distribuição uniforme e independência dos bits em uma sequência, ou seja, a sequência parece aleatória quando observada em termos de probabilidade e frequência. Já a **imprevisibilidade** está relacionada à incapacidade de prever qualquer bit subsequente na sequência, mesmo conhecendo todos os bits anteriores. Em criptografia, não basta que uma sequência seja estatisticamente aleatória; ela também deve ser imprevisível para garantir segurança.


### 2 - Liste considerações de projeto importantes para uma cifra de fluxo.

As principais considerações de projeto para uma cifra de fluxo incluem:

* **Imprevisibilidade** : A sequência de chave deve ser imprevisível, tornando difícil para um atacante prever os próximos bits da sequência.
* **Alta taxa de bits** : A cifra deve ser capaz de gerar bits a uma taxa alta para ser eficiente em aplicações de transmissão de dados.
* **Auto-sincronização** : A capacidade de se recuperar rapidamente de erros de transmissão, como a perda de bits.
* **Simplicidade e eficiência** : O algoritmo deve ser simples o suficiente para ser implementado em hardware ou software, mantendo-se eficiente em termos de velocidade e uso de recursos.
* **Chave única** : A sequência de chave gerada não deve ser reutilizada para outra mensagem para evitar ataques de reuso de chave.


### 3 - Por que não é desejável reutilizar uma chave de cifra de fluxo?

> Reutilizar uma chave em uma cifra de fluxo pode permitir ataques do tipo **"ataque de texto conhecido"** ou  **"ataque de texto escolhido"** . Se a mesma chave for usada em duas mensagens diferentes, um atacante pode comparar as duas mensagens cifradas e deduzir informações sobre o texto original, comprometendo a segurança das mensagens.


### 4 - Que operações primitivas são usadas no RC4?

O algoritmo RC4 usa duas operações primitivas principais:

* **Troca de elementos (swap)** : Durante a fase de inicialização e geração de fluxo, RC4 troca valores em uma matriz S de permutação.
* **Soma modular (modulo 256)** : RC4 usa a operação de soma modular com base em 256 durante o processo de permutação e geração de chave.


### 5 - Se apanharmos um algoritmo de congruência linear com um componente aditivo de 0:

então, podemos mostrar que, se m é primo, e se determinado valor de a produz o período máximo de m − 1, então a k também produzirá o período máximo, desde que k seja menor que m e que m − 1 não seja divisível por k. Demonstre isso usando X0 = 1 e m = 31, e produzindo as sequências para ak = 3, 3^2, 3^3, 3^4.

Vamos demonstrar a propriedade mencionada para m=31, começando com X0=1.

Para a=3:
X1=(3×1)mod  31=3
X2=(3×3)mod  31=9
X3=(3×9)mod  31=27
X4=(3×27)mod  31=19

Agora, para a2=9:
X1=(9×1)mod  31=9
X2=(9×9)mod  31=19
X3=(9×19)mod  31=16
X4=(9×16)mod  31=18

Continuando o processo para a^3=27 e a^4=81 (reduzido mod 31), e observando as sequências geradas, podemos verificar se a^k também produz um período máximo.

### 6 -

#### (a) Qual é o período máximo que pode ser obtido do seguinte gerador? Xn+1 = (aXn) mod 2^4

> O período máximo que pode ser obtido é 8.

#### (b) Qual deverá ser o valor de a?

> O valor de aa**a** deve ser um número que seja co-primo com 24 e satisfaça as condições de maximizar o período.

#### (c) Que restrições são exigidas na semente?

> A semente X0deve ser co-prima com 24 e diferente de zero para garantir a geração de todas as iterações possíveis antes de repetir.


### 7 - Que valor de chave RC4 deixará S inalterado durante a inicialização? Ou seja, após a permutação inicial de S, as entradas de S serão quais aos valores de 0 a 255 na ordem crescente.

> Um valor de chave que consiste em uma sequência incremental de números de 0 a 255 (ou seja, 0,1,2,...,255) deixará S inalterado, já que a permutação inicial simplesmente repetiria os valores originais.

### 8 - O algoritmo Blum Blum Shub é baseado na teoria dos resíduos quadráticos e utiliza três números inteiros para realizar os cálculos: p, q e s.

#### (a) Escolha dois números primos grandes p e q, onde p e q sejam congruentes a 3 mod 4 e não tenham fatores primos comuns. Por exemplo, você pode escolher p = 499 e q = 503.

* p=499 e q=503.
* Ambos p e q são congruentes a 3 mod 4 porque 499mod  4=3 e 503mod  4=3. Além disso, p e q são primos e não têm fatores primos comuns.

#### (b) Calcule n = p ∗ q. Neste caso, n seria igual a 499 ∗ 503 = 250997.

* n=499×503=250997.

#### (c) Escolha um número inteiro s entre 1 e n − 1 que seja co-primo com n. Por exemplo, você pode escolher s = 17.

* s=17.

* O número s=17* é co-primo com n=250997 porque o máximo divisor comum entre 17e 250997 é 1.

#### (d) Calcule o valor inicial x0 = (s2) mod n. Neste caso, x0 seria igual a (172) mod 250997 = 289.

* x0=(17^2) mod250997=289.

#### (e) Agora, vamos gerar uma sequência de números aleatórios usando o algoritmo Blum Blum Shub. Para gerar cada número da sequência, use a seguinte fórmula: xi = (x^2i−1) mod n.

#### (f) Execute a fórmula várias vezes para gerar uma sequência de números aleatórios. Por exemplo, você pode executar a fórmula 10 vezes para obter 10 números aleatórios. Aqui está a sequência de números aleatórios gerados usando o algoritmo Blum Blum Shub com os valores do exemplo: 289, 253306, 14107, 23546, 67740, 144593, 79829, 46219, 132936, 9863. Qual foi a sua sequência?

> A sequência de 10 números aleatórios gerados com os valores p=499, q=503, n=250997, s=17 e x0=289 é:
>
> 83521,48817,133971,186362,89157,146656,49406,7011,209706,175057
