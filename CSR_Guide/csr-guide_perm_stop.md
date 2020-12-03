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
2. Select the **change** button next to the corresponding permant stop.
3. Update the **stop type**, **stop date**, and **reason**. The **stop date** can updated only when you choose a **stop type** value of `Specific Date`.
4. Select **submit**. The update is processed in real-time with the circulation system.

See also: [temporary stop](example.com), [vacation delivery](example.com), [restart a subscription](example.com)

> [!NOTE]
> The information displayed in this tab returns in real-time from our circulation databases.
> You must have NCS Circ `2018.5` or greater for current integration.

<br><br><br><br><br><br><br><br><br><br>