# Composing A Large Plugin Surface

.Net Focused

When you are building a large system and want to allow for a "plugin" type approach for each sub system, what is the best way to compose together the variety of extension points.

## One big interface
Provide one big interface that the developers can implement. The problem with one big interface is that it can be a large surface area to implement and can make for very large class file with a lot of mixed concerns.

## With a base class
You can solve some of those issue by providing a base class that the developers can override, but now you have inhertance over composition.

