# Summary

The way you organize your code is important. As I'm sure you can imagine. The following lays out a structure that has worked well for me the last 10+ years and has evolved through many different approaches.

# 2001

No organizational style, reading - and just trying to get a grip on it all.

# 2004

My original thought process of applications was to apply what basics I had learned about Object Oriented Programming (OOP) to truly try and model the real world. I had read enough Plato to understand the _ideal_ form he used and sought to apply it to my classes as well. I would dive into what a word meant, and leaned into my dictionary. I would ask myself questions like "What _IS_ a loan?"  I would break down a word into its components and see if I could do the same with my objects. ([Object Thinking](https://www.amazon.com/Object-Thinking-Developer-Reference-David/dp/0735619654))

Then I read Visual Basic .NET Business Objects by Rocky Lhotka and realized there was more to the technical approach to code organization, and I learned about separating data access from the business logic for the first time. I was still writing Stored Procedures at this point and following in lock step with CLSA, by having my classes implement the .Net Remoting protocol so that I could switch between local and remote objects. I was also still programming in Win forms but was at a loss for how I could centralize my data between myself and my coworker.

It also focused on handling the network boundary between data access and business logic.

# 2006

> IoC - DI - MVC

Influences of [Hammett](http://www.hammettblog.com/) as I dug into IoC as a means to implement Castle on Rails. [Introducing Castle - Part 1](https://www.codeproject.com/articles/9157/introducing-castle-part-i)

http://alistair.cockburn.us/Hexagonal+architecture

The influences of IoC with Castle.Windsor -> StructureMap + Fubu -> AutoFac

[Domain Driven Design](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215)

The influences of FubuMVC and Bottles

Vertical Slices vs Horizontal Slices