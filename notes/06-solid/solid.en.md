# SOLID

These are 5 principles of object-oriented design:

- S: SRP (Single Responsibility Principle)
- O: OCP (Open-Closed Principle)
- L: LSP (Liskov Substitution Principle)
- I: ISP (Interface Segregation Principle)
- D: DIP (Dependency Inversion Principle)

## Single Responsibility Principle (SRP)

The principle says each class should be specialized in a single subject and have only one responsibility inside the software. That doesn't mean it can only have one method: it can have several, as long as all of them serve the same subject. The rule of thumb is having only one reason to change.

This way you don't create a god class, which would be a class packed with responsibilities. It can look efficient, but it's the complete opposite, and you notice it when you need to modify or change something.

## Open-Closed Principle (OCP)

It's the open and closed principle: open for extension and closed for modification. When you add a new feature, the idea is to add new code instead of touching what's already there and working, which lowers a lot the chance of introducing new bugs.

It's not "never touch anything" (fixing a bug is modifying, and that's fine). It's designing the code so new behaviors come in by adding, not by editing an if/elif that keeps growing.

Example in LocTis: in `core/tenant.py`, the `ENTITY_MODELS` dictionary maps each entity type to its model. For a new entity to have notes, you only add one line to the dictionary, and the `get_owned_entity` function stays the same.

## Liskov Substitution Principle (LSP)

Objects of a child class should be able to replace objects of the parent class without breaking the program. So any place in the system that works with the parent has to keep working if it receives the child.

LSP is about behavior, not about reusing fields. The child can't break the parent's promise, and when that happens, what breaks is the code that uses the parent.

Example: if the `Bird` class has `fly()` and `Penguin` inherits from it and throws an error when someone calls `fly()`, a function that makes all birds fly breaks when it gets a penguin, even though nobody touched that function. The penguin inherited a promise it can't keep.

Other signs LSP was broken: the child overrides a method to do nothing, returns a different type than the parent, or does something unexpected.

## Interface Segregation Principle (ISP)

Don't force a class to implement interfaces and methods it won't use. It's better to have several small, specific interfaces than one big interface that forces everyone to implement everything. So don't add something to the parent just because one of the children needs it, create something specific for it instead.

Example: a `Printer` interface with `print`, `scan` and `send_fax`. A simple printer would be forced to implement `scan` and `send_fax` without doing any of that. The right way is splitting it into `Prints`, `Scans` and `SendsFax`, and each class implements only what it uses.

The bird case can also be solved with ISP: instead of `Bird` having `fly` for everyone, split it into `FlyingBirds` and `FlightlessBirds`. Then the penguin never promises what it can't do.

LSP and ISP look alike because they attack the same problem from different sides:

- LSP: the child can't break the parent's promise
- ISP: don't force anyone to promise what they don't need

## Dependency Inversion Principle (DIP)

Note: DI (Dependency Injection) is a design pattern, a technique, not a principle. DIP is the principle.

The idea is: depend on abstractions, not on implementations. The two rules are:

- high level modules should not depend on low level modules, both should depend on abstractions
- abstractions should not depend on details, details should depend on abstractions

Car example: the driver (high level) only depends on the steering wheel and the pedals, which are the abstraction. The engine and the carburetor are the details (low level). That's why you can swap a combustion engine for an electric one and the person keeps driving the same way.

So to follow DIP we use an interface, which is the abstraction, and that gives us decoupling and flexibility to add more things.

Python doesn't have an `interface` keyword like Java. What plays that role is `ABC` (from the `abc` module) or `Protocol` (from `typing`).

## Reflection

After writing all of this I noticed SOLID is very close to the idea of software architecture: letting the project grow with as few bugs as possible and making it easier to change, that's why there's decoupling, simplicity and reuse.

But SOLID works at the level of classes and modules (the micro), and architecture applies similar ideas to the whole system (the macro), just like the difference between design patterns and architectural patterns. And "scaling" here means the code being able to grow without becoming a mess, not handling more traffic.
