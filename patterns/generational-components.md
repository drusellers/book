# Generational Components

Sometimes we need to build systems that can represent change over time, or "generations." We did this a lot at OMC and it roughly boiled down to a model like:

```text
thing -* thing_generation
```

So, we had a one to many relationship, then the "thing" model could also track the current generation

```text
thing
id | current_generation_id | ...

thing_generation
id | thing_id | ...
```

Then in the code we could delegate various "properties/attributes" to the `current_generation` so that we could continue to program against a code model that didn't have incessant child navigation. This worked out really well in ruby with its `delegate` support. 

