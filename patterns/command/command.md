# Command

## Why to use?

- used to encapsulate all information needed to perform an action or trigger an event at a later time.

## When to use?

- GUI buttons and menu items
- Multi-level undo: If all user actions in a program are implemented as command objects, the program can keep a stack of the most recently executed commands. When the user wants to undo a command, the program simply pops the most recent command object and executes its ```undo()``` method.
- Networking: It is possible to send whole command objects across the network to be executed on the other machines, for example player actions in computer games.

## Structure

Four terms always associated with the command pattern are _command_, _receiver_, _invoker_ and _client_.
- A _command_ object declares an interface for executing an operation
- _ConcreteCommand_ defines a binding between a Receiver object and an action and implements Execute by invoking the corresponding operation(s) on Receiver
- The _receiver_ then does the work. It knows how to perform the operations associated with carrying out the request.
- An _invoker_ asks the command to carry out the request.
- The _client_ creates a ConcreteCommand object and sets its receiver

![command uml](https://github.com/Porter84/HarrisonJones/blob/master/patterns/composite/Command_UML_class_diagram.png "Command UML")

## Typical usage in JavaScript

TODO