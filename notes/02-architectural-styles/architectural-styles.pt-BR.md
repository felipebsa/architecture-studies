# Estilos arquiteturais: monolítica e distribuída

## Monolítica

Exemplos: em camadas, pipeline...

Toda a aplicação é construída e executada como uma única unidade. No trade-off você ganha simplicidade inicial, desempenho e rastreamento fácil na hora de depurar, mas em troca tem baixa escalabilidade granular.

Dá pra escalar sim, subindo várias cópias do monolito atrás de um load balancer, só que não de forma granular: não dá pra escalar só uma parte dele. Por isso monolito não é só pra projeto pequeno ou produção rápida, tem sistema grande rodando monolito em produção há anos.

## Distribuída

Exemplos: microservices, event-driven, microfrontends...

É quando você quebra o sistema em várias partes que rodam em computadores ou servidores diferentes e se comunicam pela rede, usando APIs HTTP, filas de mensagens, etc.

Microsserviços é um tipo de arquitetura distribuída, não outro nome pra ela. Todo microsserviço é distribuído, mas nem todo sistema distribuído é microsserviço.

O trade-off é maior complexidade e exigir mais infraestrutura, mas em troca é mais flexível e granular. Ela pode ter maior tolerância a falhas se for bem feita, porque um serviço caindo não derruba o resto. Mas a rede também cria falhas novas que o monolito nem tem (serviço fora do ar, timeout, mensagem duplicada).

## Diferença entre as duas

A maior diferença seria o trade-off de complexidade em troca da escalabilidade granular. E a característica que mais diferencia é que uma é centralizada e a outra é descentralizada.

## Exemplos

1. Um monólito web tradicional: um único projeto em Next.js (fullstack) ou Laravel que renderiza as telas, processa as regras e salva no banco de dados. Tudo junto na mesma máquina.
2. Um sistema web distribuído: uma aplicação React hospedada na Vercel (front-end), conversando via API REST com três serviços diferentes no back-end (um em Node.js para usuários, um em Python para relatórios e uma fila RabbitMQ para enviar e-mails).

## Topologia

Desenho ou mapeamento de como os componentes de um sistema estão conectados, tanto a lógica (o fluxo de dados) quanto a física (os servidores reais), tipo a topologia cliente-servidor (requests e responses).
