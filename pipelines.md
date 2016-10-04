# Pipelines

Almost everything we build is a pipeline. Having a solid construct for processing pipelines is a powerful construct that can bee seen clearly in functional languages.

FSharp

```
buildPlan input
|> drawPlan
|> executePlan
```

Clojure

```
(-> input
    buildPlan
    drawPlan
    executePlan)
```

But in C# look like

```
executePlan(drawPlan(buildPlan(input)));
```

or 

```
var plan = buildPlan(input);
drawPlan(plan);
executePlan(plan);
```

## Build a Plan

to build a plan, I prefer to gather all of the data that could possibly be needed, and generate a "request" object. The request object contains all of the user required input as well as all of the existing state (such as the state in databases and services). Once all of that state is put together it can be fed into a service class to generate a plan.

```
void DoIt(UserInput input)
{
  var dbState = _repository.GetItem(input.ItemId);
  var apiState = _client.GetTakes(input.ItemId, input.State);
  var plan = _service.BuildPlan(dbState, apiState, input);
  
  ...
}
```

## Make a tool to visualize the plan

- example visualizers

## Make a `Fiddler` for the plan generation

Allow the business to play with the plan generation so they can have a solid mental model of how things should work.


## Execute the plan

Then build a service that executes the plan with no other logic. This should make it straight forward. This also plays well with both functional and message based systems.