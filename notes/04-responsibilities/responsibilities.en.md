# Responsibilities

## What a responsibility is

You could say it's the obligation to perform a task or to know some information ("Object Design", Rebecca Wirfs-Brock and Alan McKean).

The responsibility of an object defines what it must do or know, each one having its own role. The set of responsibilities of an object should be related, so one object doesn't end up with more than one role. And handling data of the same nature doesn't make two or more responsibilities related.

## How to assign responsibilities (SRP and SoC)

**Single Responsibility Principle (SRP):** an object should have a single responsibility.

The most famous definition, from Uncle Bob, is that a class should have only one reason to change. It helps a lot in practice: if you can think of two different reasons to change a class, it probably has two responsibilities.

**Separation of Concerns (SoC):** a responsibility should be performed by a single object.

That's how the talk sees it. The more common definition is broader: splitting the system into parts, where each one takes care of one concern.

So SRP + SoC: an object should have a single responsibility, and that object should be enough to perform that responsibility.

A good architecture defines in an effective way how we should assign responsibilities to the parts of the system. This is a design decision that is part of the architecture.

## Levels of responsibility

Some responsibilities are more important than others, so they are split into levels. The higher the level, the farther that responsibility is from the inputs and outputs of the system.

[1] input -> [2] use case (application) -> [3] business rules (domain) -> [1] output (infrastructure)

domain > application > input & output
