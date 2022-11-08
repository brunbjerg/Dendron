---
id: xl7t20b4wm1jsn34znhql7l
title: Chapter 1 - Getting Started with Design Patterns
desc: ''
updated: 1667919100872
created: 1667914680326
---

Creational patterns: How to construct objects.

OOP brings together data and behavior  and a class may inherit the structure and behavior of an ancestor class. 

Structural patterns: How to extend objects.

Behavioral patterns: How to make objects work seperately and how to make them communicate with each other. 

GoF: 23 design patterns, 16 were unnecessary by LISP (close to Julia)



## Software design principles 
### Solid
1. Single Responsibility: All modules, classes and function should have a single functional objective.  Only one reason to change.The benefit here is that I as a programmer can focus on a single context during development. The size of each component is smaller. The code is easier to understand. The code can be tested more easily.

1. Open/Closed: Thid principle states that every module should be open for extension but closed for modification. Benefits are: Existing components acan be reused to derive new functionalities. Components are loosely coupled so it is easier to replace them without affecting the existing functionality
1. Liskov Substitytion: A program that accepts type T can also accept type S (which is a subtype of T) without any change in behavior or intended outcome. Benefits are: Functions can be reused for any subtype passed in the arguments.
1. Interface Segregation: IA client should not be forced to implement interfaces that it does not need to use. Benefits are: Software components are more modular and reusable; new implementations can ve created more easily.
1. Dependency Inversion: High-level classes should not depend on low-level classes; instead high-level classes should depend on an abstraction that low0level classes implement. Benefits: Components are decoupled; the sustem becomes flexible and can adapt to changes more easily. Low-level components can be replaced with out affecting high-level components. This is important for my project! 


### DRY: Do not Repeat Yourself
Duplication code is bad. Eliminate it and create a common function. Often we get 90% similarity, yes, refactor to a common interface. 


### KISS: Keep It Simple, Stupid!
I often like to think ahead and try to deal with all kinds of future scenarios. Avoid over engineering. Agile development puts value in fast, small and high quality results over pergection or excess engineering.


### POLA: Principle of Least Astonishment 
Software components should be easy to understand and its behavior should never ne a surprise: Keep the following in mind: Make sure that the names of the module, function or function arguments are clear and unambiguousl ensure that modules are right-sized and well maintained; ensure that interfaces are small and easy to understand; ensure that functions have few positional arguments.

Right sizes modules seems important. I need to understand interfaces. What does it mean that a function has few positional arguments 

### YAGNI: You Are not Gonna Need It
This principle says that I should only develop software that is needed today. This principle came from Extreme Programming.

Always implement things when you actually need them, never when you just foresee that you need them. Makes sense! Should remember this. I often over think instead of working.Of developers focus on things that we/I fell customers need. This has been proved many times to be ineffecient. Scenarios: The functionality is never needed; the business environment changes and the sustem has to be redesigned or replaced; the technology changes and the system has to be upgraded to use a new library a new framework or new language.

You are not gonna need it! 


### POLP: Principle of Least Privilege
On;u give access to information or functions that is needed. Most important pillar for building secure applixations. Benefits: Sensitive data is protected and not exposed to non-privileged users; the system can be tested more easily since the number of use cases is limited; the system becomes less prone to misuse because only limited access is given and the interface is simpler.


# Software quality objectives
* Reusability: Top down, and then break problem into smaller problems. Eventually we can design code. Pluggable interfaces. Important principles: Single purpose; well degined; function type substitution (liskov); interfaces are degined as a small set of functions; interfaces are used to bridge between components. Resuability is one of the reasons open source is so succesful. Julia open source package borrow from each other.
* Performance: Compiler friendly, translate program into optimized machine code. Characteristics of high-performance code: functions are small and can be optimized easily. Simple logic in functions; data is laid out in contiguous memory space so the compiler can fully utilize CPU hardware; memory allocation should be kept to a minimum to avoud excessive garbage collection. 
* Maintenance: Technical debt, when you have to update multiple parts of the code for a single change. List: No unused code; noduplicate code; code is concise and short; code is clear and easy to understand; every function has a single purpose; every module contains functions that relate to and work with each other. A proper design makes large applications easy to change. 
* Safety: Each module exposes a minimum set of types, functions and variables; each function is called with arguments such that the respective types implement the expected behavior of the function;missing data is handled properly; variables are limited to the smallest scope; exceptions are caught and handled accordingly. Embarrassing and costly incidents. 


# Questions
1. What are the benefits of using design patterns
    * Making code maintainable so we do not incur technical debt as ours programs grow in size. 
    * Making code reusable, readable and safe
1. Name some key design principles:
    * SOLID: Single Responsibility; Open/Closed, meaning the components should be open to extentions but closed to modification; Liskov, meaning subtypes should always be able to go into a function and give the same return value.
1.  What problem does the Open/Closed  principle solve?
    * It makes code easy to extend while making sure that existing functionality is kept operational. 

1. Why is interface segregation important for software reusability?
    * Interfaces that are coupled makes it hard to reuse them for different purposes as they become rigid for the specific problem
1. That are the simplest ways to keep an application maintainable?
    * Avoid duplication
1. What is a good practice for avoiding over-engineered and bloated software?
    * Only focus on the present problem and needs
1. How does memory usage affect system performance?
    * Allocating memory and subsequently freeing it again is expensive.

    