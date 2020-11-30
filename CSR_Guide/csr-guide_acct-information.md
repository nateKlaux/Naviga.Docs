## Account Information

The **Account Information** tab displays information about the subscription/subscriber. From this tab, you can:

- view account details, personal details, addresses, and products
- update a subscriber's solicitation preference
- restart a stopped subscription

### Navigation

To view the **account information** tab, perform a [subscription search](www.subsearch.com). The **start call** feature defaults to the **account information** tab.

(GIF OF PROCESS)

### Account Information Definitions

These are the account information definitions. These values return in real-time, via API calls to either the circulation database or the Subscribe database. These databases sync together on a nightly basis. The **Source** column in the table below indicates the database that stores the information.

**Account Details**

| Term | Definition | Source |
|-|-|-|
| Account # | Circulation number. | Subscribe |
| Subscriber # | Naviga Subscribe's subscriber ID. | Subscribe |
| Auto-renew | Indicates whether the subscription renews automatically, for example, if the subscriber qualifies for EZ Pay. | Subscribe |
| Subscriber Since | Date of when subscriber began service (`MM-DD-YYYY`). | Subscribe |
| Subscriber Stop Date | Date of when subscriber ended service (`MM-DD-YYYY`). | Subscribe |
| Client | Name of the publication. | Subscribe |
| Trial | Indicates whether the subscription is a trial. Options are either `yes` or `no`.  | Subscribe |
| Subscriber Status | Status of the subscriber's subscription. | Circulation |
| Next Publishing Date | Date of the next publication  (MM-DD-YYYY). | Circulation |
| Copies Until Expiration | Amount of subscription copies that a subscriber is scheduled to receive. If digital, days left of digital access.  | Circulation |
| Billing Method | Method of payment collection. `Office Pay` means their bill is paid to the office. `Carrier Collect` means the carrier collects payment upon delivery. `Paid Comp` and `UnPaid Comp` are complimentary subscriptions. `Third Party` refers to gift subscriptions. | Subscribe |
| Delivery Method | Method of publication delivery. Options: `Route` `Mail` `Online` `Mixed` `Hybrid`. | Subscribe |

**Personal Details**

| Term | Definition | Source |
|-|-|-|
| Company Name | Subscriber’s company name. **Note**: Subscriptions can be for either a company or an individual. Depending on the subscription type, either `Company Name` or `First Name` and `Last Name` will display. | Subscribe |
| First Name | Subscriber's first name. **Note**: Subscriptions can be for either a company or an individual. Depending on the subscription type, either `Company Name` or `First Name` and `Last Name` will display. | Subscribe |
| Last Name | Subscriber's last name. | Subscribe |
| Subscriber Email | Email address upon starting a subscription. **Note**: This may or may not be the subscriber's registered email, which a subscriber uses to gain access to digital subscriptions.  | Subscribe |
| Primary Phone | Subscriber's primary phone number. | Subscribe |
| HH Sub Level | Means `Household Subscription Level` and refers to a numeric value that is associated with a subscriber’s entitlement access. The numeric values are not fixed and the client determines them. However, `99` typically refers to no access and `1` typically to full access. This field is editable. | Subscribe |


**Products**

| Term | Definition | Source |
|-|-|-|
| Product ID | Product ID number. | Subscribe |
| Copies | Amount of copies of a given publication that a subscriber receives each delivery. | Subscribe |
| Product | Name of the subscription product. Note: this is *not* the name of the publication itself. | Subscribe |
| Service Code | Code that indicates the service type (e.g., `7Day` refers to a seven-day delivery or `SooooFS` a Fri, Sat, Sun delivery). | Subscribe |
| Delivery Frequency | Frequency a subscriber receives a publication (e.g., a Wednesday and Friday delivery would be `We Fr`). | Subscribe |
| AddOn | Any additional services a subscriber receives (e.g., a digital edition *and* a print subscription or an activation of a free product). | Subscribe |

**Addresses**

| Term | Definition | Source |
|-|-|-|
| Billing Address | Subscriber's billing address. To edit addresses, check out this [how-to](example.com). | Subscribe |
| Delivery Address | Subscriber's delivery address. To edit addresses, check out this [how-to](example.com). | Subscribe |

From the **account information** tab, you can also [update a subscriber's solicitation preferences](example.com) with the **account update** button and [restart a subscriber's service](example.com) if it has been stopped.

**See also**: How to [update delivery and billing addresses]().