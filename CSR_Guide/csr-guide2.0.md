# CSR User Guide

Welcome to the *Customer Service Representative (CSR) User Guide*! This guide will walk you through all the functions of the subscription information panel (**CSR Panel**) in the SubCon Admin Portal.

> [!TIP]
> If you are looking for something in particular, try out our search function in the upper right corner. Otherwise, check out the guide's table of contents to the left.

## Subscription Search

**Subscription search** is a powerful tool that allows you to manage subscription and subscriber accounts. With it, you can view, edit, and access all pertinent subscription information. Checking payment information or managing transactions, like vacation stops or billing options, is easy.

To find a particular subscription, fill out the appropriate search parameters, then select either **research** or **start call**.  The **research** function returns basic subscription information, whereas the **start call** gives you powerful functionality to edit and change subscription or subscriber data.

To perform a search, you need at least one query parameter (besides `client`), but the more detailed your search query, the more precise your data return will be.

See the [query parameter definitions]() for detailed descriptions of the query parameters.

>[!NOTE]
> **Subscription Search** is continually being updated and improved. If you can't yet find a feature, know that it is on its way, and you can probably find that feature in the classic CSR portal. You can access the classic CSR portal by selecting the [**look up classic portal**]() button, located at the bottom of any subscription call page. (SCREEN SHOT OF BUTTON)

## Account Information

The **Account Information** tab displays information about the subscription/subscriber, including account details, billing address, personal details, delivery address, and products (particular subscriptions). From this tab, you can also update a subscriber's solicitation preference or restart their subscription.

### Navigation

To view subscription information, fill the appropriate search parameter fields, and select **search**.

1. Find the desired subscriber/subscription from search results.
2. Select the **start call** button of the desired subscription result.

    The application will prompt you to confirm the subscriber's email address.

3. Choose either no email, the subscriber's email, or add a new email address and select **OK**.

(GIF OF PROCESS)

### Account Information Definitions

These are the account information definitions. These values return in real-time, via API calls to either the circulation database or the Subscribe database. The **Source** column in the table below indicates the database that stores the information.

**Account Details**

| Term | Definition | Source |
|-|-|-|
| Account # | Circulation number. | Subscribe |
| Subscriber # | Naviga Subscribe's subscriber ID. | Subscribe |
| Auto-renew | Indicates whether the subscription renews automatically, for example, if subscriber qualifies for EZ Pay. | Subscribe |
| Subscriber Since | Date of when subscriber began service (`MM-DD-YYYY`). | Subscribe |
| Subscriber Stop Date | Date of when subscriber ended service (`MM-DD-YYYY`). | Subscribe |
| Client | Name of the publication. | Subscribe |
| Trial | Indicates whether the subscription is a trial. Options are either `yes` or `no`.  | Subscribe |
| Subscriber Status | Status of the subscriber's subscription. | Circulation |
| Next Publishing Date | Date of the next publication  (MM-DD-YYYY). | Circulation |
| Copies Until Expiration | Amount of subscription copies that a subscriber is scheduled to receive. If digital, days left of digital access.  | Circulation |
| Billing Method | Method of payment collection. `Office Pay` means their bill is paid to the office. `Carrier Collect` means the carrier collects payment upon delivery. `Paid Comp` and `UnPaid Comp` are complementary subscriptions. `Third Party` refers to gift subscriptions. | Subscribe |
| Delivery Method | Method of publication delivery. Options: `Route` `Mail` `Online` `Mixed` `Hybrid`. | Subscribe |

**Personal Details**

| Term | Definition | Source |
|-|-|-|
| Company Name | Subscriber’s company name. **Note**: Subscriptions can be for either a company or an individual. Depending on the subscription type, either `Company Name` or `First Name` and `Last Name` will display. | Subscribe |
| First Name | Subscriber's first name. **Note**: Subscriptions can be for either a company or an individual. Depending on the subscription type, either `Company Name` or `First Name` and `Last Name` will display. | Subscribe |
| Last Name | Subscriber's last name. | Subscribe |
| Subscriber Email | Email address upon starting a subscription. **Note**: This may or may not be the subscriber's registered email, which a subscriber uses to gain access to digital subscriptions.  | Subscribe |
| Primary Phone | Subscriber's primary phone number. | Subscribe |
| HH Sub Level | Means `Household Subscription Level` and refers to a numeric value that is associated with a subscriber’s entitlement access. The numeric values are not fixed and the client determines them. However, `99` typically refers no access and `1` typically to full access. This field is editable. | Subscribe |


**Products**

| Term | Definition | Source |
|-|-|-|
| Product ID | Product ID number. | Subscribe |
| Copies | Amount of copies of a given publication that a subscriber receives each delivery. | Subscribe |
| Product | Name of the subscription product. Note: this is *not* the name of the publication itself. | Subscribe |
| Service Code | Code that indicates the service type (e.g., `7Day` refers to a seven-day delivery or `SooooFS` a Fri, Sat, Sun delivery). | Subscribe |
| Delivery Frequency | Frequency a subscriber receives a publication (e.g., a Wednesday and Friday delivery would be `We Fr`). | Subscribe |
| AddOn | Any additional services a subscriber receives (e.g., a digital edition in addition to a print subscription or an activation of a free product). | Subscribe |

**Addresses**

| Term | Definition | Database |
|-|-|-|
| Billing Address | Subscriber's billing address. | Subscribe |
| Delivery Address | Subscriber's delivery address. | Subscribe |

From the **account information** tab, you can also [update a subscriber's solicitation preferences]() with the **account update** button and [restart a subscriber's service]() if it has been stopped.

**See also**: How to [update delivery and billing addresses]().



## Delivery Issues

The **Complaints** tab is...

### Navigation

### Workflow
<br><br><br><br><br><br><br><br><br><br>

## Payment Management

## Pause Subscription

## Cancel Subscription

## Update Solicitation Preferences

## Restart a Subscription

## Update Delivery and Billing Address