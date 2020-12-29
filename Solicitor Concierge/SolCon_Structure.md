# Solicitor Concierge User Guide (title)

## Welcome

Welcome to the Solicitor Concierge (SolCon) User Guide. SolCon is an application designed to help you manage your sales products. This guide will explore some key concepts to help you understand the SolCon application and guide you through common tasks.

Current version: 3.12 87408

Your SolCon site automatically syncs with your Subscribe database and sync your Billing Products This means that your divisions (individual publications) and Frequencies (Delivery Schedules)are already accessible in the SolCon site. You can use SolCon to manage your particular products, offer groups, communcations, and more.

## SolCon Quick Start

This quick start guides you through getting your first offer group up and running in SolCon. For detailed explorations of the features explored in this quick start, check out the [tutorials](example.com) section.

### Before you start

Make sure you meet the following pre-requisites before starting the tutorial steps:
* Reach out to Naviga Implementation Manager to ensure your Billing Products are configured in SolCon
* another??

### Get Started

### Step 1 - Configure your first available area

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

### Step 5 - Configure your first offer group

1. Select **offer groups**.
2. Select the **+** button.
3. Name your offer group. Add your product, price, division, term & conditions, and marketing texts that you just configured.
4. Select **publish**

### Step 6 - Optionally, configure your sales team

If your offer is using `direct sales/Kiosk` or `Subscriber concierge admin`, follow this step. Otherwise, unselect these options from the Offer Groups' setting and skip the rest of this step.

1. Select **teams**, then choose **sales team**.
2. Select the **+ new** button.
3. Enter a name for your sales team, then configure their privileges. 
4. Select **save**.

### What's next

Congratulations! You've just configured your first inventory product and offer group. Follow these sets of instructions for each product and/or offer group that you wish to create. For more detailed explorations of the SolCon features, check out the [tutorials] or [SolCon UI] sections.

<!-- PM Gets application set up, then PM makes sure sync is working, and division is set up.

PM would have to give client access in the admin button.menu

Start w/ inventory section. Inventory is anything and everything you'd need to set up an offer group. All the features in inventory, -->

## Find your way around SolCon UI

(ANNOTATED IMAGE)

You can access most of SolCon's functionality from the Solicitor Menu.

**Offer groups**: You can create and manage your offer groups in this section. You can customize an offer group to your liking, however, recommended practice dictates that you organize your offer groups around delivery type (selfnote: 'delivery type' isn't quite accurate here). For example, _7 Day Delivery_, _Sunday Only_, _Monday, Wednesday, Friday_, _eEdition_ and so on. You can add divisions (individual publications) to an offer group and adjust their price(s) accordingly.

Organizing your offer groups in this way minimizes complexity and duplication. Instead of managing hundreds of different publications, each with their own product and delivery type, you will manage a few groups, and customize them as needed.

**Offers**: This is a read-only section that allows you to quickly view your offers and divisions.

**Promotions**: You can create and manage your promotions here. Promotions is a legacy concept, and a promotion is a group of Offer Groups.
<!-- (Replaced promotions w/ offer groups in new release. Promotions is basically legacy concept. ) -->

**Inventory**: This is a drop-down menu that allows you to manage everything related to your inventory. Create your sales products, bundles, marketing text, and T&C. You can also set up premiums and determine delivery areas.

**Teams**: Manage your sales teams here. Create a team, manage it's members, and customize what offers each team can sell.

**Reference Tables**: This is a read-only reference section that allows you to quickly view product data.

**Admin**: Add users and manage their registration to the SolCon application here.

**Sync Features**:

Clearing your cache often resolves errors. It is important to clear your cache after you have made changes in the SolCon application.

Syncing your SolCon app to the Subscribe database also resolves errors. It is recommended you try these are first steps if you encounter an issue.

**Import/Export Features**: Use these buttons to import and export data into SolCon. Data must be in {{X}} format.

**User Icon**: Select the user icon to log out of the SolCon app.

## Tutorials

### Configure available areas

#### Goal

The goal of this is to show you how an **Available Area** (AA) works in SolCon. An **AA** is an area that a division can be delivered to.
SolCon comes with all of the US and Canada postal codes pre-configured, but you might want to limit or expand your delivery range to a different **AA**.

#### Before you start

Make sure you meet the following pre-requisites before starting the tutorial steps:

* Reach out to your Naviga Implementation Manager to get your SolCon application up and running

#### Manage your AAs

In this section, you will learn how to create a new **AA** and delete or edit an existing **AA**.

Create an AA:

1. Select the **inventory** menu in the SolCon dashboard, then choose **Available Areas**. Any existing or pre-configured **AAs** will display.
2. Select the **+ New** button. The creation screen will appear.
3. Choose a name for your **AA**, then add your desired postal codes.

Add a postal code:

1. Select the circular **+** button in the **ZIP/Postal Codes** section. A search feature will appear.
2. In the following order, choose a country, state, and if applicable, county and city. You can limit your **AA** to a single postal code or an entire city or state's postal codes.
3. Add individual postal codes by either dragging or double-clicking them or add your entire search query with the **add all** button. Once a postal code has been added to your **AA**, you can explore them with the expand arrow.
4. Select the **active** box, then select **save**.

Congratulations, you've created a unique **AA**. To use this **AA**, you will need to add it to your billing product, the subject of the next section in this guide.

Delete or edit an existing **AA**:

1. Select the **inventory** menu in the SolCon dashboard, then choose **Available Areas**. Any existing or pre-configured **AAs** will display.
2. Navigate to the desired **AA** and select the pencil icon to edit **OR** the trash can icon to delete. If editing, the creation screen will appear. If deleting, confirm your choice and select **delete**.

#### Add your new AA to your billing product

In this step, you will learn how to add your new **AA** to your existing billing product. Your billing products will have been configured by Naviga to include the pre-configured US and Canada postal codes, but you will need to manually add any new **AAs** you create.

Add an **AA** to a billing product:

1. Select the **inventory** menu in the SolCon dashboard, then choose **Products & Bundles**. Any existing or pre-configured billing products will display.
2. Navigate to your desired billing product and select the pencil icon.
3. Select the **available areas** window to highlight it. Any **AAs** you have created will appear to the right.
4. Drag or double-click the **AA** you wish to add.
5. Select **save**.

Congratulations! You've added your newly created **AA** to your billing product. 

#### What you've learned

To review, you've learned to create or update **AAs**, which are designated deliverable postal codes, and you've learned to add the **AAs** that you've created to your billing products, which in effect _activates_ them.

### Configure a sales product

### Configure marketing text

### Configure terms and conditions

### Configure offer groups

### Configure your sales team

### Configure an activation fee



## Common questions / find answers

Just have any common questions people have...

