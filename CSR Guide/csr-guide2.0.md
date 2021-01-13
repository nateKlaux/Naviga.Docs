# CSR User Guide

Welcome to the *Customer Service Representative (CSR) User Guide*! This guide will walk you through all the functions of the subscription information panel (**CSR Panel**) in the SubCon Admin Portal.

> [!TIP]
> If you are looking for something in particular, try out our search function in the upper right corner. Otherwise, check out the guide's table of contents to the left.

> [!TIP]
> If you are looking for something in particular, try out our search function in the top right corner. Otherwise, check out the guide’s table of contents to the left.

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

## Delivery Issues and Delivery Management

This guide explores the **complaints** tab, which displays information about delivery management and delivery issues. From this tab, you can:

- view a subscription's complaint history
- create a new complaint
- relay messages to carriers and district managers

This guide also contains instructions for creating new complaints and adding delivery messages.

### Navigation

To view the **complaints** tab, perform a [subscription search](www.example.com), and then select the **complaints** tab.

(GIF OF PROCESS)

## Record and Process Delivery Issues

The **add new delivery error** feature allows you to process subscriber complaints. It displays product information and a redelivery window. The displayed information integrates in real-time with the client's circulation system.

(SCREEN W/ ANNOTATIONS OF REDELIVERY WINDOW AND SOLUTION)

This feature is highly configurable and clients define their own rules.
This [workflow](example.com) can help determine when to record and process complaints.

### Helpful Information

Here are some helpful pointers for recording and processing complaints.

- Subscribers cannot make complaints before the redelivery window on the same day. They can inside or after the redelivery window.
- Subscriber's cannot make complaints during vacation days.

### Record a complaint

To record a complaint:

1. Select the **calendar icon** and choose a complaint date.
The client determines the number of days back, as well as the number of complaints you can select.
2. Select an **error type** that corresponds with the subscriber's complaint.
Use your best judgment to match the subscriber's issue with an error from the drop-down field.
3. Choose a **resolution** for the subscriber that corresponds to the workflow and client's rules.
To choose `Redelivery`, the complaint must *not* have been made before the redelivery window.
4. Read the disclaimer text to the subscriber and check the `Disclaimer read` box.
5. Select **save**. If successful, the record will appear in the **complaints** box.

(GIF OF PROCESS)

### Subscription Complaint History

The **complaints** table at the top of the page displays a history of subscription complaints.  The table displays the following categories: `Transaction ID`, `Incident date`, `Complaint description`, `Complaint option`, `Credit value`, and `Escalated`. Any new complaints will appear here.

An escalation status of `yes` occurs when a certain number of complaints are created within a certain amount of days. Both the number of complaints and the number of days is client configurable.  

## Add Delivery Messages and Instructions

This feature allows you to create customized, real-time messages for carriers and district managers. You can create:

- one-off notes for special instructions for carriers and district managers
- permanent, placement delivery instructions
- general delivery instructions

> [!Note] The message/instruction is added into the circulation system in real-time. It may take up to 24 hours to reflect the added message on the screen

### Carrier and District Manager Messages

Message types are configurable and add context to the message (e.g. a message concerning the `route` or `ZIP code`).
The maximum message length is 140 characters.

To create a carrier or district manager message:

1. Select the **add new** button under the `Carrier & district manager messages` section.
2. Chose a message `type` from the drop-down menu.
3. Enter a message in the text box.
4. Select **save**.
5. Confirm your message and select **OK**.

(GIF)

### Permanent Delivery Messages

This feature creates permanent, placement instructions (e.g. `door delivery` or `double bag when wet`). Only _one_ permanent message is allowed per account, and the message options are predetermined.

To create a permanent delivery message:

1. Select the **add new** button within the `Permanent delivery messages` grid.
2. Choose a date and message from the drop-down menu.
3. Select **save**.
4. Confirm your message and select **OK**.
(GIF)

### Delivery Instructions and Directions

These are editable text boxes that you can use to create general carrier notes (e.g. "Corner of Melrose and 1st St" or "backhouse").
The maximum message length is 140 characters.

To create new instructions or directions:

1. Select the **add new** or **edit** button.
2. Enter your message.
3. Select **save**.

