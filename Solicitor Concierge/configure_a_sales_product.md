### Configure a sales product

#### Overview and goal

The goal of this guide is to show you how Sales Products (SPs) and Billing Products (BPs) work in SolCon. One difference between SPs and BPs is that Naviga preconfigures your BPs whereas you create your SPs.

BPs are a combination of divisions (publications) and their service types (delivery frequencies). SPs are a way to "group" similar BPs so that you can use them in your Offer Groups.

> **Note**: Best practice dictates that you create SPs to reflect _divisions that have similar service types_. Creating SPs in this way will greatly simplify managing your Offer Groups.

> For example, you may want to create a Sunday Only SP. This SP would be a single entity that includes _every_ division that has a Sunday Only BP.

> You could also create a Digital Only SP, which would include every division that has a Digital Only BP.

> Creating SPs in this way helps you organize your SolCon dashboard and removes complexity and duplication.

#### Before you start

Make sure you meet the following pre-requisites before starting the tutorial steps:

* Have at least one billing product with an assigned Available Area.

#### Create a Sales Product

In this section, you will learn how to create an SP. The first procedure will guide you through the mandatory steps. The latter procedures explore optional configurations.

Create an SP:

1. Select the **inventory**  menu in the SolCon dashboard, then choose **Products & Bundles**. Your BPs will display.
2. Select the **sales** tab. If you have created any SPs, they will display here.
3. Select the **+ new** button. A creation window will appear.
4. Name your SP, e.g. `Sunday Only Print`.
5. Add your desired BPs. Select the billing products window, then double-click or drag your desired BP. To continue with the example, this would be any Sunday Only BPs.
6. Add an optional configuration with the steps below. Otherwise, select the **active** box then select **save**.

**NOTE**: If you do not see the desired BP, make sure you have assigned it an [Available Area](example.com). BPs without an assigned Available area _will not_ display here.

##### Optionally, you can configure your SP further:

**Limit available areas** allows you to specify a particular Available Areas that you have added to BPs (if you don't wish to limit, leave all product available areas checked). To limit the available area:

1. Select the limit available area window.
2. Select **set per product**.
3. Toggle between BPs and double-click or drag your desired Available Areas.

**Add incompatible products** allows you to denote incompatible SPs. This feature disallows certain SPs from being combined when configuring Offer Groups. To add an incompatible product:

1. Select the incompatible product window.
2. Double-click or drag all desired incompatible products.

**Add mandatory products** allows you to denote any BPs that must be sold as part of the SP. To add a mandatory product:

1. Select the mandatory product window.
2. Double-click or drag all desired mandatory products.

Congratulations! You've created a Sales Product.

#### What you've learned

To review, you've learned the difference between Sales Products and Billing Products, as well as how to create and customize a Sales Product. Creating these Sales Products is necessary for creating Offer Groups.
