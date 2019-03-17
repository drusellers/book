# Patterns

## Sister Database

> Pattern for accessing and manipulating vendor software at the database level

### Problem

Given the database VendorDb how can I add my own sprocs and views to it so I can easily manage the database and its integration work.

### Preferred Solution

We create what we call a "sister database" - this is a schema that can query the database through linked databases. In your application database, create a schema that is named for the database its going to connect. Inside of there create your sprocs and views as needed. You can then turn on linked databases and get access to everything that way.

## Mocked Database

> Pattern for testing against a vendored database

### Problem

How do you test against a vendor database

### Preferred Solution

I copy the schema to my local machine and make it a 2nd database that I build when I build my applications database.

