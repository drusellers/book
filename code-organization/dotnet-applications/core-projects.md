# Core Projects

Playing with GitBook

## Highlevel Overview of the Root folders

```text
~/
    Applications/
    Features/
    Infrastructure/
    Integration/
```

### Applications

Application code is all about grouping the code into hostable applications and giving them a name. Some projects will build out X applications and need a way to partition that code.

```text
~/
    Applications/
        <Application Name>/
            <Application Name>.cs
        Console/
            <Console>.cs
        Web/
            <Web>.cs
```

This is particularly nice when you want to provide the majority of the application as a website but may need a few scheduled tasks to run with the same code.

This design idea draws from FubuMVC which had a central application model that was shared between web applications and messaging applications. In addition the idea of a shared application environment comes from Ruby on Rails and Clojure applications that have REPLs for their web applications.

### Features

Contains code that is CRITICAL to the business problem at hand.

* Fast moving code
* Unique to the application

A simple feature would be implemented using something like this

```text
~/
    Features/
        <feature name>/
            <feature module (IoC Registration)>.cs
            I<feature>.cs
            <feature>.cs
        BrandReport/
            BrandReportModule.cs
            IBrandReport.cs
            BrandReport.cs
```

At its most simplistic this is what my features look like. This is your lego piece.

#### Internal Feature Structure

```text
~/SomeFeature/
    CommandLine/  ManyConsole command line
    AutoMapper/   AutoMapper Profiles
    Json/         Json Serializers
    Mapping/      NHibernate / Dapper Mapps
    <interfaces>.cs
    <implementations>.cs
    <models>.cs
    <micro types>.cs
```

**The Need for Ceremony**

If this seems heavy handed please realize that the goal is clarity across a large number of code bases. Not just the project you are working on today. Another goal is to really drive out single responsibility, by forcing each feature to be implemented in its own folder. Too many times I have opened up a project to see the lovely folder of _Services_ that has 30+ files in it. Trying to understand the system from the file system level in that context is very difficult. The goal with this model is to be very explicit about what each piece of the code does.

**Features vs Entities \(aka Models\)**

Why are my Entities features? Entities are features like anything else. In this case they provide a sense of memory for the application. A service may need to persist something across runs and that is one way of thinking of Entities. This becomes more true if you are using a Rich Domain model vs an Anaemic Domain model as they have so many more function points. The Entity that is a feature is the Aggregate Root in DDD terms.

**What about my Models \(or Entities\) folder?**

Again, just another dumping ground. What feature owns the model or entity?

**Micro Types**

These can be a feature for me as well, and reperesent an _addition_ to the language. Some Micro Types might be sharable across projects \(like Money\) and some may be application specific. This is one where I usually default to application specific.

* [http://codebetter.com/drusellers/2010/01/27/business-primitives-1-2/](http://codebetter.com/drusellers/2010/01/27/business-primitives-1-2/)
* [http://codebetter.com/drusellers/2010/02/04/business-primitives-2-2/](http://codebetter.com/drusellers/2010/02/04/business-primitives-2-2/)

#### Organizational Structure

> Flat is better than nested
>
> The Zen of Python - [https://www.python.org/dev/peps/pep-0020/](https://www.python.org/dev/peps/pep-0020/)

One of the things that I believe in is trying to keep a codebase flat by default. It helps to expose ideas as top level constructs. To that end I prefer the following format to nesting when possible.

```text
~/
    Features/
        Serializers/
        Serializers.Json/
        Serializers.Xml/
```

This format exposes the options available, and treats them as the full blown feature that they are.

### Infrastructure

Contains code that is not necessarily business code, but the business code uses to build up on higher level abstractions. I use this kind of code to give my self a better api to either 3rd party libraries or to solve a common problem across business domains. This code should be easily extractable from the code base and **COULD** exist in a library if need be.

* medium to slow moving code
* unique to the business

Some examples of infrastructure code include:

* Persistance
* Messaging
* Email

### Integration

Contains code that is needed to talk to external services. Ideally this code is agnostic to business needs and is all about just talking to the 3rd party system. The business code then takes this code to do its work. This code should be easily extractable from the code base and **COULD** exist in a library if need be.

* medium to slow moving code
* **NOT** unique to the business or application

> Integration / Infrastructure – end up being VERY juicy spots to easily pull code out of into shared libs. It truly highlights cross application duplication, it also helps to standardize common config file settings.

## Examples of a Feature Folder

### The Object Only Feature

```text
~/Features/<KeyEntity>/
  //might have validations
  //might have ORM related mappings
  <Entity>.cs
  //typically no IoC registrations
```

Often there are key entities in the solution that need to exist as a feature all to themselves. These entities tend to have a lot of touch points through out the code base and in order to avoid cyclical namespace references we need to put them in their own folder. Doing so will show how important they are, as they will exist outside of any service code.

### The Service Only Feature

