# Fluxo de dependências vs fluxo de dados (DIP e DI)

Um bom princípio é nunca deixar uma responsabilidade de nível mais alto depender de uma de nível menor (nível de importância, no caso), e seguir isso mesmo quando o fluxo de dependências não coincide com o fluxo de dados. Isso serve pra proteger a responsabilidade mais importante quando você muda uma menos importante. Pra conseguir isso usamos DIP e DI:

- DIP: Dependency Inversion Principle (Princípio de Inversão de Dependência)
- DI: Dependency Injection (Injeção de Dependência)

## DIP (princípio)

É o D do SOLID. O objetivo é desacoplar: não deixar a lógica principal (alto nível) ficar refém de detalhes técnicos de baixo nível.

Normalmente a gente inverte esse fluxo. Por exemplo, A (alto nível) --> B (baixo nível), e o A precisa do B. Pra seguir o DIP podemos fazer uma interface que é ditada pelo A, e assim o A nem sabe que o B existe, e com isso invertemos essa dependência (é uma das maneiras).

## DI (técnica)

É um padrão de design / técnica de programação que serve pra passar pra uma classe as dependências que ela precisa pra funcionar, em vez de deixar a própria classe criar essas dependências. Ela recebe um objeto pronto pelo construtor da classe, por métodos ou por propriedade.

Dá pra usar DI sem seguir o DIP: se você injeta uma classe concreta em vez de uma interface, a dependência continua apontando pro detalhe de baixo nível. A DI é o jeito de entregar a dependência, o DIP é sobre pra onde ela aponta.
