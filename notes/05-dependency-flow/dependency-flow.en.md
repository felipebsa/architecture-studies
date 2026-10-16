# Dependency flow vs data flow (DIP and DI)

A good principle is to never let a higher level responsibility depend on a lower level one (level of importance, in this case), and to follow that even when the dependency flow doesn't match the data flow. This protects the more important responsibility when you change a less important one. To do that we use DIP and DI:

- DIP: Dependency Inversion Principle
- DI: Dependency Injection

## DIP (principle)

It's the D in SOLID. The goal is decoupling: not letting the main logic (high level) be hostage to low level technical details.

Usually we invert this flow. For example, A (high level) --> B (low level), and A needs B. To follow DIP we can create an interface that is dictated by A, so A doesn't even know B exists, and that way we invert this dependency (it's one of the ways).

## DI (technique)

It's a design pattern / programming technique used to give a class the dependencies it needs to work, instead of letting the class create those dependencies itself. It receives a ready object through the class constructor, methods or a property.

You can use DI without following DIP: if you inject a concrete class instead of an interface, the dependency still points to the low level detail. DI is how the dependency gets delivered, DIP is about where it points.
