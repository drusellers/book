# What is a loan?

When discussing software and its architecture its important that we all understand that our entity is rarely owned by one organizational unit.

I was once asked by Udi Dahan, "What is a loan?" "Can you pull something out of a drawer and say, 'This! This is your loan.'" Of course, I could not. The paper work that we sign for my mortgage (my loan) is my term sheet. That term sheet has an identifier on it. That identifier links my slice of a larger loan into the bigger loan that the bank took on. That "debt" was then balanced against a set of derivatives to protect against "rate risk". My credit score determines my "default risk" and combined set the overall interest rate.

If we peel back the covers, and look at the backing systems for these functions we can see that the entire picture of my loan is owned by multiple departments in a bank. Funding, Lending, Accounting, Risk, and Compliance. Each department wants to tack on little bits of data about my loan. 

The variety of forces at play will wreck havoc on my pretty domain model. This is where I think Eric Evan's gets it right with bounded contexts. But the complexity of getting into the nitty gritty of a bounded context leaves us with few examples.

## Random

On top of this complexity we don't have a good way to get an overview of all of our systems. We need a tool and process that can query all of our repositories of code and help glue a picture together. We have a lot of tools that can look at our code and generate static diagrams like UML of our classes, but it lacks showing how the flow and move together. This is where we need a new tool that can look at our code and generate flow diagrams. This would indeed be a powerful tool.