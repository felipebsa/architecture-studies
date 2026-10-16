# Architectural styles: monolithic and distributed

## Monolithic

Examples: layered, pipeline...

The whole application is built and runs as a single unit. In the trade-off you get initial simplicity, performance and easy tracing when debugging, but in return you get low granular scalability.

You can scale it, by running several copies of the monolith behind a load balancer, just not in a granular way: you can't scale only one part of it. That's why a monolith is not only for small projects or fast releases, there are big systems running monoliths in production for years.

## Distributed

Examples: microservices, event-driven, microfrontends...

It's when you break the system into several parts that run on different computers or servers and talk to each other over the network, using HTTP APIs, message queues, etc.

Microservices is one type of distributed architecture, not another name for it. Every microservice system is distributed, but not every distributed system is microservices.

The trade-off is more complexity and needing more infrastructure, but in return it's more flexible and granular. It can have better fault tolerance if it's done well, because one service going down doesn't take down the rest. But the network also creates new failures that a monolith doesn't even have (a service being down, timeouts, duplicated messages).

## Difference between the two

The biggest difference would be the trade-off of complexity in exchange for granular scalability. And the characteristic that differs the most is that one is centralized and the other is decentralized.

## Examples

1. A traditional web monolith: a single project in Next.js (fullstack) or Laravel that renders the pages, runs the rules and saves to the database. Everything together on the same machine.
2. A distributed web system: a React app hosted on Vercel (front-end), talking through a REST API to three different back-end services (one in Node.js for users, one in Python for reports and a RabbitMQ queue to send emails).

## Topology

A drawing or map of how the components of a system are connected, both the logical side (the data flow) and the physical side (the real servers), like the client-server topology (requests and responses).
