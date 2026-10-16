# Architectural patterns and design patterns

## Architectural patterns

Architectural patterns are ready and tested solutions for problems that show up all the time when you're sketching the structure of a software system. It's like a floor plan in civil engineering: instead of starting from zero, you use a well-known model (a template).

But remember that we always adapt it to our project instead of just copying, that's why it's an architecture pattern and not literally an architecture.

We use patterns for several reasons: easier maintenance, a common language for the team, avoiding hacky workarounds, and for projects that will keep growing it's perfect so you don't start completely from zero.

### Some patterns

**Layered:** most common in monoliths. The system is split into floors, where each one talks to the one below:

presentation layer --> business layer --> data layer

**MVC (Model View Controller):** used to organize the user interface, splitting the system into 3 parts:
- Model: the data and the rules
- View: what the user sees
- Controller: receives the user action and connects the view and the model

**Microservices:** each service has its own logic and database, like a payment service and a delivery service, separated.

**Event-driven:** components don't call each other directly. Whoever did something publishes an event (e.g. the orders service publishes "order created"), an intermediary in the middle (a broker, a message queue) delivers that event, and the other interested components react when they can. It's used a lot in high scale systems, but you can use events even inside a monolith.

**REST:** REST itself is an architectural style for web APIs. The main ideas are resources identified by URLs, stateless communication (the server doesn't keep a session between requests) and a standard interface. In practice it's almost always used with HTTP and its methods (GET, POST, PUT, DELETE, PATCH), that's why the two are kind of intertwined, but REST is the style and HTTP is the protocol.

## Design patterns

Different from the architectural one, which would be the macro and defines the global structure of the whole system (how the project is split, where the parts communicate and where the data is saved), the design one would be the micro. It solves specific code problems and how classes and functions are organized in one piece of your system, so it's easier to reuse or test and doesn't get coupled.

A design pattern is not a framework. A framework is ready code you install (like FastAPI), and a design pattern is an idea of how to organize code that you implement yourself. Some examples: Repository, Strategy, Factory, Observer.

So: architectural patterns are to architectures what design patterns are to objects.
