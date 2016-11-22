# Composing A Large Plugin Surface

.Net Focused

When you are building a large system and want to allow for a "plugin" type approach for each sub system, what is the best way to compose together the variety of extension points.

## One big interface
Provide one big interface that the developers can implement. The problem with one big interface is that it can be a large surface area to implement and can make for very large class file with a lot of mixed concerns.

## With a base class
You can solve some of those issue by providing a base class that the developers can override, but now you have inheritance over composition.

But you still end up with one class that has a whole lot of methods on it. Making it hard to use.

## Central Interface with Jump Points

```csharp
var retailer = GetRetailer("kuryakyn");
retailer.Orders.AcceptUpdates();
retailer.Inventory.ProcessInventory();
retailer.Orders.GenerateSessionKey();
```

The class Retailer is very basic and takes in the jump points as dependencies. By default we register safe / no-op jump points that log to that effect. Then the developer can implement each jump point one at a time.

