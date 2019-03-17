# Account \/ Tenant Model

## Account / Tenant Model

This is simple a record of how I think about account and tenant modeling

I tend to think of a tenant as the abstract version of an account. Tenant is what we would call it in the programming world but I personally feel that Account is more accurate from a business perspective. The following is how I would design the business model of an account.

### Relational Database

I would create a schema called `accounts`

```text
accounts.
  organization  -- This represents a company  
  users         -- This represents an individual 
  memberships   -- This gives a user access to an organization's stuff
```

Every user should have a default organization that is the same name as the user, this way billing details and security rules can always be associated with an organization and not a user. Additionally it can always be traversed from user to organization to account and then back down as needed

#### Security Model Notes

**Key Administrative Roles**

* Technical Contact - contact to reach out when we have questions of them for technical things
* Administrative Contact - can add / remove users
* Billing Contact - can change billing details
* Owner - user that can close the account

#### Billing Model Notes

```text
billing_details.
  id
  account_id
  billing_user_id # user in charge of key billing items? or role based
  base_plan_id    # The plan that was used as a starting point 
  price_override  # The amount to be charged to the customer
  stripe_token?
  chargify_token?
  effective_start
  effective_end
```

By having an effective end, we can use this a way to record trials \(type='trial'\)?

## Chargify Notes

### Subscription

components

### Product Family

Name

Description

API Handle

### Product

* Product / Plan Name
* Recurring Period and Price
  * 20 / month
* Accounting Codes
* Description
* API Handle
* Trial Period
* Setup Fee

## Components

> line items?

## Coupons