You can have one instruction and one direction.
The messages will remain until you edit or delete it.

(GIF)

> [!NOTE]
> The information displayed in this tab returns in real-time from our circulation databases.
> You must have NCS Circ `2018.5` or greater for current integration.

## Vacation Transfer

This feature allows you to temporarily change a print subscription's delivery address.

Transfers cannot overlap with other stops. You can edit or cancel existing transfers in the **scheduled stops/starts** grid.

### Navigation

You can find this feature under the **stop tab**. To navigate here, perform a [subscription search](www.subsearch.com), and then select the **stop** tab.

(GIF OF PROCESS)

### Helpful Information

Here are some helpful pointers when creating or updating vacation transfers.

- Transfers must comply with the **vacation cut-off times** table.
    > For example, `Sun for Mon | 07:00 PM Sun` translates to `For a Monday transfer, the cutoff must occur by 7:00 PM Sunday`.
- If the temporary delivery address is within a delivery route, a carrier will deliver the subscription per usual. Otherwise, the subscription will ship via mail and may lead to a later delivery.
- This [workflow](example.com) can help determine how and when to process vacation transfers.

### Create a vacation transfer

To create a vacation transfer:

1. Select **vacation transfer**. The **add new vacation transfer** feature appears.
2. Choose a **stop date** and **resume date**. Adhere to the **vacation cut-off times** table.
3. Enter a temporary delivery address into the corresponding fields.
4. Select a **transfer reason**.
5. Confirm the disclaimer text to the subscriber and select **submit**. You will see the scheduled transfer in the **scheduled stops/starts** grid. The vacation transfer is processed in real-time with the circulation system.

### Update or cancel a vacation transfer

If a vacation transfer has already been created, you can only update the dates (and not the address). To update the address, cancel the initial vacation transfer and start anew.

To cancel a vacation transfer:

1. Navigate to the **scheduled stops/starts** grid.
2. Select the **cancel** button next to the corresponding vacation transfer.
3. Confirm you want to delete the record and select **OK**. The cancellation is processed in real-time with the circulation system.

To update a temporary stop:

1. Navigate to the **scheduled stops/starts** grid.
2. Select the **change** button next to the corresponding vacation transfer. The **change vacation transfer** function appears.
3. Choose the updated dates for the vacation transfer, being sure to adhere to the **vacation cut-off times** chart.
4. Select **submit**. The update is processed in real-time with the circulation system.

(GIF OF PROCESS)

See also: [permanent stop](example.com), [temporary stop](example.com)

> [!NOTE]
> The information displayed in this tab returns in real-time from our circulation databases.
> You must have NCS Circ `2018.5` or greater for current integration.

## Temporary Stop

This feature allows you to pause a print delivery. It functions as a temporary hold of a subscription.

Temporary stops cannot overlap with other stops or transfers. You can edit or cancel existing temporary stops in the **scheduled stops/starts** grid. 

### Navigation

You can find this feature under the **stop tab**. To navigate here, perform a [subscription search](www.subsearch.com), and then select the **stop** tab.

(GIF OF PROCESS)

### Helpful Information

Here are some helpful pointers when creating or updating temporary stops.

- Temporary stops must comply with the **vacation cut-off times** table.
For example:
    > `Sun for Mon | 07:00 PM Sun` translates to `For a Monday stop, the cutoff must occur by 7:00 PM Sunday`.
- **Reason**, **hold**, and **donation options** come in real-time from a circulation database.
- Some common **hold options** are `VacPack`, `credit`, and `donation`. `VacPack` refers to a vacation package where the subscription will be delivered after the vacation. Sometimes `donation` allows the subscriber to specify *where* a donation goes. `Credit` extends the subscription's expiry date in accordance with the number of paused days.
- This [workflow](example.com) can help determine how and when to process temporary stops.

### Create a Temporary Stop

To create a temporary stop:

1. Select **temporary stop**. The **add new temporary stop** feature appears.
2. Choose a **stop date** and **resume date**. Adhere to the **vacation cut-off times** table.
3. Choose a **reason** from the drop-down menu.
4. Select a **hold option**.
5. Confirm the disclaimer text to the subscriber and select **submit**. The temporary stop is processed in real-time with the circulation system.

