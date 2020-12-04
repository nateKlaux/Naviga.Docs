## Subscription Search

This guide will introduce you to the **Subscription Search** feature of the Subcon Admin Portal. **Subscription Search** allows you to search for and manage subscriptions.

## Find a Subscription

To find a particular subscription:

1. Select the **subscription search** button on the left side of the window.
2. Fill in the appropriate search parameters.
3. Select the **search** button.
A list of matches will display.
4. Find the desired subscription from the **search results** and select either **research** or **start call**

> [!TIP] Though including `client` in your search query can be helpful, you cannot search by it exclusively.
> Attempting to do so will return an error, and the mandatory fields will be highlighted.
> Populate at least one mandatory field in addition to `client` for a successful search.
> In general, the more detailed your search parameters, the more precise and quick your return will be.

(GIF OF PROCESS)

### Research

The **research** feature displays read-only overview of the subscription. You can view account information, digital subscription information, and search the account's history of events, filtering the events by type and time. This feature does not start a call.

### Start Call

The **start call** feature allows you to manage subscription information.
You can process requests, update information, review events, etc.
Likely, you will find yourself using this feature in most scenarios.
By default, the feature displays the [account information](www.example.com) tab.

**Note**: The client can configure whether the **start call** feature prompts you to confirm a subscriber's email address. You can either enter a new email (`other`), select a registered email from the drop-down menu, or choose `no email`. The email address you choose (new or registered) will become the selected email _for this call_. This email address will be recorded in the event log and will receive a confirmation of events that occurred during the call.

### End Call

To end a call, select the **end call** button in the upper right corner of any tab.
**Note**: If you don't deliberately end a call (with the **end call** button), after _<X<X>>_ hours the call automatically ends.

## Query Parameter Definitions

| Query Parameter | Definition |
|-|-|
| Client | Client's publication name. |
| Phone number | Subscription holder's phone number. |
| Email | Subscription holder's email. |
| House number | Delivery address house number. |
| Street | Delivery address street name. |
| Postal/ZIP code | Delivery address postal code. |
| Last name | Subscription holder's last name. |
| First name | Subscription holder's first name. |

See also: [create new account](example.com), [email address types](example.com)