# **Atividade - Introdução a Segurança de Redes**

### **1. O que é a arquitetura de segurança OSI?**

>
> **A arquitetura de segurança OSI é uma estrutura conceitual que descreve como os sistemas de comunicação de rede devem ser organizados para garantir a segurança da informação. Ela se baseia no modelo OSI (Open Systems Interconnection), que é uma referência para entender como diferentes protocolos de rede interagem.
>
> **

### **2. Qual é a diferença entre ameaças à segurança passivas e ativas?**

>
> **As ameaças à segurança passivas são aquelas em que um invasor tenta obter acesso não autorizado a informações confidenciais sem alterar os dados. Por outro lado, as ameaças ativas envolvem a modificação, destruição ou interrupção dos dados ou dos sistemas de comunicação.
>
> **	

### **3. Liste e defina resumidamente as categorias de ataques passivos e ativos à segurança.**

>
> **As categorias de ataques passivos incluem monitoramento não autorizado, análise de tráfego, captura de dados e coleta de informações. Enquanto isso, as categorias de ataques ativos incluem interrupção de serviço, modificação de dados, destruição de dados e usurpação de identidade.
>
> **

### **4. Liste e defina resumidamente as categorias dos serviços de segurança.**

>
> **As categorias de serviços de segurança incluem confidencialidade (garantir que apenas usuários autorizados possam acessar informações), integridade (garantir que os dados não sejam alterados durante a transmissão), autenticação (verificar a identidade dos usuários), não repúdio (garantir que o remetente de uma mensagem não possa negar o envio) e controle de acesso (determinar quem pode acessar quais recursos).
>
> **

### **5. liste e defina resumidamente as categorias dos mecanismos de segurança.**

>
> **As categorias de mecanismos de segurança incluem criptografia (transformar dados em um formato ilegível para proteger sua confidencialidade), controle de acesso (gerenciar quem pode acessar recursos de rede), controle de integridade (verificar se os dados não foram modificados indevidamente), autenticação (confirmar a identidade dos usuários ou sistemas) e auditoria (registar e analisar eventos de segurança para detectar atividades suspeitas).
>
> **

### **6. Considere um caixa eletrônico, ATM no qual os usuários fornecem um cartão e um número de identificação pessoal (senha). Dê exemplos de requisitos de confidencialidade, integridade e disponibilidade associados com esse sistema e, em cada caso, indique o grau de importância desses requisitos.**

>
> **No contexto de um caixa eletrônico (ATM), os requisitos de segurança são:
>
> Confidencialidade: Proteger informações sensíveis dos usuários, como números de conta e senhas, para evitar acesso não autorizado e fraudes. A divulgação dessas informações pode resultar em perdas financeiras e danos à reputação do banco.
>
> Integridade: Garantir que as transações dos usuários não sejam alteradas durante a comunicação com o sistema do caixa eletrônico. Qualquer manipulação pode causar prejuízos financeiros e danos à confiança no sistema do ATM.
>
> Disponibilidade: Manter o sistema do caixa eletrônico sempre disponível para os usuários realizarem transações. Interrupções no serviço podem causar inconveniência aos clientes e danos à reputação do banco. A disponibilidade é crucial para evitar perda de clientes e danos à imagem da instituição financeira.
>
> **

### 7. Para responder as letras abaixo, por favor, consulte o livro-texto da disciplina:

#### (a) Desenhe uma matriz similar ao Quadro 1.4 que mostre o relacionamento entre serviços de segurança e ataques.

|                               | Confidencialidade | Integridade | Autenticação | Disponibilidade |
| ----------------------------- | ----------------- | ----------- | -------------- | --------------- |
| Monitoramento não autorizado | Vulnerável       | Vulnerável | Vulnerável    | Resiliente      |
| Modificação de dados        | Resiliente        | Vulnerável | Vulnerável    | Vulnerável     |
| Usurpação de identidade     | Vulnerável       | Resiliente  | Vulnerável    | Vulnerável     |
| Interrupção de serviço     | Resiliente        | Resiliente  | Resiliente     | Vulnerável     |

#### **(b) Desenhe uma matriz similar ao Quadro 1.4 que mostre o relacionamento entre mecanismos de segurança e ataques.**

|                               | Criptografiaco | Controle de acessoco | Controle de integridade | Autenticação | Auditoria   |
| ----------------------------- | -------------- | -------------------- | ----------------------- | -------------- | ----------- |
| Monitoramento não autorizado | Resiliente     | Resiliente           | Vulnerável             | Vulnerável    | Vulnerável |
| Modificação de dados        | Resiliente     | Resiliente           | Vulnerável             | Vulnerável    | Resiliente  |
| Usurpação de identidade     | Resiliente     | Vulnerável          | Vulnerável             | Vulnerável    | Resiliente  |
| Interrupção de serviço     | Resiliente     | Resiliente           | Resiliente              | Resiliente     | Resiliente  |
