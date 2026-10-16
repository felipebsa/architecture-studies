# O que é arquitetura de software

## O que não é

- organização de pastas e arquivos
- conjunto de bibliotecas e frameworks
- onde sua aplicação roda (web, API, CLI, desktop)
- somente um nome ("clean architecture", "microservices", "MVC")

## O que é

- o modo como as partes do sistema interagem entre si e têm responsabilidades atribuídas, priorizando as decisões importantes
- estilos arquiteturais e suas implicações
- princípios e decisões de design
- características que definem o sucesso do sistema
- conhecimento em comum do time sobre o sistema

## Características de sucesso do sistema

São impactadas pelas decisões da arquitetura:

- escalabilidade
- tolerância a falhas
- disponibilidade
- segurança
- implantabilidade (deployability)
- agilidade de desenvolvimento
- manutenibilidade

Apesar das características não serem a arquitetura, uma boa arquitetura leva elas em consideração, e são elas que definem o sucesso do seu sistema.

Elas também brigam entre si, não dá pra maximizar todas ao mesmo tempo. Tipo, mais segurança costuma custar agilidade de desenvolvimento, e mais escalabilidade costuma custar simplicidade. Então escolher quais priorizar já é uma decisão de arquitetura.

## Arquitetura por implicação (Architecture by implication)

É um antipadrão de design de software. Quer dizer que a arquitetura não foi planejada nem documentada de verdade, ela surgiu de forma implícita, com base em suposições e costumes. Foram só pessoas fazendo sem rumo ou planejamento, sem decidir "vamos fazer X por causa de Y" (trade-offs). A arquitetura acaba sendo consequência acidental de como os primeiros arquivos foram criados.

- Os fatores de sucesso de um sistema devem ser bem especificados
- A arquitetura deve ser planejada, de conhecimento comum do time e analisada continuamente
- Quando a arquitetura não é planejada nem clara para o time, consideramos um caso do anti-pattern Architecture by implication
- Seguir com esse anti-pattern pode impactar bastante o sucesso do sistema
- Todo sistema tem uma arquitetura, é melhor que ela seja intencional
- Pra não cair nesse antipadrão, começa com uma boa definição dos objetivos do sistema e documentação das decisões arquiteturais

Um jeito bem usado de documentar essas decisões é o ADR (Architecture Decision Record): um arquivo curto pra cada decisão, dizendo o contexto, o que foi decidido e as consequências.
