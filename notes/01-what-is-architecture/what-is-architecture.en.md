# What software architecture is

## What it is not

- how folders and files are organized
- a set of libraries and frameworks
- where your application runs (web, API, CLI, desktop)
- just a name ("clean architecture", "microservices", "MVC")

## What it is

- the way the parts of the system interact with each other and get their responsibilities, prioritizing the important decisions
- architectural styles and what they imply
- design principles and decisions
- the characteristics that define the success of the system
- the knowledge the team shares about the system

## Success characteristics of the system

They are affected by architecture decisions:

- scalability
- fault tolerance
- availability
- security
- deployability
- development agility
- maintainability

These characteristics are not the architecture, but a good architecture takes them into account, and they are what define the success of your system.

They also compete with each other, so you can't maximize all of them at the same time. Like, more security usually costs development agility, and more scalability usually costs simplicity. So choosing which ones to prioritize is already an architecture decision.

## Architecture by implication

It's a software design anti-pattern. It means the architecture was never really planned or documented, it showed up implicitly, based on assumptions and habits. It was just people building without direction or planning, without deciding "we'll do X because of Y" (trade-offs). The architecture ends up being an accidental consequence of how the first files were created.

- The success factors of a system should be well specified
- The architecture should be planned, known by the whole team and reviewed continuously
- When the architecture is not planned or clear to the team, we consider it a case of the Architecture by implication anti-pattern
- Keeping this anti-pattern can have a big impact on the success of the system
- Every system has an architecture, it's better if it's intentional
- To avoid this anti-pattern, start with a good definition of the system goals and document the architecture decisions

A common way to document these decisions is the ADR (Architecture Decision Record): a short file for each decision, saying the context, what was decided and the consequences.
