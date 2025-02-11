# Solid

Introduced by Uncle Martin, acronim for five design priciples aiming to make object-oriented designs more understadeable, flexible and mantainable.

> The are statements on the order of “An apple a day keeps the doctor away.” This is a good principle, it is good advice, but it’s not a pure truth, nor is it a rule. (...) Practice, practice, practice, practice. Be prepared to make lots of mistakes. And, of course, apply what you’ve learned on the job, and ask your peers to review your work. Pair program with them if at all possible. “As iron sharpens iron, so one man sharpens another.”


## Single responsibility principle

> "[t]here should never be more than one reason for a class to change.

> "Gather together the things that change for the same reasons. Separate those things that change for different reasons.

Imagine such a module can be changed for two reasons. First, the content of the report could change. Second, the format of the report could change. These two things change for different causes. The single responsibility principle says that these two aspects of the problem are really two separate responsibilities, and should, therefore, be in separate classes or modules.

## Open-closed principle

(by Bertrand) Software entities should be open for extension, but closed for modification. 

A module will be said to be open if it is still available for extension. For example, it should be possible to add fields to the data structures it contains, or new elements to the set of functions it performs.

A module will be said to be closed if [it] is available for use by other modules. This assumes that the module has been given a well-defined, stable description (the interface in the sense of information hiding).


## Liskov substitution principle

(by Barbara liskov) Functions that use pointers or references to base classes must be able to use objects of derived classes without knowing it. 

An object (such as a class) may be replaced by a sub-object (such as a class that extends the first class) without breaking the program.

## Interface segregation

Clients should not be forced to depend upon interfaces that they do not use.

> "ISP splits interfaces that are very large into smaller and more specific ones so that clients will only have to know about the methods that are of interest to them. "

ISP is also a key principle in the design of distributed systems in general and one of the six IDEALS principles for microservice design.

> "The design problem was that a single Job class was used by almost all of the tasks. Whenever a print job or a stapling job needed to be performed, a call was made to the Job class. This resulted in a 'fat' class with multitudes of methods specific to a variety of different clients. (...) Instead of having one large Job class, a Staple Job interface or a Print Job interface was created that would be used by the Staple or Print classes, respectively, calling methods of the Job class. Therefore, one interface was created for each job type, which was all implemented by the Job class. Therefore, one interface was created for each job type, which was all implemented by the Job class."

## Dependency inversion principle

1. High-level modules should not import anything from low-level modules. Both should depend on abstractions (e.g., interfaces).
2. Abstractions should not depend on details. Details (concrete implementations) should depend on abstractions.

By dictating that both high-level and low-level objects must depend on the same abstraction, this design principle inverts the way some people may think about object-oriented programming.
