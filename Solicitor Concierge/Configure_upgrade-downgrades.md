# Configure Upgrades and Downgrades

## Goal

The goal of this guide is to help you configure product upgrades and downgrades with Naviga. To configure your upgrades and downgrades, you must:

- complete and submit the Business Rules Document
- configure Solicitor Concierge

## Before you start

Make sure you meet the following pre-requisites before starting the tutorial steps:

- Have Subscribe version 3.13.
- Have NCS Circ 2018.5 or above.

## Part 1 - Complete the Business Rules Document

### Goal

The goal of Part 1 is to introduce you to the Business Rules Document. It defines the conditions for what upgrades and downgrades are presented to a subscriber. You will need to complete the document and return it to Naviga so we can implement your business rules into our databases.

### Create your business rules

A good way to format your rules is to use the following example:

`If NewspaperID = 4 and daily rate is between $0 and $0.12 AND base productID = 400002, offerGroupID = 368 and SegmentName = SaverPlus`

This translates to the following:

If the newspaper is Milroy Area Appeal (`NewspaperID = 4`) with a rate between `$0 and $0.12` and scheduled for a 7 Day Delivery(`productID = 400002`), then offer a Sunday Only Delivery (`offerGroupID = 368`) with a segment name of `SaverPlus`.

Use the following segment as a template, and replace your information:

`If NewspaperID = {X} and daily rate is between {$x.xx and $x.xx} AND base productID = {X}, offerGroupID = {X} and SegmentName = {SaverPlus}`

> [!Tip]
> You can create as many rules as you need to cover any type of scenario. The example here expounds only on the price dimension, but you will probably want to extend your rules to cover many other scenarios.

### Outcome

Congratulations! You have created your business rules. You must create business rules for all other scenarios. After you have created your rules, return them to your Naviga Implementation Manager.

## Part 2 - Configure the offers in Solicitor Concierge

### Goal

The goal of Part 2 is to configure your offers in Solicitor Concierge.

### Add rules to Solicitor Concierge

From the Solicitor Concierge dashboard:

1. Select **Offer Groups** from on the left and choose an offer from the right. 
2. Choose and offer from the right. If no offers currently exist, create a new one.
3. Select the **coding** section.  Details will appear to the right.
4. Choose **SmartOfferSegment** and check the smart offer box.
5. Select either **UPGRD** or **DNGRD** from the **smart offer type** drow-down menu.
6. Enter the segment name that you created in the Business Rules Document (e.g. `Basic`, `Plus`). The segment name can be applied to all divisions, including specific divisions.
7. Select **update** or **save as new**.

(STOP SAVER GIF)

### Outcome

Congratulations! You have added an upgrade and downgrade offers to the Solicitor Concierge. Now your offer will appear when you walk a customer through the Stop Saver feature of the **offers** tab.

## What You have learned

Congratulations! You have added an offer to the Solicitor Concierge. Now your offer will appear when you walk a customer through the Stop Saver feature of the **offers** tab. Be sure to add each Business Rule segment you've added to the Solicitor Concierge.