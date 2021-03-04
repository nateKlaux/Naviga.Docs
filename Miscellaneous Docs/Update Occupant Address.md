
# Update Occupant email address USE CASES

## Prerequisite Information

Important Information!

There are two types of email addresses:

- registered email address
- subscriber/subscription email address

Subscriber/subscription email addresses are used when a Subscriber completes the act of subscribing. There typically is only _one_ subscriber email.

Registered email addresses are used to access registration-related things. There can be multiple registered email addresses. For instance, the Subscriber has a registered email address, and that can be the same as the Subscriber email (but it doesn't have to be). However, if that Subscriber decides to share his registration with say his partner, than that person also receives a registration email address. 


***Understanding the above is prerequisite for understanding what is below.***


## Use Case 1 - ***User adds or updates their email address through our application*** 

The user can do this on either their profile page or their account tab in SA.

With this use case, there are three scenarios:

- `The email address **is not** already registered in the Subscribe database`
  - Since the email address is not already registered, it will be added or updated in the following tables:
    - email field in the Subscription table
    - email field in the Subscriber table
    - email field will be added or updated for the occupant in circulation system

***This scenario will likely occur when the person updating their email address is the Subscriber, but hasn't created a registered email yet.***

- `The email address **is** already registered in the Subscribe database AND is the same in both the Subscriber and Subscription table`
  - The email address will be added to the following tables:
    - Email field in the Subscription table
    - Email field int he Subscriber table
    - Email address filed in the email address table
    - Email field in the registration table
    - Email will be added or updated for the occupant in the circulation system

***This scenario will likely occur when the person updating their email address is both the Subscriber and registered user.***


- `The email address **is** already registered in the Subscribe database AND is the not the same in both the Subscriber and Subscription table`
  - The email address will be updated in the following tables:
    - Email address filed in Email address table
    - Email field in registration table.

***This scenario will likely occur when the person updating their email address is not the Subscriber, but a registered user.***


## Use case 2 - **User registers email address and links their existing subscription through our application**

With this use case, there are two scenarios:

- `The email address that the user registered in the Subscribe database does not exist in the Subscribe and Subscription tables`
  - The following tables will be updated:
    - Email address filed in Email address table
    - Email field in registration table

***This scenario will likely occur when the person linking their account is not the Subscriber, but a registered user.***

- `The email address that the user registered in the Subscribe database does exist in the Subscribe and Subscription tables`
  - The following tables will be updated:
    - Email field in Subscription table
    - Email field in Subscriber table
    - Email address filed in Email address table
    - Email field in registration table
    - Email will be added/updated for the occupant in the circulation system

***This scenario will likely occur when the person linking their account is both the Subscriber and registered user.***

