# SOLID

São 5 princípios de design orientado a objetos:

- S: SRP (Single Responsibility Principle)
- O: OCP (Open-Closed Principle)
- L: LSP (Liskov Substitution Principle)
- I: ISP (Interface Segregation Principle)
- D: DIP (Dependency Inversion Principle)

## Single Responsibility Principle (SRP)

O princípio diz que cada classe deve ser especializada em um único assunto e ter apenas uma responsabilidade dentro do software. Isso não quer dizer que ela só pode ter um método: ela pode ter vários, desde que todos sirvam ao mesmo assunto. A régua é ter um único motivo pra mudar.

Assim você não cria uma god class, que seria uma classe lotada de responsabilidades. Pode parecer eficiente, mas é muito pelo contrário, e você percebe isso na hora que vai modificar ou alterar algo.

## Open-Closed Principle (OCP)

É o princípio do aberto e fechado: aberto pra extensão e fechado pra modificação. Quando você for adicionar uma funcionalidade nova, a ideia é adicionar código novo em vez de mexer no que já tá lá e funciona, o que diminui muito as chances de introduzir bugs novos.

Não é "nunca mexer em nada" (corrigir bug é modificar, e tudo bem). É desenhar o código de um jeito que comportamentos novos entrem adicionando, e não editando um if/elif que só cresce.

Exemplo no LocTis: no `core/tenant.py`, o dicionário `ENTITY_MODELS` liga cada tipo de entidade ao model dela. Pra uma entidade nova poder ter notas, é só adicionar uma linha no dicionário, e a função `get_owned_entity` continua igual.

## Liskov Substitution Principle (LSP)

Objetos da classe filha devem poder substituir objetos da classe pai sem quebrar o programa. Ou seja, qualquer lugar do sistema que funciona com o pai tem que continuar funcionando se receber o filho.

O LSP é sobre comportamento, não sobre reaproveitar campos. O filho não pode quebrar a promessa do pai, e quem quebra quando isso acontece é o código que usa o pai.

Exemplo: se a classe `Ave` tem `voar()` e o `Pinguim` herda dela e dá erro quando alguém chama `voar()`, uma função que manda todas as aves voarem quebra quando recebe um pinguim, mesmo sem ninguém ter mexido nela. O pinguim herdou uma promessa que não consegue cumprir.

Outros sinais de que o LSP foi violado: o filho sobrescreve um método pra não fazer nada, retorna um tipo diferente do pai ou faz alguma coisa inesperada.

## Interface Segregation Principle (ISP)

Não forçar uma classe a implementar interfaces e métodos que ela não vai usar. É melhor ter várias interfaces pequenas e específicas do que uma grande que obriga todo mundo a implementar tudo. Então não adicionar algo no pai só porque um dos filhos precisa, e sim criar algo específico pra isso.

Exemplo: uma interface `Impressora` com `imprimir`, `escanear` e `enviar_fax`. Uma impressora simples seria obrigada a implementar `escanear` e `enviar_fax` sem fazer nada disso. O certo é separar em `Imprime`, `Escaneia` e `EnviaFax`, e cada classe implementa só o que usa.

O caso das aves também se resolve com ISP: em vez de `Ave` ter `voar` pra todo mundo, separa em `AvesQueVoam` e `AvesQueNaoVoam`. Aí o pinguim nunca promete o que não faz.

LSP e ISP são parecidos porque atacam o mesmo problema por lados diferentes:

- LSP: o filho não pode quebrar a promessa do pai
- ISP: não obrigar ninguém a prometer o que não precisa

## Dependency Inversion Principle (DIP)

Detalhe: DI (Dependency Injection) é um design pattern, uma técnica, não um princípio. O DIP é o princípio.

A ideia é: dependa de abstrações, não de implementações. As duas regras são:

- módulos de alto nível não devem depender de módulos de baixo nível, os dois devem depender de abstrações
- abstrações não devem depender de detalhes, detalhes devem depender de abstrações

Exemplo do carro: quem dirige (alto nível) depende só do volante e dos pedais, que são a abstração. O motor e o carburador são os detalhes (baixo nível). Por isso dá pra trocar um motor a combustão por um elétrico e a pessoa continua dirigindo do mesmo jeito.

Então pra respeitar o DIP a gente usa uma interface, que é a abstração, e assim consegue desacoplamento e flexibilidade pra adicionar mais coisas.

Em Python não existe a palavra `interface` como em Java. Quem faz esse papel é `ABC` (do módulo `abc`) ou `Protocol` (do `typing`).

## Reflexão

Depois de escrever tudo isso reparei que o SOLID é bem parecido com a ideia da arquitetura de software: deixar o projeto crescer com o mínimo de bugs e mais facilidade de mudar, por isso o desacoplamento, a simplicidade e o reaproveitamento.

Só que o SOLID trabalha no nível das classes e módulos (o micro), e a arquitetura aplica ideias parecidas no sistema inteiro (o macro), igual a diferença entre padrão de design e padrão arquitetural. E "escalar" aqui é o código conseguir crescer sem virar bagunça, não aguentar mais acessos.
