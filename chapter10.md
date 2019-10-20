# Classes

**Encapsulation**
Keep variables private, but if there's a use case for it

for example, tests need to access some method, variable. make it protected.

**Classes should be small**
Too many method, variables, and responsibilities will lead to God class

5 methods can be too large if there are too many responsibilities.

The name of a class should describe what responsibilities it fulfills.

Processors, Manager, Super usually hints combination of too many things the classes do.

If we need to describe what the class does with the word

if and or but 

it hints that we can split the class

**SRP**

class should have one and only one reason to change.

try to identify the reason to change the class

**Cohesion**

keep method and variable in the class high-cohesive.

one method should manage as much variable as possible, that means it is cohesive.

**Organizing for Change**

Any modification to current class introduces risk of breaking things.

if we need to modify class to add fuctionality, that means a reason to change.

it seems we are going to break SRP.

**Isolating from Change**

Use interface to decouple code to be easy to change and test.

this refers to DIP -> Dependency Inversion Principle

our class should depend upon abstraction not concrete detail.















