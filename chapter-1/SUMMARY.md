# Summary

The way you organize your code is important. As I'm sure you can imagine. The following lays out a structure that has worked well for me the last 10+ years and has evolved through many different approaches.

My original structuring of applications was very much centered around the "model". I would ask myself questions like "What _IS_ a loan?" I would dive into trying to understand the domain I was working in and I would then start to apply basic "analysis" patterns. Using this process I would dive deeper and deeper into each component further breaking it down as my understanding increased. (Object Thinking)

Over time that model didn't scale well to the businesses I worked for. We don't always have time for me to reach that level of understanding. It was about this time that I started to read CSLA by Rocky Lhotka and I started to get a better sense of how a technical implementation could effect design.

-- stuff

Then I read one of the more influential posts:

http://alistair.cockburn.us/Hexagonal+architecture


The influences of FubuMVC and Bottles

The influences of IoC with Castle.Windsor -> StructureMap + Fubu -> AutoFac

Vertical Slices vs Horizontal Slices