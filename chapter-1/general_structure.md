# General Structure


## Root Folder Structure (aka Solution Structure)

Solution in this case comes from the Visual Studio nomenclature but what we are talking about is a single software unit. This is typically for me a single git repository or this would be a folder in a [mono repository](https://developer.atlassian.com/blog/2015/10/monorepos-in-git/). But this represents a single deployed "software entity".

```
~/
  src/
  doc/
  lib/
  <make files>
```

The way this folder looks will depend on your "platform". A lot of the discussion is going to be about what happens in the `src` folder versus what happens outside of it.

##### A .Net version circa 2016

```
~/
  src/
  doc/
  Packages/ -- NuGet packages
  build.bat
  <proj>.sln
```

##### A rust version circa 2016

```
~/
  src/
  doc/
  Cargo.toml
```

### Goal: Help me find my way

Having a consistent approach even at this entry level will help people new to the project feel comfortable in the new program.

## Src folder layout

### Goal: Make it easy to identify harvestable code

For the majority of my career I have worked in internal corporate IT. The following structure is constructed with the thought that identifying code for harvest has value. Additionally, I need a way for the many development teams to communicate that a section of code would be of value to others in the organization. This has lead to the following folder structure which has worked very well for this goal.

> > Integration / Infrastructure – end up being VERY juicy spots to easily pull code out of into shared libs. It truly highlights cross application duplication, it also helps to standardize common config file settings.

```
~/
  applications/
  features/
  infrastructure/
  integration/
```

### Application
Application code is all about grouping the code into hostable applications and giving them a name. Some projects will build out X applications and need a way to partition that code.

This is particularly nice when you want to provide the majority of the application as a website but may need a few scheduled tasks to run with the same code.

This design idea draws from FubuMVC which had a central application model that was shared between web applications and messaging applications. In addition the idea of a shared application environment comes from Ruby on Rails and Clojure applications that have REPLs for their web applications.

### Features

Contains code that is CRITICAL to the business problem at hand.

- Fast moving code
- Unique to the application

```
~/
    Features/
        <feature name>/
```

The only reason this code exists is to serve the application and is not reuasble outside of any API the application provides.


### Infrastructure

```
~/
  Infrastructure/
    <Infrastructure Piece>/

```

Contains code that is not necessarily business code, but the business code uses to build up on higher level abstractions. I use this kind of code to give my self a better api to either 3rd party libraries or to solve a common problem across business domains. This code should be easily extractable from the code base and COULD exist in a library if need be.

- medium to slow moving code
- unique to the business

Some examples of infrastructure code include:
- Persistance
- Messaging
- Email

### Integration

```
~/
  Integration/
    <Integration Piece>/

```

Contains code that is needed to talk to external services. Ideally this code is agnostic to business needs and is all about just talking to the 3rd party system. The business code then takes this code to do its work. This code should be easily extractable from the code base and COULD exist in a library if need be.+

- medium to slow moving code
- NOT unique to the business or application


