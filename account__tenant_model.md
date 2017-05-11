# Account / Tenant Model

This is simple a record of how I think about account and tenant modeling

I tend to think of a tenant as the abstract version of an account. Tenant is what we would call it in the programming world but I personally feel that Account is more accurate from a business perspective. The following is how I would design the business model of an account.

## Relational Database

I would create a schema called `accounts`

```
accounts.
  organization  -- This represents a company  
  users         -- This represents an individual 
  memberships   -- This gives a user access to an organization's stuff
```

Every user should have a default organization that is the same name as the user, this way billing details can always be associated with an organization and not a user.

```
accounts.
  billing_details -- the billing data associated with an organization (there can be many)
```

`billing_details (billing_detail_id, organization_id, type, stripe_token, effective_end)`

By having an effective end, we can use this a way to record trials \(type='trial'\)

```
Account Billing Contact
accounts.
  owner_id
  administrative_contact_id
  technical_contact_id
  billing_contact_id
```

## \# CHARGIFY NOTES

## Subscription

components

## Product Family

Name

Description

API Handle

## Product

* Product / Plan Name
* Recurring Period and Price
  * 20 / month
* Accounting Codes
* Description
* API Handle
* Trial Period
* Setup Fee

# Components

> line items?

# Coupons



