# General Respnsibility assignment software patterns (or principles)

Is the set of nine fundamental priciples in object design and responsibility assignment.

A standard for tried-and-tested programming principles in object-oriented design.



## Information expert

## Creator

The creation of entities is one of the more common activities in object oriented design. 

**Problem:** Who should be responsible for creating say the class Coffee?

**Solution:** It does not need to be necesarely the class Coffee itself, you can delegate the responsibility to a higher class (B) if:

- B contain or compositely aggregate instances of Coffee
- B record instances of Coffee
- B closely use instances of Coffee
- B have the initializing information for instances of Coffee and pass it on creation

A common example in testing are Factories where we delegate to an external function with default test data the creation of a Coffee instance.

## Controller

**Problem:** Who should be responsible for handling an input system event?


**Solution:** A controller should be used to deal with all system events of a use case, and may be used for more than one use case. 

For instance, *Create* and *Delete* a cetain domain (Coffee), can have a single class called *DomainController*.

The controller is defined as the first object beyond the UI layer, that "controlls" the system with the objective of delegating the work

## Indirection

**Problem:** Where to assign responsibility, to avoid direct coupling between two (or more) things? How to de-couple objects so that low coupling is supported and reuse potential remains higher?

**Solution:** Comonnly one would separate the responsibilities between this things, or the responsibility in layers, introducing intermediate classes. This mediation in software architecture is comonly seen as the *model-view-controller* pattern. Were the data (model) get separated from its representation (view) via a class that defines how data can be handled.

## Low coupling / Loose coupling

Lower dependency between clases translates into
- independance on change between them 
- higher reuse potential

## High cohesion

Attempts to keep objects appropriately focused, manageable and understandable. High cohesion is generally used in support of low coupling. 

Low cohesion is a situation in which a set of elements, of e.g., a subsystem, has too many unrelated responsibilities. Subsystems with low cohesion between their constituent elements often suffer from being hard to comprehend, reuse, maintain and change as a whole

## Polymorphism

Responsibility for defining the variation of behaviors based on type is assigned to the type for which this variation happens using polymorphic operations.

The user of the type should use polymorphic operations instead of explicit branching based on type.

## Protected variations

**Problem:** I want to change the postgresDb to SQLlite

**Solution:** Protect elements from the variations on other elements **by wrapping the focus of instability** with an interface and using polymorphism to create variations. In this way, the implementation details are hidden, and one can replace diferent implementations if the contract (inteface) is respected.

Identify points of predicted variation or instability; assign responsibilities to create a stable interface around them.

## Pure fabrication

A pure fabrication is a class that does not represent a concept in the problem domain either with a specific doman.

One can achieve low coupling, high cohesion, and potential reuse if we separate this type of logic. This kind of class is called a *service* in DDD.