# Security

## Authentication

Who are you?
In the BCL this is the IIdentity

## Authorization

What are you allowed to do?
In the BCL this is the IPrincipal

## Xxxx

the roles a user/identity is given

## Roles
A grouping of rights
A person in the Admin role might have all rights.
A person in the User role would only have access to a subset of those rights.

## Rights

A fine grained access control

## Asset 
What is being protected? Requires a right to use.

## Thoughts

### Check Rights not Roles
Roles group rights, but we should not check for roles in our code, because that is a means for managing the explosion of rights. We should check the right in our code to see if something can be done.

```
//DON'T
if(user.IsInRole("Admin"))
{
    //delete user
}
  
//DO
if(user.HasRight("User:Delete"))
{
    //delete user
}
```

Imagine that you needed to add another role that can delete users, now you have to modify the security checking code vs checking to rights.

### Claims based approach

A claims based approach requires a central service to know all of the users / rights / roles and then once authenticated and authorized will send to the application a token that proves the user is X and here are the rights that they have. However, if you are follow claims and try to send ALL of the rights the payload gets quite heavy and also forces the central to know all of the rights offered by a system. So typically the central service is only away of the roles, if that.

If you look at SAML, one of the first claims based I heard about back in the Indigo days, the goal was to put the Authentication and Authorization into another services as a part of a SOA build out. Now all of the other services don't have to know how to do things. This also lead to OAuth as a way of sharing authentication knowledge.