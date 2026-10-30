# Laboratório 01: Decomposição de Monolitos e Cloud-Native

**Disciplina:** Engenharia de Backend
**Professor:** Ronaldo Amaral
**Aluno:** [Seu Nome Aqui]
**Matrícula:** [Sua Matrícula Aqui]

> **Diretriz de Execução:** Este laboratório deve ser desenvolvido e submetido **individualmente**. Realize seus commits com as respostas diretamente neste arquivo no repositório da disciplina.

---

## Cenário Base: MonolitoShop
O e-commerce **MonolitoShop** roda em um único servidor e compartilha um banco de dados relacional gigante. Com a proximidade de picos de acesso, a equipe de engenharia identificou falhas graves de lentidão e travamentos. Você foi escalado para planejar a modernização arquitetural deste sistema legado.

### Parte 1: Bounded Contexts e Microsserviços (Eixo Y - Decomposição)
Atualmente, a classe `Usuario` no código fonte do monolito possui 45 atributos, misturando dados de login, endereço de entrega, número do cartão de crédito e histórico de navegação no catálogo. O objetivo do Eixo Y é extrair fronteiras de negócio (*Bounded Contexts*) para projetar nossos futuros microsserviços.

**Tarefa 1.1 - Mapeamento:** Separe o sistema em 3 Bounded Contexts principais (ex: Identidade, Pagamentos, Logística) que atuarão como microsserviços independentes. Distribua quais informações da classe "Usuário" legado devem pertencer a cada novo microsserviço.

> **Sua Resposta 1.1:**
> - **Microsserviço 1 (Nome):** [Quais dados do usuário ficam aqui?]
> - **Microsserviço 2 (Nome):** [Quais dados do usuário ficam aqui?]
> - **Microsserviço 3 (Nome):** [Quais dados do usuário ficam aqui?]

**Tarefa 1.2 - Diagrama de Arquitetura:** Crie um diagrama demonstrando a quebra do monolito nesses 3 novos microsserviços. O diagrama deve ilustrar as fronteiras dos contextos e seus respectivos bancos de dados isolados. (Utilize a sintaxe Mermaid diretamente neste Markdown ou insira o link de uma imagem gerada em ferramentas como draw.io/Lucidchart).

> **Exemplo de como estruturar seu diagrama Mermaid (Substitua pelos seus dados e expanda conforme necessário):**
>
> ```mermaid
> graph TD
>     Client[Cliente / App] --> API[API Gateway]
>
>     API --> MS1[Microsserviço A]
>     API --> MS2[Microsserviço B]
>     API --> MS3[Microsserviço C]
>
>     MS1 --> DB1[(Banco de Dados A)]
>     MS2 --> DB2[(Banco de Dados B)]
>     MS3 --> DB3[(Banco de Dados C)]
> ```

> **Sua Resposta 1.2 (Insira seu diagrama abaixo):**
>
> [Insira seu código Mermaid ou link do diagrama aqui]

### Parte 2: O Cubo AKF e a Escalabilidade (Eixo X - Clonagem)
Durante os testes de carga, o servidor web atingiu 100% de CPU. A equipe decidiu colocar um *Load Balancer* e subir 3 instâncias idênticas do servidor. No entanto, ao fazer isso, os clientes começaram a reclamar que os itens desapareciam misteriosamente do carrinho de compras a cada clique.

**Tarefa:** Explique por que os itens somem do carrinho ao clonar o servidor (estado) e qual é a solução Cloud-Native (Stateless) para resolver este problema.

> **Sua Resposta:**
> [Escreva sua explicação técnica e a solução aqui]

### Parte 3: Particionamento de Dados (Eixo Z)
O serviço de Pedidos foi extraído com sucesso do monolito, mas seu banco de dados começou a apresentar lentidão devido ao volume massivo de transações originadas de todo o Brasil.

**Tarefa:** Proponha uma estratégia de *Sharding* (particionamento) para o banco de dados de Pedidos. Qual seria a sua chave de partição (Shard Key) e por quê?

> **Sua Resposta:**
> [Justifique sua estratégia de Sharding aqui]
