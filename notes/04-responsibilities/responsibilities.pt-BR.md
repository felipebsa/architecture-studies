# Responsabilidades

## O que é responsabilidade

Pode se dizer que é a obrigação de realizar uma tarefa ou saber uma certa informação ("Object Design", Rebecca Wirfs-Brock e Alan McKean).

A responsabilidade de um objeto define o que ele é obrigado a realizar ou saber, cada um tendo seu próprio papel. O conjunto de responsabilidades de um objeto deve ser relacionado, pra evitar que um objeto tenha mais de um papel. E lidar com dados da mesma natureza não faz com que duas ou mais responsabilidades sejam relacionadas.

## Como atribuir responsabilidades (SRP e SoC)

**Single Responsibility Principle (SRP):** um objeto deve ter uma única responsabilidade.

A definição mais famosa, do Uncle Bob, é que uma classe deve ter um único motivo pra mudar. Ajuda bastante na prática: se dá pra pensar em dois motivos diferentes pra mexer numa classe, ela provavelmente tem duas responsabilidades.

**Separation of Concerns (SoC):** uma responsabilidade deve ser desempenhada por um único objeto.

Esse é o jeito da palestra de enxergar. A definição mais comum é mais ampla: separar o sistema em partes, onde cada uma cuida de um assunto.

Então SRP + SoC: um objeto deve ter uma única responsabilidade, e esse objeto deve bastar pra desempenhar essa responsabilidade.

Uma boa arquitetura define de maneira efetiva como devemos atribuir responsabilidades às partes do sistema. Isso é uma decisão de design que faz parte da arquitetura.

## Níveis de responsabilidade

Algumas responsabilidades são mais importantes que outras, então elas são separadas em níveis. Quanto maior o nível, mais longe aquela responsabilidade está dos inputs e outputs do sistema.

[1] entrada -> [2] caso de uso (aplicação) -> [3] regras de negócio (domínio) -> [1] saída (infraestrutura)

domínio > aplicação > input & output
