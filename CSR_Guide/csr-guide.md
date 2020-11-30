# CSR User Guide

Welcome to the *CSR User Guide*! This guide documents all aspects of the **subscription information** panel (<- dif word for panel??) of the Subscriber Concierge Platform. If you are looking for something in particular, you can use our docs' search function (upper right corner). Otherwise, there are three main sections in this user guide:

- Subscription search
- Subscriber search
- Event viewer

The sections of this guide corroborate with the function of the CSR Subcon Admin section. We'll explore each feature in depth below, but as a brief overview, **subscription search**  returns data particular to a subscription. From this returned data, you easily identify a customer's subscription and interact with the customer's data. **Subscriber search** differs in that it returns more concise customer data. You are still able to edit customer data through the `start call` button. **Event viewer** is another search feature that allows you ....

## Subscription Search

This search function returns a database with the following columns/categories:

- Subscriber
- Account
- Full name
- Address
- Phone
- E-mail
- Billing Status
- Client

By default, the search orders by billing status, showing **active** accounts first. You can reorder the search result by clicking on any column name.

> [!NOTE]
> You need at least one query parameter, not including `client`.

### Add Account and Start Call Function

![Add Account and Start Call](/CSR_Guide/screen_captures/add_account.png)

If a subscription doesn't exist, and you wish to create one, you can add it:

1. Select **+ Add account and start call**.
2. Enter a subscriber's email if they have one. If not, select **No email**.

***NOTE, NATE: I AM UNABLE TO PROGRESS PAST THIS STEP. APPEARS THAT THIS FUNCTION DOESN'T WORK.***

### Research Function

[MAYBE: Insert picture of button](LINK)

The research function provides more detailed, but read-only, information than the general database. By default, selecting the **research** button brings you to a customer's print subscription information. To access their digital subscription information, select the **digital** tab.

#### Events Function

You are able to access event history by selecting **show events** or the digital event history by selecting **digital** then **show events**.

PROVIDE PROCEDURE TO EXPLAIN THIS TOOL.

### Call Function

[MAYBE: Insert picture of button](LINK)

The call function provides you the ability to edit customer data. After selecting the **start call** button, you will be prompted to confirm or update a subscriber's email address. Your options are:
- Subscriber's email address
- Other email
- No email

The **other email** box allows you to add a subscriber's email address into the database. Otherwise, select the listed email address or **no address** if the subscriber doesn't wish to include one, then select **OK** to continue. You'll be directed to the **Account Information** tab, which is the default landing tab.

#### Account Information

The **Account Information** tab details the subscriber's account details, billing address, personal details, delivery address, and products (subscriptions).

In addition to a subscriber's account details, you can **>MUTE?<** a subscriber's communication with the **account update** button. [INSERT IMAGE OF BUTTON HERE]
1. Select **account update** button
2. Select **type**
3. Choose a category: do not call, do not email, do not mail
4. Determine whether this applies to all or only this subscription
5. Select the **submit** button

#### Payment and Billing
#### Service
#### Stop
#### Move
#### Offers
#### Digital

**MIGHT BE BEST TO LEAVE THESE AS IS, AS THEY ALL PERFORM SIMILARLY**
##### Show Events
##### Show Remarks
##### Show Access Events

#### Look Up Classic Portal ??NOT SURE ABOUT THIS??

### Subscription Search Parameter Glossary

|  Parameter Name | Parameter Description             |
|-----------------|-----------------------------------|
| Phone number    | Subscriber's phone number.        |
| Email           | Subscriber's email address.       |
| Account         | Subscriber's account number.      |
| House number    | Subscriber's home address number. |
| Street          | Subscriber's street name.         |
| Postal/ZIP Code | Subscriber's postal code.         |
| Last name       | Subscriber's last name.           |
| First name      | Subscriber's first name.          |
| Client          | Subscriber's publication.         |

### Error Messages and Solutions

| Error Message             | Description            | Solution             |
|---------------------------|------------------------|----------------------|
| CSR presentation is missing. Please, choose “Default SubCon Admin presentation” in CMS (on the newspaper division level) or add presentation binding for your role.  Source: SubConAdmin. (**ENCOUNTERED WHEN ADDING SUBSCRIPTION**) |                        |                      |
| There is no Circ system found for selected newspaper. (**ENCOUNTERED WHEN ADDING SUBSCRIPTION**)                                          |                      |
| Could not find any subscription. Source: Subscribe API                  | Parameters too narrow  | Add more parameters. |













## Subscriber Search


### Subscriber Search Parameter Glossary

|  Parameter Name | Parameter Description             |
|-----------------|-----------------------------------|
| Phone number    | Subscriber's phone number.        |
| Email           | Subscriber's email address.       |
| Address         | Subscriber's address              |
| Account         | Subscriber's account number.      |
| First name      | Subscriber's first name.          |
| Last name       | Subscriber's last name.           |







## Event Viewer

## Notes, drafts, etcs

- Nathan, what does this product do?
  - This product ... allows you to search for subscriptions, subscribers, and events. 
  - Allows you to add subscribers, subscriptions.
- Is there a particular type of user?
  - Very specific. The end-user here is a Customer Service Rep.

Sometimes you may not have all of a customer's information. 

The more parameters you enter, the quicker and narrower your search will be. 


## Glossary to-do:
define: 
- Phone number
- email
- account
- house number
- street
- postal/ZIP code
- last name
- first name
- client

## Event type glossary


## Error message:
" ! Could not find any subscription. Source: Subscribe API"
"At least one field is required."
"There is no information to display from GetPaymentMethods endpoint"

An error has occurred during the execution of the request. Source: Subscribe API

Enter a valid processed publishing date. Source: NavigaApi 


An error has occurred.
Source: SubConAdmin

The specified tenant does not support the requested functionality. Source: Subscribe API