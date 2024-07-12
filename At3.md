# **Atividade - Cifras de bloco e o data encryption standard**

### **1. Responda os questionamentos a seguir:**

#### **(a) Por que é importante estudar a cifra de Feistel?**

> O estudo da cifra de Feistel é relevante porque ela é a base para muitos algoritmos de criptografia simétrica, como o DES (Data Encryption Standard). Compreender seus princípios e propriedades é fundamental para projetar e analisar sistemas seguros.

#### **(b) Qual é a diferença entre uma cifra de bloco e uma cifra de fluxo?**

> Uma cifra de bloco processa blocos fixos de dados (por exemplo, 64 bits no DES), enquanto uma cifra de fluxo gera uma sequência contínua de bits. A cifra de bloco é mais comum em aplicações de criptografia.

#### **(c) Por que não é prático usar uma cifra de substituição reversível qualquer do tipo mostrado na Tabela 3.1?**

> Não é prático usar uma cifra de substituição reversível qualquer, pois isso não proporciona confusão e difusão adequadas, tornando o algoritmo vulnerável a ataques.

#### **(d) O que é uma cifra de produto?**

> Uma cifra de produto combina várias operações (como substituição e permutação) para criar uma transformação complexa.

#### **(e) Qual é a diferença entre difusão e confusão?**

> Difusão espalha a influência de um bit de entrada para vários bits de saída, enquanto confusão torna a relação entre a chave e o texto cifrado.

#### **(f) Que parâmetros e escolhas de projeto determinam o algoritmo real de uma cifra de Feistel?**

> O número de rodadas: Mais rodadas geralmente aumentam a segurança, mas também atrasam o processo.
>
> A função de rodada: Essa função deve ser não-linear e complexa para garantir confusão e difusão adequadas.
>
> O tamanho das sub-chaves: Sub-chaves geradas a partir da chave mestra.

#### **(g) Explique o efeito avalanche.**

> Refere-se à propriedade de que uma pequena mudança nos dados de entrada ou na chave deve causar uma grande mudança nos dados de saída. Isso é fundamental para a segurança da cifra.

### 2. Qual(is) dos recursos abaixo estão presentes no projeto da rede de Feistel? Explique.

(a) Tamanho do bloco e da chave;

(b) Função da rodada;

(c) Gerador de sub-chaves;

(d) Todas as alternativas.

> Tamanho do bloco e da chave: Esses parâmetros afetam a segurança e a eficiência da cifra. Blocos maiores podem aumentar a segurança, mas também a complexidade.
>
> Função da rodada: A função de rodada é aplicada repetidamente na cifra de Feistel. Sua escolha impacta a segurança e a velocidade do algoritmo.
>
> Gerador de sub-chaves: Essencial para criar as chaves de rodada. Sub-chaves únicas são geradas a partir da chave mestra.
>
> Todos esses recursos estão presentes no projeto da rede de Feistel, logo, alternativa correta, letra D.

### 3. Qual é o tamanho do texto claro no Data Encryption Standard (DES)? Explique.

(a) 57;

(b) 48;

(c) 32;

(d) 64.

> O tamanho do texto claro no DES é de 64 bits, alternativa correta, letra D. 
>
> Esse tamanho foi escolhido como padrão para garantir uma combinação adequada de segurança e eficiência.
>
> O algoritmo DES também usa uma chave de 64 bits, mas apenas 56 bits são efetivamente utilizados para a criptografia. Os outros 8 bits são usados para verificar a paridade e, em seguida, descartados.

### 4. A cifra de Feistel do algoritmo de encriptação utilizada no Data Encryption Standard (DES) utiliza quantos S-boxes? Explique.

(a) 8;

(b) 7;

(c) 6;

(d) 5.

> O DES utiliza 8 S-boxes (ou caixas de substituição) em seu processo de cifragem, alternativa correta letra A. 
>
> Durante a cifragem, o DES gera um valor intermediário de 48 bits. Esse valor é dividido em 8 blocos de 6 bits. Cada bloco de 6 bits é usado como entrada para uma das S-boxes. Cada S-box realiza uma substituição não linear, misturando os bits de entrada e produzindo uma saída de 4 bits. As S-boxes são essenciais para a confusão (mistura) no algoritmo, tornando difícil a análise criptográfica.

### 5. O Data Encryption Standard possui uma chave de 56 bits, o que torna possível um espaço de 2^56 chaves possíveis. Essa sentença trata de ataque de. . . Explique.

(a) Tempo;

(b) Matemático;

(c) Força-Bruta;

(d) DoS.

> A sentença se refere ao ataque de força-bruta, pois o espaço de chaves possíveis é de 2^56 (devido à chave de 56 bits), alternativa correta, letra C.

### 7. Considere uma cifra de Feistel composta de 16 rodadas com tamanho de bloco de 128 bits e tamanho de chave de 128 bits. Suponha que, para determinado k, o algoritmo de escalonamento de chave defina valores as oito primeiras chaves de rodada, k1, k2, . . . , k8, e depois estabeleça

### k9 = k8, k10 = k7, k11 = k6, . . . , k16 = k1

### Admita que você tenha um texto cifrado S. Explique como, com acesso a um oráculo de encriptação, você pode decriptar c e determinar m usando apenas uma única consulta a ele. Isso mostra que tal cifra é vulnerável a um ataque de texto claro escolhido. (Um oráculo de encriptação pode ser imaginado como um dispositivo que, dado um texto claro, retorna o texto cifrado correspondente. Os detalhes internos do dispositivo não são conhecidos, e você não pode abri-lo. Você só consegue obter informações do oráculo fazendo consultas a ele e observando suas respostas.)

```
1 - Descrição do cenário:
Temos uma cifra de Feistel com 16 rodadas.
O tamanho do bloco é de 128 bits.
O tamanho da chave é de 128 bits.
As primeiras oito chaves de rodada são definidas como k1, k2, …, k8.
As chaves subsequentes são derivadas de forma circular: k9 = k8, k10 = k7, k11 = k6, …, k16 = k1.
2 - Ataque de texto claro escolhido:
Vamos escolher um texto claro arbitrário m.
Consultamos o oráculo de encriptação com m e obtemos o texto cifrado correspondente c.
3 - Processo de decriptação:
Para decriptar c, precisamos encontrar as chaves de rodada correspondentes.
Como temos acesso ao oráculo de encriptação, podemos fazer uma consulta com o texto claro m e obter o texto cifrado 
4 - Estratégia:
Calculamos k9 a partir de k8 (usando a relação circular).
Em seguida, calculamos k10 a partir de k9, e assim por diante, até chegarmos a k16.
Finalmente, aplicamos as chaves de rodada na ordem inversa (de k16 a k1) para decriptar o texto cifrado c e obter o texto claro m.
```

> Conclusão:
> Com apenas uma consulta ao oráculo de encriptação, podemos determinar as chaves de rodada e decriptar o texto cifrado.
> Isso demonstra que essa cifra de Feistel é vulnerável a um ataque de texto claro escolhido, pois podemos recuperar o texto claro sem conhecer as chaves diretamente.
