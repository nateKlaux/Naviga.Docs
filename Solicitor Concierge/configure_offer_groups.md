### Configure offer groups

#### Goal and overview

The goal of this guide is to show you how **Offer Groups** work, as well as how to configure them in SolCon.

Each component of an Offer Group can be applied everywhere (`to all`) or be limited by either price plan (`use for price plan`) or individual divisions (`select division`). This gives you flexibility with how you apply your components.

Use the **exceptions** button to exclude particular divisions. Alternatively, limit by division and choose the specified division from the drop-down menu.

> **Best practice note**: We suggest creating Offer Groups as collections of Sales Products and divisions (publications). Creating them in this way allows you to still add unique prices, but minimizes the amount of duplication.

This guide is a mix of tutorial and description. Use the headings to explore features at length.

#### Before you start

Make sure you meet the following pre-requisites before starting the tutorial steps:

* Create your inventory items (available areas, sales products, marketing text, and terms and conditions)

#### Create an Offer Group

In this section, you will learn how to create/edit/delete an Offer Group. The guide divides the steps into smaller, manageable chunks.

**Offer Group basics**:

1. Select the **Offer Groups** menu in the SolCon dashboard. Any existing Offer Groups will display on the right.
2. Select the **+** button. The creation screen will appear.
3. Choose a name for your Offer Group.
4. Select **save draft** if continuing. Otherwise, select **publish**.

**Products and divisions**:

