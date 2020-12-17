# Configure Subscription Purchases

## Goal

The goal of this tutorial is to show you how to configure some of the Subscription Purchases in the Solicitor Concierge and Content Management System (CMS) dashboards. This guide explores four types:

- ZIP-only/digital Subscription Purchase
- start-and-bill Subscription Purchase
- complimentary Subscription Purchase
- campaign code Subscription Purchase

Navigate to your desired Subscription Purchase type to learn more.

## Before you start

Make sure you meet the following pre-requisites before starting the tutorial steps:

- Have Subscribe version 3.13.
- Have NCS Circ 2018.5 or above.
- Reach out to a Naviga Implementation Manager to ensure Solicitor Concierge and CMS components are configured and structured properly.

## ZIP-only Subscription Purchase

A ZIP-only Subscription Purchase requires a subscriber to enter only a postal code (and not a complete address) while making a purchase.

### Goal

The goal of this section is to explain how to configure a ZIP-only Subscription Purchase in Naviga's Solicitor Concierge and CMS dashboards.

### Solicitor Concierge setup

From the Solicitor Concierge dashboard:

1. Select **offer groups** from the left sidebar. Your offer groups will appear in a list to the right.
2. Select an offer group from the list, or create a new offer group.
3. Select the **additional options** category, then select the **address requirements** drop-down menu.
4. Uncheck the _run product delivery check_, _billing address_, and _delivery address_ boxes.
5. Select **update** or **save as new**.

### CMS setup

From the CMS dashboard:

1. Select **subscription panel** then **presentations**.
2. Choose your desired presentation from the drop-down menu.
3. Add the **Independent Address V3** as a child component to the **Step V3** component.
4. Select **save**.

### Outcome

Congratulations! You've added a ZIP-only Subscription Purchase in the Solicitor Concierge and CMS dashboards.

## Start-and-bill Subscription Purchase

A start-and-bill Subscription Purchase allows the subscriber to begin a subscription and pay for it later via invoice. The subscriber is not required to provide payment information.  

### Goal

The goal of this section is to explain how to configure a start-and-bill Subscription Purchase in Naviga's Solicitor Concierge and CMS dashboards.

### Solicitor Concierge setup

From the Solicitor Concierge dashboard:

1. Select **offer groups** from the left sidebar. Your offer groups will appear in a list to the right.
2. Select an offer group from the list, or create a new offer group.
3. Select the **additional options** category, then select the **payment method** drop-down menu.
4. Check the _billed_ box.
5. Select **update** or **save as new**.

### CMS setup

From the CMS dashboard:

1. Select **subscription panel** then **presentations**.
2. Choose your desired presentation from the drop-down menu.
3. Add the **Bill Me V3** as a child component to the **Payment Method V3** component.
4. Select **save**.

### Outcome

Congratulations! You've added a start-and-bill Subscription Purchase in the Solicitor Concierge and CMS dashboards.

## Complimentary Subscription Purchase

A complimentary Subscription Purchase does not require the subscriber to provide payment information, and no payment is required. Instead, the payment method is marked as either `Paid Comp` or `UnPaid Comp` and has no rate code.

### Goal

The goal of this section is to explain how to configure a complimentary Subscription Purchase in Naviga's Solicitor Concierge and CMS dashboards.

### Solicitor Concierge setup

From the Solicitor Concierge dashboard:

1. Select **offer groups** from the left sidebar. Your offer groups will appear in a list to the right.
2. Select an offer group from the list, or create a new offer group.
3. Select the **additonal options** category, then select the **payment method** drop-down menu.
4. Check the _billed_ box.
5. Select the **coding** category, then select the **billing systems code** drop-down menu.
6. Designate the **billing method** as either `Paid Comp` or `UnPaid Comp`.
7. Select **update** or **save as new**.

### CMS setup

From the CMS dashboard:

1. Select **subscription panel** then **presentations**.
2. Choose your desired presentation from the drop-down menu.
3. Add the **Bill Me V3** as a child component to the **Payment Method V3** component.
4. Select **save**.

### Outcome

Congratulations! You've added a complimentary Subscription Purchase in the Solicitor Concierge and CMS dashboards.

## Campaign-code Subscription Purchase

A campaign-code Subscription Purchase minimizes the amount of data you need to enter. Instead of entering repeated data, a single campaign code sent to the circulation database will automatically understand the rate code, term, and length of a subscription.

### Goal

The goal of this section is to explain how to configure a campaign-code Subscription Purchase in Naviga's Solicitor Concierge and CMS dashboards.

### Solicitor Concierge setup

From the Solicitor Concierge dashboard:

1. Select **offer groups** from the left sidebar. Your offer groups will appear in a list to the right.
2. Select an offer group from the list, or create a new offer group.
3. Select the **coding** category, then select the **custom codes** drop-down menu.
4. Enter the NCS campaign code value in the **Campaign Code 1** field.
5. Select **update** or **save as new**.

### CMS setup

Configure a campaign code Subscription Purchase just as you would a regular Subscription Purchase.

### Outcome

Congratulations! You've added a campaign code Subscription Purchase in the Solicitor Concierge and CMS dashboards.

See also: [Configure activation fees for Subscription Purchases](example.com)