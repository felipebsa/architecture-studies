# Padrões arquiteturais e padrões de design

## Padrões arquiteturais

Os padrões arquiteturais são soluções prontas e testadas pra problemas que acontecem toda hora quando você vai rascunhar a estrutura de um sistema de software. É como uma planta baixa da engenharia civil: em vez de fazer do zero, você já usa um modelo consagrado (um template).

Mas lembrando que a gente sempre adapta ao nosso projeto e não simplesmente copia, por isso é um padrão de arquitetura e não literalmente uma arquitetura.

Usamos padrões por vários motivos: facilidade de manutenção, linguagem comum entre o time, evitar gambiarras, e pra projetos que vão continuar crescendo é perfeito pra não começar totalmente do zero.

### Alguns padrões

**Em camadas:** mais comum em monolitos. O sistema é dividido em andares, onde cada um conversa com o de baixo:

camada de apresentação --> camada de negócio --> camada de dados

**MVC (Model View Controller):** usado pra organizar a interface do usuário, separando o sistema em 3 partes:
- Model: os dados e as regras
- View: o que o usuário vê
- Controller: recebe a ação do usuário e faz a ponte entre a view e o model

**Microservices:** cada serviço tem sua própria lógica e banco de dados, tipo serviço de pagamento e serviço de entrega separados.

**Event-driven:** os componentes não chamam um ao outro diretamente. Quem fez alguma coisa publica um evento (ex.: o serviço de pedidos publica "pedido criado"), um intermediário no meio (broker, fila de mensagens) entrega esse evento, e os outros componentes interessados reagem quando podem. É muito usado em sistemas de alta escala, mas dá pra usar eventos até dentro de um monolito.

**REST:** o próprio REST é um estilo arquitetural pra APIs web. As ideias principais são recursos identificados por URL, comunicação sem estado (o servidor não guarda sessão entre as requisições) e uma interface padronizada. Na prática ele quase sempre é usado com HTTP e os métodos dele (GET, POST, PUT, DELETE, PATCH), por isso os dois ficam meio entrelaçados, mas REST é o estilo e HTTP é o protocolo.

## Padrões de design (design patterns)

Diferente do arquitetural, que seria o macro e define a estrutura global do sistema inteiro (como o projeto é dividido, onde as partes se comunicam e onde os dados são salvos), o de design seria o micro. Ele resolve problemas específicos de código e de organização de classes e funções num pedaço do seu sistema, pra ficar mais fácil de reutilizar ou testar e não ficar acoplado.

Um padrão de design não é um framework. Framework é código pronto que você instala (tipo o FastAPI), e o padrão de design é uma ideia de como organizar o código que você mesmo implementa. Alguns exemplos: Repository, Strategy, Factory, Observer.

Então: padrões arquiteturais estão para arquiteturas assim como padrões de projeto estão para objetos.