1. Select the **products** box. Your sales products will appear to the right. Double-click or drag all corresponding sales products (e.g. `7 Day Delivery`, `Sunday Only`, or `Friday Only`).
2. Select the **divisions** box. Your divisions will appear to the right. Double-click or drag all corresponding divisions (e.g. publication's name).
3. Select the **price** box. The price creation screen will appear to the right. Enter a price for the Sales Product+Division combination. **NOTE**: To price divisions differently, select the **+** tab directly to the right of the **price** box. This creates a separate tab for a new division/set of divisions. Add a division, then adjust it's price accordingly.
4. Select **save draft** if continuing. Otherwise, select **publish**.

(Screen of price button)

**Marketplace**: Use this feature to determine the domain/URL on sales platforms where the offer will be sold. A default selection will use the division's default domain. You can add multiple URLs if you wish.

1. Select the **marketplace** box. Your maketplace options will appear to the right.
2. Choose how you wish to apply your sales platform (for `all`, by `price plan`, or by `division`).
3. Select a sales platform from the drop-down menu.
4. Double-click or drag your desired sales platform to add to the Offer Group.
5. Select **save draft** if continuing. Otherwise, select **publish**.

> Note: you can also adjust the sales platform from the **additional options** box.

**Terms and conditions**: use this feature to add the a T&C template to your Offer Group.

1. Select the **terms & conditions** box. Your T&C options will appear to the right.
2. Choose how you wish to apply your T&C (for `all`, by `price plan`, or by `division`).
3. From the drop-down menu, select the sales platform you wish to apply your T&C to.
4. Double-click or drag your desired T&C to add it to the Offer Group.
5. Select **save draft** if continuing. Otherwise, select **publish**.

>Note: You can edit and create new [T&C templates](example.com) from the **terms & conditions** box. To do this, select **unlink**, make your changes, then select **save as new**.

**Marketing text**: use this feature to add a Marketing Text template to your Offer Group.

1. Select the **marketing text** box. Your marketing text options will appear to the right.
2. Choose how you wish to apply your marketing text template (for `all`, by `price plan`' or by `division`).
3. Double-click or drag your desired marketing text to add it to the Offer Group.
4. Select **save draft** if continuing. Otherwise, select **publish**.

> Note: You can edit and create new [Marketing Text templates](example.com) from the **marketing text** box. To do this, select **unlink**, make your changes, then select **save as new**.

**Related offers**: use this feature to add related Offer Groups as upsell options to this Offer Group (e.g. the addition of a digital subscription to a Sunday Only subscription).

1. Select the **related offers** box. The related offers screen will appear to the right.
2. Choose how you wish to apply your related offers (for `all`, by `price plan`, or by `division`).
3. Select the **upsell** box. Your related Offer Groups will appear to the right.
4. Double-click or drag your desired related Offer Groups to add to your current Offer Group.
5. Select **save draft** if continuing. Otherwise, select **publish**.

> Warning!: The Upsell V3 component must be added to the presentation in the CMS for this feature to work properly.

**Premiums**: use this feature to add premiums to your Offer Group. Premiums are individual additions to a Sales Product, like a free mug or $5 gift card.

1. Select the **premiums** box. The premiums screen will appear to the right.
2. Choose how you wish to apply the premiums (for `all`, by `price plan`, or by `division`).
3. Select the **add premiums** box. Your premiums options will appear to the right.
4. Double-click or drag your desired premium to add to your Offer Group.
5. Select **save draft** if continuing. Otherwise, select **publish**.

**Coding**: use this feature to add, manage, or define unique codes that support your Offer Group.

1. Select the **coding** box. The coding options screen will appear to the right.
2. Choose the code type you wish to add (i.e. `house hold levels`, `smart offer segments`, `multi-use codes`, `custom codes`, or `billing system codes`). The tables below define the coding options.
3. Select **save draft** if continuing. Otherwise, select **publish**.

_House hold levels_ is a means by which you can define entitlement levels (e.g. `1` typically refers to full access an `99` to no access.) You can apply house hold levels to either all or individual divisions.

_Smart offer segments_ determines if your Offer Group will be used as a Smart Offer. Check out the [Stop Saver tutorial](example.com) for detailed exploration. You can apply the Smart Offer segment to either all or individual divisions.

_Multi-use codes_ determines whether a customer coupon-code can be used to access kind of special offer. These offers can be unlocked on either the Subscription Panel or in the CSR portal. On CSR portal there's a code field.

(SCREEN)

*One-time use codes* determines whether a single-use coupon code can be used to access a special offer.

To create a code, select **one time use codes** and create your code's group in the *code groups created field. Name your code, determine it's length, and the amount of codes desired. Select **generate codes**. You can only add codes, and the difference between the number of preexisting codes and codes desired will generate. These codes exist only in the Subscribe database and will not be passed to a circulation database. View the Reference Guide for information about managing them.

_Custom codes_ refer to circulation dependent codes. The table below shows NCS Circ example codes. You can apply these codes to either all or individual divisions.

| Custom codes | Definition |
|-|-|
| Prm Sub Src | Subscription sub source from NCS Circ (optional). |
| Source | Source code from NCS Circ. |
| Campaign code 1 | Campaign code from NCS Circ (optional). |
| Codes 4-10 | Placeholders for additional functionality. |

_Billing system codes_ refers to codes associated with the circulation system. You can apply these codes to either all or individual divisions. For systems using NCS Circ 2018.5 or greater, choose a rate code first. Doing so will trigger a real-time call to the circulation system and populate your fields. If more than one option exists, a drop-down menu with the appropriate options appears. Choose an option.

The following table is an example from NCS Circ. Other circulation systems can be configured differently.

| Billing System Codes | Definition |
|-|-|
| Rate code | The Offer Group's NCS Circ rate code. |
| Bill period | The billing type used (e.g. `CCAuto` or `BankAuto`) |
| Reason code | NCS Circ's reason code associated with the rate code. |
| Term | The billing term type (e.g. `weeks` or `months`). |
| Billing Method | The billing method used (e.g. `Office Pay`). |
| Term length | Associated with the Term: `1` for monthly term or `13`/`26`/`52` for weekly term. |
| Delivery method | The method of delivery. Either `Route` for print offers, or `Online` for Digital Only offers. |
| Tags 2-5 | Placeholders for additional functionality.  |

**Additional options**: use this feature for miscellany such as address validation rules, and active subscription check, and payment methods.. The table below defines each section's use.

| Additional options | Usage |
|-|-|
| Sales platform | Use this section to determine where the Offer Group will be sold. |
| Validity date | Use this section to select a start and end date for the Offer Group. |
| Offer Group code | Use this section to create a unique code to identify your Offer Group. This code can be referenced as a URL parameter direct customer to your Offer Group. |
| Term | Use this section to define the Offer Group's type of term and term length. Subscriber's will see this in their UI panel. |
| Pass or trial | Use this section to determine if the Offer Group is either a Free or Trial subscription. |
| Payment method | Use this section to determine the Offer Group's valid payment methods. Check all that apply. **Note**: These payment methods will apply to _all_ divisions. |
| Address requirements | Use this section to determine which address type will be required of a subscriber.  `Billing address` will require a billing address. `Delivery address` will require a delivery address. `Run product delivery check` will validate the postal code against the default available area configured in the Subscribe database. |
| Subscription validation | Use this section to determine other required validations for your Offer Group. `No existing subscription at address` would require the address to not be used for ane existing subscription. `No existing subscription stopped recently` would require that the subscription wasn't stopped within {X} amount of days, with the amount of days configurable in MG2Control. `No outstanding balance` would require the subscription to not have an outstanding balance. |
| EZPay | Use this section to determine if your Offer Group accepts/requires EZPay (automatic payment renewal).**Note**: This section will apply to _all_ divisions. `EZPay required` will require auto-renew. `EZPay optional` will allow auto-renew to be optional. `No EZPay` will disallow auto-renewal as a feature. |
| Tags | Use this section to add search tags to your Offer Group. |
| Old PID | Legacy promotion id. |

#### What you've learned

Congratulations! You've created an Offer Group! To review, you've learned how to create an Offer Group, as well as explored all of the functionality of the Offer Groups menu.
