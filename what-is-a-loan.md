# What is a loan?

When discussing software systems with people one mental exercise that I like to go through is "What is a loan?" Many people in America are familiar with with the concept of a [loan](https://en.wikipedia.org/wiki/Loan), and the basic complexities involved in procuring one. Once, the listener is invested in the conversation, I simple ask "What is a loan?". "Can you pull out something, anything, and point at it and say 'This is my loan'?" I will posit that you can not. A loan, is a complex financial instrument that is typically presented in an abstract manner to most consumers. I get money today and pay you back more over time. However, underneath the covers, my loan is backed by some asset, so there are records of collateral some place tied back to my "loan" by an identifier. For a given bank, my loan will often be too small to fund on its own, so the bank will take my loan and a few other loans and get the money needed from the market for this basket of loans, so now the funding is linked to my loans. The bank's ability to "fund" my loan will effect the rate I get on my loan so there is a relationship there. Then there is my personal credit score that gets added into the mix and affects my term sheet and will be linked into my "loan" as well.

* Principle
* Funding \(Originization\)
* Rate Risk
* Loanee Risk \(Default Risk\)
* Audit

If we peel back the covers, and look at the backing systems for these functions we can see that the entire picture of my loan is owned by multiple departments in a bank. Funding, Lending, Accounting, Risk, and Compliance. Each department wants to tack on little bits of data about my loan. Soon, my "loan" will look like a Christmas tree with little doo dads hung on it by all of the various departments.

So, in this case, the idea of a `loan` is really an abstraction, or a means to encapsulate a variety of tools, data points, and techniques into one single item for consumer consumption. It has been packaged up with a nice little bow on it so that anyone can understand it at a basic level.

As a company grow's the number of departments that want to analyze my loan in some unique and valuable way will continue to grow until the system becomes untenable. This is why I find both Enterprise Architecture and the concepts of "Domain Driven Design" as powerful forces in the construction of an enterprise. These two thought tools give us a means to address and scale the complexity of our enterprise.

The number of systems at play, each in their own silo provides one compelling reason to embark on data warehousing projects.

## Random

On top of this complexity we don't have a good way to get an overview of all of our systems. We need a tool and process that can query all of our repositories of code and help glue a picture together. We have a lot of tools that can look at our code and generate static diagrams like UML of our classes, but it lacks showing how the flow and move together. This is where we need a new tool that can look at our code and generate flow diagrams. This would indeed be a powerful tool.

