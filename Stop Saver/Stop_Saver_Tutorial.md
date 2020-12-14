# Setup Stop Saver

## Goal

The goal of this guide is help you configure the **Stop Saver** feature in the CSR Portal. **Stop Saver** is a tool that helps reduce subscription cancellations by offering subscribers **Smart Offers**. These are alternative offers that you present to subscribers when they attempt to cancel their subscription.

To configure **Stop Saver**, you must:

- complete and submit the Benefits Document
- complete and submit the Business Rules Document
- configure Solicitor Concierge

## Before you start

Make sure you meet the following pre-requisites before starting the tutorial steps:

- Possess a general understanding of Stop Saver. The goal above is a good orientation.
- Have access to NCS Circ 2018.5 or greater

## Part 1 - Complete the Benefits Document

### Goal

The goal of Part 1 is to introduce you to the Benefits Document.
This document details your dialogue preferences for the **Stop Saver** feature.
You will need to complete the document and return it to Naviga so that Naviga can integrate your dialogue preferences into our databases.

We provide you with an [example]() that you can customize to your liking. Please refer to this example as you work through Part 1 of this tutorial.

Part 1 will walk you through a single scenario.
After you learn how to format the Benefits Document for a single scenario, you will need to complete the document for any other scenarios your business might encounter.
After you complete your first scenario, the other scenarios should come easily.

### Choose a Stop Saver reason

**Stop Saver Reasons** are the UI options that describe why a subscriber may want to end their subscription.
In this scenario, we will use the common reason `Too Expensive`.

Add this reason to the **Stop Saver Reasons** column in the Benefits Document.

### Choose a Benefit Section dialogue

A **Benefit Section** dialogue is what you wish to respond with after hearing about a particular reason.
In the case of `Too Expensive`, we will respond with:

```I understand your money is tight. We have special offers for you at a lower price.```

Add this dialogue to the **Benefit Section** column in the Benefits Document. It must be in the same row of the corresponding reason.

### Choose a Stop Saver Smart Offer dialogue

The **Stop Saver Smart Offer** dialogue introduces your alternatives offers.

In this scenario, we will use:

```Let me see what I can do to keep you as a subscriber. Here's what I can offer you:```

Add this dialogue to the **Stop Saver Smart Offer** column in the Benefits Document. It must be in the same row of the corresponding reason.

### Choose a Stop Subscription dialogue

The **Stop Subscription** dialogue appears if a subscriber chooses to cancel their subscription anyway.

In our scenario, we will respond with:

```I've taken care of your request. Should you change your mind, please be sure to call us or go online and see what specials we have for you.```

Add this dialogue to the **Stop Subscription** column in the Benefits Document. It must be in the same row of the corresponding reason.

(Image of a Row)

### Outcome

Congratulations! You have created your dialogue options for your first scenario. You must complete the document all other potential scenarios. Again, refer to the [example]() to get started, or use this [template]() for a fresh start. Don't forget to return it to your Naviga Product Manager for implementation.

> [!Warning]
> Some reasons will not prompt the **Stop Saver** feature.
> Typically, these are reasons where a subscriber cannot continue, for example `Deceased` or `Returned Mail`. Customize these responses on Sheet 2 of the Benefits Document.

## Part 2 - Complete the Business Rules Document

### Goal

The goal of Part 2 is to introduce you to the Business Rules Document. It defines the conditions for when Stop Saver Offers are presented to a subscriber. You will need to complete the document and return it to Naviga so we can implement your business rules into our databases.

We provide you with an [example]() that you can customize to your liking. Please refer to this example as you work through Part 2 of this tutorial.

### Create your business rules

A good way to format your rules is to use the following example:

`If NewspaperID = 4 and daily rate is between $0 and $0.12 AND base productID = 400002, StopSaverID = 368 and SegmentName = SaverPlus`

This translates to the following:

If the newspaper is Milroy Area Appeal (`NewspaperID = 4`) with a rate between `$0 and $0.12` and scheduled for a 7 Day Delivery(`productID = 400002`), then offer a Sunday Only Delivery (`StopSaverID = 368`) with a segment name of `SaverPlus`.

Use the following segment as a template, replacing with your information:

`If NewspaperID = {X} and daily rate is between {$x.xx and $x.xx} AND base productID = {X}, StopSaverID = {X} and SegmentName = {SaverPlus}`

You can create as many rules as you need. It is not uncommon to have many rules or to add more parameters.

### Outcome

Congratulations! You have created your business rules. You must create business rules for all other scenarios. Again, refer to the [example](example.com) to get started, or use this [template](example.com) for a fresh start. Don't forget to return it to your Naviga Product Manager for implementation.

## Part 3 - Setup the offers in Solicitor Concierge

### Goal

The goal of Part 3 is to setup your offers in the Solictor Concierge.

### Add rules to Solicitor Concierge

From the Solicitor Concierge dashboard:

1. Select **Offer Groups** from on the left and choose an offer from the right. 
2. Choose and offer from the right. If no offers currently exist, create a new one.
3. Select the **coding** section.  Details will appear to the right.
4. Choose **SmartOfferSegment** and check the box. 
5. Select **StopSaver** from the **smart offer type** drow-down menu.
6. Enter the segment name that you created in the Business Rules Document (e.g. `SaverPlus`). The segment name can be applied to all divisions, including specific divisions.
7. Select **update** or **save as new**.

(STOP SAVER GIF)

### Outcome

Congratulations! You have added an offer to the Solicitor Concierge. Now your offer will appear when you walk a customer through the Stop Saver feature of the **complaints** tab.

## What You have learned

Congratulations! You have added an offer to the Solicitor Concierge. Now your offer will appear when you walk a customer through the Stop Saver feature of the **complaints** tab. Be sure to add each Business Rule segment you've added to the Solicitor Concierge.