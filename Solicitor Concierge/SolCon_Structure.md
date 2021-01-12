# Solicitor Concierge User Guide (title)

## Welcome

Welcome to the Solicitor Concierge (SolCon) User Guide. SolCon is a flexible application designed to help you create Offer Groups, sell your Offer Groups, and manage the users who have access to them.

### Overview

An Offer Group is comprised of different inventory products. The different types of inventory products are available areas, sales products, marketing texts, and terms & conditions texts. First, you will create all of your inventory products. Next, you will create your Offer Groups. Last, you will create your users and teams, designating their access and permissions.

### SolCon diagram

The diagram below shows you how the different components of SolCon work together.
 (DIAGRAM)

> Tip: Your SolCon site automatically syncs with your Subscribe database and imports your Billing Products from the Subscriber Concierge database. A billing product is a combination of your divisions (individual publications) and your service types (delivery frequencies). Besides adding Available Areas, billing products cannot be edited. However, you can group them into sales products to incorporate them into an Offer Group.

### Guide structure

This guide will explore some key concepts to help you understand the SolCon application and guide you through common tasks. The guide contains three main sections, [quick start](example.com), [SolCon UI guide](example.com), and [tutorials](example.com).

The quick start provides the highest overview and instruction to get you going. Its aim is to show you how create your inventory products and first Offer Group quickly. It also acts as a good overview for how SolCon works.

The SolCon UI Guide explores how to navigate around the SolCon application. The application contains many features. Use this section to for high-level definitions and explanations.

The tutorials provide the most detail and information. They walk you through each step for each feature in SolCon.

## SolCon Quick Start

This quick start guides you through getting your first offer group up and running in SolCon. For detailed explorations of the features explored in this quick start, check out the [tutorials](example.com) section.

### Before you start

Make sure you meet the following pre-requisites before starting the tutorial steps:

* Reach out to Naviga Implementation Manager to ensure your SolCon site has been configured

### Get Started

### Step 1 - Configure an available area

By default, all of the US and CA postal codes will be included as deliverable areas. To narrow further:

1. Select **inventory**, then choose **available areas**.
2. Select **+ new** button.
3. Add the deliverable ZIP/Postal codes of your publication.
4. Name your **available area**, then select **save**.

### Step 2 - Configure your first product

1. Select **inventory**, then choose **products and bundles**.
2. From the **billing** tab, navigate to your product and select the pencil icon.
3. Add your newly created **available area** to the billing product. Select **save**.
4. Select the **sales** tab, then select the **+ new** button.
5. Name your new sales product, add your billing product, and add your newly created **available area**.
6. Select **save**.

### Step 3 - Configure your first terms and conditions

1. Select **inventory**, then choose **terms and conditions**.
2. Select the **+** button.
3. Create a name for your new terms and conditions option.
4. Write your terms and conditions in the body field.
5. Optionally, check the **set as default** box if applicable.
6. Select **save**.

### Step 4 - Configure your first marketing text

1. Select **inventory**, then choose **marketing text**.
2. Select the **+** button.
3. Create a name for your new marketing text option.
4. Fill in your desired text in the text fields.
5. Optionally, check the **set as default** box if applicable.
6. Select **save**.

### Step 5 - Optionally, configure your sales team

If your offer will be using `direct sales/Kiosk` or `Subscriber concierge admin`, follow this step. Otherwise, unselect these options from **Offer Groups -> Additional Options** setting and skip the rest of this step.

1. Select **teams**, then choose **sales team**.
2. Select the **+ new** button.
3. Enter a name for your sales team, then configure their privileges.
4. Select **save**.

### Step 6 - Configure your first offer group

1. Select **offer groups**.
2. Select the **+** button.
3. Name your offer group. Add your product, price, division, term & conditions, and marketing texts that you just configured.
4. Select **publish**

### What's next

Congratulations! You've just configured your first inventory products and Offer Group. Follow these sets of instructions for each product and/or Offer Group that you wish to create. For more detailed explorations of the SolCon features, check out the [tutorials] or [SolCon UI] sections.

<!-- PM Gets application set up, then PM makes sure sync is working, and division is set up.

PM would have to give client access in the admin button.menu

Start w/ inventory section. Inventory is anything and everything you'd need to set up an offer group. All the features in inventory, -->

## Find your way around SolCon UI

(ANNOTATED IMAGE)

### Solicitor Menu

**Offer groups**: You can create and manage your offer groups in this section. You can customize an offer group to your liking, however, recommended practice dictates that you organize your offer groups around delivery schedules. For example, _7 Day Delivery_, _Sunday Only_, _Monday, Wednesday, Friday_, _eEdition_ and so on. You can add divisions (individual publications) to an offer group and adjust their price(s) accordingly.

Organizing your offer groups in this way minimizes complexity and duplication. Instead of managing hundreds of different publications, each with its own product and delivery type, you will manage a few groups and customize them as needed.

**Offers**: This is a read-only section that allows you to quickly view your offers and divisions. The format of the offer's name is `offerGroupName - divisionName`.

**Promotions**: You can create and manage your promotions here. Promotions is a legacy concept, and a promotion is a group of Offer Groups.
<!-- (Replaced promotions w/ offer groups in new release. Promotions is basically legacy concept. ) -->

**Inventory**: This is a drop-down menu that allows you to manage everything related to your Offer Groups. You can create your sales products, marketing text, and T&C. You can also set up premiums and determine delivery areas.

**Teams**: Manage your sales teams here. Create a team, manage its members, and customize what offers each team can sell.

**Reference Tables**: This is read-only reference section that allows you to quickly view product data, such as codes, household levels, sales platforms, service types, and billing plans.

**Admin**: Add users and manage their access and permissions of the SolCon application here.

### Sync Features

**ClearCache**: Clearing your cache often resolves errors. It is important to clear your cache after you have made changes in the SolCon application.

**Sync**: Syncing the Subscribe database to your SolCon app also resolves errors. It is recommended you try these are first steps if you encounter an issue.

### Import/Export Features
Use these buttons to import and export data into SolCon. Data must be in JSON format.

### User Icon

Select the user icon to log out of the SolCon app.

## Tutorials

### Configure available areas

### Configure a sales product

### Configure marketing text

### Configure terms and conditions

### Configure offer groups

### Configure users, sales teams, and team members

### Configure an activation fee

## Common questions / find answers