(GIF OF PROCESS)

### Update or Cancel a Temporary Stop

If a temporary stop has already been created, you can only edit the end date (and not the start date). To edit the start date, cancel the temporary stop, and start anew.

To cancel a temporary stop:

1. Navigate to the **scheduled stops/starts** grid.
2. Select the **cancel** button next to the corresponding temporary stop.
3. Confirm you want to delete the record and select **OK**. The cancellation is processed in real-time with the circulation system.

To update a temporary stop:

1. Navigate to the **scheduled stops/starts** grid.
2. Select the **change** button next to the corresponding temporary stop. The **change a temporary stop** function appears
3. Choose the updated dates for the temporary stop, being sure to adhere to the **vacation cut-off times** chart.
4. Select **submit**. The update is processed in real-time with the circulation system.

See also: [permanent stop](example.com), [vacation transfer](example.com)


> [!NOTE]
> The information displayed in this tab returns in real-time from our circulation databases.
> You must have NCS Circ `2018.5` or greater for current integration.

## Permanent Stop

This feature allows you to permanently stop a subscription.

Permanent stops cannot overlap with other stops or transfers. You can update or cancel scheduled permanent stops in the **scheduled stops/starts** grid.

### Navigation

You can find this feature under the **stop tab**. To navigate here, perform a [subscription search](www.subsearch.com), and then select the **stop** tab.

(GIF OF PROCESS)

### Helpful Information

Here are some helpful pointers when creating or updating permanent stops.

- When creating a permanent stop, you will work through the **stop saver** workflow with the subscriber. **Stop saver** includes three steps (`1. Benefit Section`, `2. Stop Saver Offer`, `3. Stop Subscription`). These steps help stop a cancellation. **Stop Saver** is configurable in the Subscribe database. Clients must follow submit a **Stop Saver Rules** document that details their preferences.
- **Note**: the **stop saver** feature will not appear for some reason types (e.g. `deceased`, `office use only`, etc.) These options are configurable in the Subscribe database.
- **Reason options** come in real-time from a circulation database.
- This [workflow](example.com) can help determine how and when to process permanent stops.

### Create a Permanent Stop

To create a permanent stop:

1. Select the **permanent stop** button.
2. Choose a cancellation **reason** from the drop-down list.
3. Read the **benefits section** to the subscriber. If the subscriber agrees to the suggested solution, select **helpful: yes** and stop this procedure. Otherwise, select **helpful: no** and continue to the next step.
4. Present the offer(s) to the subscriber. If the subscriber agrees to an offer, select **helpful: yes** and stop this procedure. Otherwise, select **helpful: no** and continue to the next step. If a subscriber agrees to an offer (typically a downgrade), the updated offer is processed in real-time with the circulation system.
5. Read the displayed message to the subscriber and choose when to stop the subscription. If scheduling for a future date, select a date.
6. Confirm the disclaimer text to the subscriber and select **submit**. The permanent stop is processed in real-time with the circulation system.

### Cancel a Permanent Stop

You can only cancel permanent stops with `stop types` values of `NextBillingCycle` or `Specific Date`. If the **stop types** value is `Immediate`, the permanent stop cannot be canceled.

To cancel a permanent stop:

1. Navigate to the **scheduled stops/starts** grid.
2. Select the **cancel** button next to the corresponding permanent stop.
3. Confirm you want to delete the record and select **OK**. The cancellation is processed in real-time with the circulation system.

### Update a Permanent Stop

You can only update permanent stops with `stop types` values of `NextBillingCycle` or `Specific Date`. If the **stop types** value is `Immediate`, the permanent stop cannot be updated.

To update a permanent stop:

1. Navigate to the **scheduled stops/starts** grid.
2. Select the **change** button next to the corresponding permanent stop.
3. Update the **stop type**, **stop date**, and **reason**. The **stop date** can updated only when you choose a **stop type** value of `Specific Date`.
4. Select **submit**. The update is processed in real-time with the circulation system.

See also: [temporary stop](example.com), [vacation delivery](example.com), [restart a subscription](example.com)

> [!NOTE]
> The information displayed in this tab returns in real-time from our circulation databases.
> You must have NCS Circ `2018.5` or greater for current integration.