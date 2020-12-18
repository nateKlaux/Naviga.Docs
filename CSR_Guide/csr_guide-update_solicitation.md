## Manage Solicitation Preferences

You can manage a subscriber's solicitation preference in the **account information** tab. From this tab, you can:

- add a subscriber to a do not call, email, or TMC list
- edit a subscriber's solicitation preference
- delete a subscriber's solicitation preference

### Navigation

To view the **account information** tab, perform a [subscription search](www.example.com), and then select the **account information** tab. Select the **account update** button to display a subscription's solicitation preferences.
(GIF OF PROCESS)

### Add a new solicitation preferences

After selecting the **account update** button:

1. Select a **type**, then select **add new**.
2. Select a **category** to change the solicitation preference. `TMC` refers to telemarketing.
3. Choose a **stop date**. (Optionally, choose a **resume date**. If left blank, the subscriber is added to the list indefinitely.)
4. If desired, leave a remark in the text field (100 characters). Select **submit**. The request is processed in real-time with the circulation system. The subscriber's solicitation preference is removed, but a record remains in the **account update** grid as an audit trail.

### Change a solicitation preference

After selecting the **account update** button:

1. Select the **edit** button next to the corresponding solicitation preference.
2. Change any of the following: **stop date**, **resume date**, **remarks**. If the preference has already begun, only **resume date** is editable.
3. Select **save**. The request is processed in real-time with the circulation system.

> [!Note]
> A solicitation preference's category (`do not call`, `do not email`, `do not TMC`) cannot be changed with the **edit** button. To change a category, delete the solicitation preference and add a new preference with the desired category.

### Delete a solicitation preference

After selecting the **account update** button:

1. Select the **remove** button next to the corresponding solicitation preference.
2. Confirm you wish to delete the preference and select **OK**. The request is processed in real-time with the circulation system, and the preference is removed from the **account update** grid.


### Account update grid

The **accounted update** grid displays all of a subscription's solicitation preferences. 

| Term | Description |
|-|-|
| Solicitation code | The code that corresponds to the solicitation preference's category (e.g. `NoEMail`, `NoCall`, `NoTMC`). These codes are configurable in the circulation database. |
| Stop date | The date when the solicitation preference begins (`MM-DD-YYYY`). |
| Resume date | The date when the solicitation preference ends (`MM-DD-YYYY`). Note:This field is optional. A solicitation preference can continue indefinitely. |
| Remarks | Any comments a CSR or subscriber left. |
| Change date | The date when the solicitation preference was created (`MM-DD-YYYY`). |

> [!NOTE]
> The information displayed in this tab returns in real-time from our circulation databases.
> You must have NCS Circ `2018.5` or greater for current integration.