# Subscription Panel User Guide

## Welcome

Welcome to the Subscription Panel User Guide!

The Subscription Panel is an application that allows potential customers to purchase subscriptions. You can manage the look, feel, and content of the Subscription Panel in the CMS. Every detail is manageable, from what offers display to what colors are used. 

### Guide structure

This guide is composed of two main elements:

- Overview - gives a brief introduction to the various features covered in this guide
<!-- - Quick start - gives the quickest explanation for how to get started -->
- Tutorials - task-based guides for common Subscription Panel tasks

---------------------------------------

## Overview

The Subscription Panel features work in tandem with the CMS Hierarchy and Cache Management features. This section discusses both the CMS Hierarchy feature and Cache Management feature, as well as the Subscription Panel features. The Subscription Panel is comprised of three subsections:

* Component Manager
* Structure Admin
* Presentations

![Subscription Panel Features](./screens/SubPan-Features.png)

### Diagram

This diagram illustrates how the three features work in tandem. 

![Subscription Panel Diagram](./screens/Subscription-Panel-Diagram.png)

### CMS Hierarchy

#### Description

There are three levels in the CMS Hierarchy:

1. Client
2. Newspaper Group
3. Newspaper

Newspapers are a part of a Newspaper Group, and a Newspaper Group is a part of a Client. Settings can be applied at each level, but settings at the Client level act as the default and apply to lower levels as well. However, changes made at lower levels (e.g. Newspaper or Newspaper Group) will not automatically apply to higher levels. Lower level changes are called **overrides** since they override higher level settings.

> **Tip**: We suggest organizing the hierarchy by configuring widely used settings at the Client level, then overriding them at lower levels when necessary. In some cases, overriding is the best way to manage settings (e.g. overriding Attribute for different Newspapers) and doing so will save you headaches in the future.

#### Choose a hierarchy

You can navigate between the hierarchical levels. To do so:

1. Select the **hierarchy button**. (The button will display the current level's name.) After selecting the button, the CMS Hierarchy screen will appear.
2. Choose the level you wish to be on. The window will disappear. Any change you now make will apply to the selected and lower levels.

#### Overrides

There are two types of overrides for the Subscription Panel section of the CMS:

- structural overrides - these apply to changes in the structuring of different components (e.g. changing parent/child relationships or their location)
- property overrides - these apply to changes of a component's property (e.g. changing the color of a component)

Remove structural overrides with the **remove overrides** button and remove property overrides with the wastebin icon located next to the component in question.

![Overrides Screenshot](./screens/Overrides.png)

-----------

### Cache management

#### Description

This feature clears your cache so that any changes you make take effect. You will want to use `CMS + Panel` button to clear the caches of the CMS and Subscription Panel feature.

> Warning! You must set the panel's URL for this feature to use this feature. From the CMS, select **Admin** -> **CMS Settings** and fill in the `PanelClearCacheUrl1` field with your panel's URL. The URL must not contain an SSL certificate (i.e. use `HTTP`, and do not use `HTTPS`).

If your cache was successfully cleared, a success banner appears at the bottom of the screen.

-----------

### Component manager overview

#### Description

The Component Manager subsection allows you to manage your Subscription Panel components. Components are the building blocks for your presentations. Each component has a name, class, and code. Components themselves contain various properties, which you can manage when you edit or create a component.

Each component is comprised of the following things:

- Name - The display name for the component
- Class - The overarching class the component falls into (e.g. address components or payment components)
- Code - The code used to call and refer to the component

> **Note**: Typically, Naviga developers create your components with an SQL script. This ensures that your components are correctly named and ordered. A component's class and code, for instance, must adhere to a predefined naming convention for them to function properly. So though you can create components manually, **it is not recommended**.

#### UI

The image below depicts the Component Manager UI.

![Component Manager UI](./screens/component-manager-UI.png)

If you select the **+ add new** button to create a new component, the following screen appears.

![Property UI](./screens/property-UI.png)

-----------

### Structure Admin overview

#### Description

The Structure Admin subsection allows you to _structure_ components to build a Presentation Template. Whereas components are just the building blocks of your presentation, a template is the _arraignment_ of the building blocks in a particular way.

Typically you will need only a single Presentation Template. It contains a Template Name and a Presentation Type, and is comprised of various components.

You can drag the components to arrange their order, or designate certain components as either a parent or child component.

> **Note**: Typically, Naviga developers create your Presentation Template. This ensures that it is created to spec. However, you can [create a Presentation Templates](example.com) manually.

#### UI

This image shows two components. One is a parent component and has multiple child components.

![Presentation Template UI](./screens/presentation_templateUI.png)

This image shows the component selector tool. Use it to drag components into your Presentation Template.

![Component Selector](./screens/component-selector.png)

### Presentations overview

#### Description

The Presentations subsection allows you to manage the _presentation_ of your _arranged components_. Instead of creating or arranging components, you are creating, previewing, editing, or deleting the final presentation of all of your work. Similar to how you use various components to create a Presentation Template, you now fine tune your Presentation Template(s) to create various Presentations.

#### UI

You can either create a new presentation, import a presentation (JSON), or select an existing presentation.

![Presentation Types](./screens/presentation-types-ui.png)

When creating a new presentation:
- a **blank presentation** is a presentation with no components.
- **save selection as new** reuses the _same_ components for multiple presentations, which means changes at the component level will affect both/any presentations using these components.
- **duplicate selection** creates _copies_ of the components to use in a new presentation, which means changes at the component level will not affect other presentations.

> **Tip**: When either saving as new or duplicating components, you should rename them so as to avoid adding copy1, copy2, and so on as extensions. 

This image displays the various features of the Presentations menu:

![Presentation Features](./screens/presentation-features-ui.png)

After selecting/creating/importing a presentation, you can:

- preview your presentation (to preview, you must be on a Newspaper level with your CMS hierarchy.)
- set whether your presentation is **active/inactive**, which determines whether the presentation can be viewed by end-users
- set whether your presentation is a **default** presentation
- manage your various components

---------------------------------------

## Tutorials, how-tos, and reference documentation

This section of the guide contains tutorials, how-tos, and reference material for the Subscription Panel. Here you will find in depth information for working with the Subscription Panel. This section covers the following topics:

- Component matrix
- Create, edit, or remove component properties
- Create, edit, or delete a Presentation Template
- Create or import Presentations
- Preview a Presentation
- Create, edit, or delete Presentations

### Components matrix

The matrix below defines each component. Each tab represents a component class and has a table that describes the component and lists each possible parent and child components. Refer to this matrix for component definitions. 

> **Tip**: The intent of the matrix is to provide a comprehensive definition for all (is this every component?) components that you can reference for specific questions. We suggest using task-based tutorials to help with particular tasks.

> (MATRIX THAT IS IN GITBOOK)

-----------------

### Create, edit, or remove component properties

#### Description

Each component must have at least one property, but typically a component has many properties.

#### Create a new property

To add a property to a component:

1. Select the **component manager** button from the CMS.
2. Search for the component that you wish to add a property to and select **edit**. (Optionally, select **+ add new** to create a new component.)
3. Select **+ add new property**. The property creation screen appears.
4. Fill in the property's information.
5. Select **save** in the property's edit column.

#### Edit an existing property

To edit a component's properties:

1. Select the **component manager** button from the CMS.
2. Search for the component that you wish to edit.
3. Select the **edit** button corresponding with your desired component. The property manager will display below.
4. Navigate to the desired property and perform your desired edits.
5. Select either **save** or **save as new**.

#### Remove a property

To remove a property from a component:

1. Select the **component manager** button from the CMS.
2. Search for the component that you wish to remove a property from.
3. Select the **edit** button corresponding with your desired component. The property manager will display below.
4. Find the desired property you wish to remove from the list and select **delete**.

-----------------

### Create, edit, or delete a Presentation Template

You can only edit Presentation Templates at the `Client` hierarchical level. 

To create a new Presentation Template:

1. From the CMS, select the **hierarchy** button and choose the `Client` level.
2. Select **Subscription Panel**, then choose **Structure Admin**.
3. Select **+ add new template**. The template creation screen appears.
4. Choose a Template Name and Presentation Type. **Note**: each Presentation Type has a unique tree structure. If you change the Presentation Type after having made some edits, _the new tree structure will delete the existing tree structure and you will lose your edits._

To edit a Presentation Template:

1. From the CMS, select the **hierarchy** button and choose the `Client` level.
2. Select **Subscription Panel**, then choose **Structure Admin**.
3. Select an existing Presentation Template from the **selected** drop-down menu.
4. Perform any edits you with to make, then select **save**.

To duplicate a Presentation Template:

1. From the CMS, select the **hierarchy** button and choose the `Client` level.
2. Select **Subscription Panel**, then choose **Structure Admin**.
3. Select an existing Presentation Template from the **selected** drop-down menu.
4. Select the **duplicate** button. The duplicated Presentation Template will appear in the drop-down menu. Select it to change it's name.

To delete a Presentation Template:

1. From the CMS, select the **hierarchy** button and choose the `Client` level.
2. Select **Subscription Panel**, then choose **Structure Admin**.
3. Select an existing Presentation Template from the **selected** drop-down menu.
4. Select the **- delete** button. Confirm you wish to delete this Presentation Template and select **Yes**. The template will be removed from the drop-down menu.

-----------------

### Create or import Presentations

You can either create a new presentation or import a presentation from a JSON file.

#### Import a Presentation

To import a Presentation:

1. From the CMS, select the **hierarchy** button and choose a hierarchical level (`Client`, `Newspaper Group`, or `Newspaper`).
2. Select **Subscription Panel**, then choose **Presentations**.
3. Select the **options** drop-down and choose **import**.
4. **Select a file** then select **import**.

If successful, your new presentation should appear under the presentations drop-down menu.

#### Create a Presentation

##### Prerequisites

Each new Presentation should meet the following criteria:

* Have a unique Presentation Name (cannot be blank) that contains only digits and latin letters
* Have a unique Presentation URL
* Have a Presentation Type
* Contain valid parent-child relationships between components.
* Contain the following components:
  1. Presentation Properties
  2. Header
  3. Page
  4. Step
  5. Confirmation
  6. Order Summary

##### Typical Presentation Component Layout

(PRESENTATION LAYOUT DIAGRAM)

##### Procedure

To create a new Presentation:

1. From the CMS, select the **hierarchy** button and choose a hierarchical level (`Client`, `Newspaper Group`, or `Newspaper`).
2. Select **Subscription Panel**, then choose **Presentations**.
3. Select **add new presentation** and choose an option:
    
    A _blank presentation_ contains no components.
    
    _Save section as new_ reuses components. Changes made to components in this presentation will affect other presentations using these components.
    
    _Duplicate selection_ makes copies of the components for this presentation. Changes made to components in this presentation **will not** affect other presentations.

    **Note**: if either saving as new or duplicating, select a presentation to work from the drop-down menu first, then choose your option.
4. Based on your selection, continue to the corresponding section below for further steps.

**Blank Presentations**:

1. Add a presentation URL, presentation name, and presentation type to your new presentation.
2. Choose whether you want the presentation to be a default presentation and whether its status is active/inactive.
3. Use the **component selector** sidebar to add your components.
4. Select **save**.

**Save Section as new**:

1. Change the presentation's name and URL to something unique.
2. (Optionally, rename the components using the Component Renaming Tool. Once finished, select **save and close**. If you don't want to rename the components, select the **x** to exit from the tool).
3. Select **save** to finish.

**Duplicate section**:

1. Change the Presentation's name and URL so that they are unique, then select **ok**.
2. (Optionally, rename the components using the Component Renaming Tool. Once finished, select **save and close**. If you don't want to rename the components, select the **x** to exit from the tool.)
3. Select **save** to finish.

-----------------

### Preview a Presentation

You can preview a Presentation at any time with the **preview** button.

To preview a Presentation:

1. From the CMS, select the **hierarchy** button and choose an option from the `Newspaper` level.
2. Select **Subscription Panel**, then choose **Presentations**.
3. Select the desired Presentation you wish to preview from the **selected** drop-down menu. Greyed Presentations are ...
4. Select the **preview** button. A preview window will appear. If you've recently made changes, clear your cache first. Select **Manage Cache** then **Refresh CMS + Site**.

-----------------

### Edit, delete, or export Presentations

You can edit and delete Presentations.

#### Edit

To edit a Presentation:

1. From the CMS, select the **hierarchy** button and choose a hierarchical level (`Client`, `Newspaper Group`, or `Newspaper`).
2. Select **Subscription Panel**, then choose **Presentations**.
3. Select the desired Presentation you wish to edit from the **selected** drop-down menu. Greyed Presentations are ...
4. Make your desired changes to the Presentation. To add a component, drag them from the **Component Selector** sidebar. To remove a component, select the **- remove** button next to the desired component.
5. Select **save** once finished.

#### Undo a change

If at any time you've made a mistake that you wish to undo, select the **cancel** button. Any changes will be removed and the Presentation screen will disappear.

#### Delete

When you delete a Presentation you **are not** deleting components. They will still be available in the Component Manager section. 

To delete a Presentation:

1. From the CMS, select the **hierarchy** button and choose the `Client` hierarchical level.
2. Select **Subscription Panel**, then choose **Presentations**.
3. Select the desired Presentation you wish to delete from the **selected** drop-down menu. Greyed Presentations are ...
4. Select **- delete**. Confirm this is the correct Presentation and select **Yes**.

#### Export

You can export Presentations as either a JSON or HTML file.

To export a Presentation as JSON:

1. From the CMS, select the **hierarchy** button and choose a level (`Client`, `Newspaper Group`, or `Newspaper`).
2. Select **Subscription Panel**, then choose **Presentations**.
3. Select the **options** drop-down, then choose **export**.
4. Select which Presentation(s) you want to export. The **show advanced** button allows you to include entity, property, and dictionary types as well as structure templates into the JSON file.
5. Select **export content**. The download dialogue will appear. **Note**: if you chose many Presentations or the Presentation is large, it may take longer for the dialogue to appear.

To export a Presentation as HTML:

1. From the CMS, select the **hierarchy** button and choose a level (`Client`, `Newspaper Group`, or `Newspaper`).
2. Select **Subscription Panel**, then choose **Presentations**.
3. Select the Presentation you wish to export from the **selected** drop-down menu.
4. Select the **options** drop-down, then choose **Business export**. The download dialogue will appear.

-----------------

### Add a landing to a Presentation

#### Overview

A landing page hosts desired promotions that you want potential subscribers to see immediately.  

To add a landing to your Presentation, make a landing component (e.g. `Landing - Tiles V3`, `Landing - Tab V3`, etc.) the child of the `Page V3` component, then add any desired promotion components as children of the landing component. Which ever promotions components you choose will appear on the landing page.

#### Step-by-step guide

Arrange the components:

1. From the CMS, select the **hierarchy** button and choose a level (`Client`, `Newspaper Group`, or `Newspaper`).
2. Select **Subscription Panel**, then choose **Presentations**.
3. From the drop-down menu, select the Presentation you wish to add a landing. The Presentation's structure and components will appear below.
4. [Add](link to how to add new components) or drag your desired landing component into the Presentation and make it a child to the `Page` component.
5. Expand the landing component to display it's children, then add promotion components as children (e.g. `Promotion Digital`, `Promotion ZipCode`, etc).

Next, configure the promotion component's properties. Select the **details** button to expand the component's properties.

At minimum, the property needs a name. However, we suggest you configure the following properties:

* `Button OfferGroupId` - add the promotion's Offer Group ID to this property. This links this promotion component to the promotion in the circulation database.
* `NoOffersAvailableMessage` - add a message to this property. This displays a message to users when there are no offers available to them (usually because of location).
* `Styling EnableCustomization` - if `On`, allows you to customize the landing promotion's styling (e.g. `Styling Button Type`, `Styling TextColor`, etc).
* `ActionsInModal` - if `On`, displays the promotions in a Modal window so that user's must choose before continuing.
* `Action ZipCodeFail Title` - error message for postal codes that are out of geographic range.
* `Tile Top Text` - if `Show Tile Top` is `On`, then the text that displays on the top of the offer promotion's tile.


-----------------

### Add social media icons at the confirmation screen

#### Overview

You can add social media icons to your confirmation screen. Each social media element has it's own component. Each `Social Media V3` component must be a child of the `Confirmation V3` component, which is a child of the `Page V3` component.

#### Before you start

Before you follow the steps below, be sure that the `Confirmation V3` component is a child of the `Page V3` component.

#### Step-by-step guide

Arrange the components:

1. From the CMS, select the **hierarchy** button and choose a level (`Client`, `Newspaper Group`, or `Newspaper`).
2. Select **Subscription Panel**, then choose **Presentations**.
3. From the drop-down menu, select the Presentation you wish to add social media components to. The Presentation's structure and components will appear below.
4. Drag a `Social Media V3` component into the Presentation and make it a child to the `Confirmation V3` component.
    **Note**: Each social media icon requires it's own component. For instance, if you want icons for Facebook, Twitter, and LinkedIn, you will need three social media components.

5. Select **save**.

Configure various component properties: 

1. Navigate to the social media components.
2. Expand each social media component and fill out the `SocialMedia Link` `SocialMedia Type` properties. **Example**: For Twitter, enter `www.twitter.com` for the link and select `Twitter` from the `type` drop-down menu.
3. (Optionally, configure the `SocialMedia Header` [e.g. "Follow us on"].)
4. Select **save**.


-----------------

### Add app-download buttons to the confirmation screen

#### Overview

You can add app-download buttons to the confirmation screen. Currently we support buttons for the Apple App Store and the Google Play Store. Each app store button needs it's own `App Downloads V3` component, which must be a children of the `Confirmation V3` component.

#### Before you start

Before you follow the steps below, be sure that the `Confirmation V3` component is a child of the `Page V3` component.

#### Step-by-step guide

Arrange the components:

1. From the CMS, select the **hierarchy** button and choose a level (`Client`, `Newspaper Group`, or `Newspaper`).
2. Select **Subscription Panel**, then choose **Presentations**.
3. From the drop-down menu, select the Presentation you wish to add download buttons to. The Presentation's structure and components will appear below.
4. Drag a `App Downloads V3` component into the Presentation and make it a child to the `Confirmation V3` component.
    **Note**: Each app store icon it's own component. For instance, if your app is in both the Apple App Store and the Google Play Store, you will need two components.
5. Select **save** next to each component to save your work.

Configure various component properties:

1. Navigate to the `Confirmation V3` component that is the parent to your `App Downloads V3` components.
2. Select the **details** button to expand the component's properties.
3. Toggle `AppDownloads.Show` to `ON`.
4. (Optionally, configure the `AppDownloads Header` [e.g. "Download our apps].)
5. Select **save**.

Other non-mandatory properties:

* `AppDownloads.Subtitle` - Subtitle to the header
* `AppDownloads.Image` - adds a background image
* `AppDownloads.Styling.Background` - changes the background color


-----------------

### Configure an upsell offer

#### Overview

You can add add upsell offers to your components by added the `Upsell V3` component as a child to any `Step V3` component.

#### Step-by-step guide

Arrange the components:

1. From the CMS, select the **hierarchy** button and choose a level (`Client`, `Newspaper Group`, or `Newspaper`).
2. Select **Subscription Panel**, then choose **Presentations**.
3. From the drop-down menu, select the Presentation you wish to add an upsell feature to. The Presentation's structure and components will appear below.
4. Drag the `Upsell V3` component into your Presentation and make it a child to any `Step V3` component.
5. Select **save**.

Configure various component properties:

1. Navigate to the `Upsell V3` component and select the **details** button.
2. Toggle `Offer ShowImage` to `On`.
3. Add text to the `InlineTitle` property and `Offer MarketingTitle Text`.
4. Select **save**.

> **Note**: These are the recommended properties to make your component functional. Fill in the other properties to add more customization.

### Ask for registration password only at confirmation

#### Overview

You can arrange your Subscription Panel to ask for a user's registration password _after_ they've finished purchasing, at the confirmation screen. The component checks the user's email to see if it is new, and if it is, it will prompt for a registration password.

This often leads to more customer retention, and makes the checkout process efficient. Todo this, the `Registration on Confirmation V3` component needs to be a child of the `Confirmation V3` component. Follow the instructions below for a step-by-step guide.

#### Step-by-step guide

Arrange the components:

1. From the CMS, select the **hierarchy** button and choose a level (`Client`, `Newspaper Group`, or `Newspaper`).
2. Select **Subscription Panel**, then choose **Presentations**.
3. From the drop-down menu, select the Presentation you wish to edit. The Presentation's structure and components will appear below.
4. Using the Component Selector tool, drag the `Registration on Confirmation V3` component into your Presentation and make it a child to any `Confirmation V3` component.
5. Select **save**.

Configure various component properties:

1. Navigate to the `Registration on Confirmation V3` component and select the **details** button.
2. Toggle `Password Show` to `On`.
3. Toggle `Password Validation Required Apply` to `On`.
4. Add text to the `Title` property (e.g. "Create a password") and `Button Text` property (e.g. "Submit").
5. Select **save**.

### Add an abandonment popover

#### Overview

An abandonment popover is a popover that appears whenever a user moves their pointer near the top of the screen, presumably to abandon the page. The popover usually contains an offer at a discounted price, though you can customize the popover to contain any offer.

To add this popover to your presentation, add the `AbandonmentPopoverV3` component as a child to the `Page V3` component. Follow the step-by-step guide below for more instructions.

#### Step-by-step guide

Arrange the components:

1. From the CMS, select the **hierarchy** button and choose a level (`Client`, `Newspaper Group`, or `Newspaper`).
2. Select **Subscription Panel**, then choose **Presentations**.
3. From the drop-down menu, select the Presentation you wish to edit. The Presentation's structure and components will appear below.
4. Using the Component Selector tool, drag the `AbandonmentPopoverV3` component into your Presentation and make it a child to any `Page V3` component.
5. Select **save**.

Configure various component properties:

1. Navigate to the `AbandonmentPopoverV3` component and select the **details** button.
2. Toggle `Button Show` to `On`.
3. Add the offer id of the offer you wish to sell to the `Button OfferGroupId` field. This links the button to your offer in circulation.
4. Add text to the `title` and `body` properties (e.g. "Get Unlimited Access to Local News");
5. Add text to the `Button Text` property (e.g. "Get this Offer").
6. Set the `MaxWidth(px)` property to determine the pixel size of your popover. 480 pixels is standard.
7. Select **save**.

> **Note**: These are the recommended properties we suggest to get going for a functional abandonment popover. Optionally, configure the `BackgroundColor`,`BackgroundImage`, or other properties.


### Add an idle popover

#### Overview

You can add an idle popover to your Subscription Panel that triggers a reminder popover at determined intervals.

To add this popover to your presentation, add the `Idle Popover V3` component as a child to the `Page V3` component. Follow the step-by-step guide below for more instructions.

#### Step-by-step guide

Arrange the components:

1. From the CMS, select the **hierarchy** button and choose a level (`Client`, `Newspaper Group`, or `Newspaper`).
2. Select **Subscription Panel**, then choose **Presentations**.
3. From the drop-down menu, select the Presentation you wish to edit. The Presentation's structure and components will appear below.
4. Using the Component Selector tool, drag the `Idle Popover V3` component into your Presentation and make it a child to any `Page V3` component.
5. Select **save**.

Configure various component properties:

1. Navigate to the `Idle Popover V3` component and select the **details** button.
2. Add a number of seconds `Idle Timeout (sec)` property. This number determines how many seconds go by before the popover appears.
3. Add a number to the `NumberOfOpenings` property. This number determines how many times the idle popover appears before it stops altogether.
4. Select **save**.

> **Note**: These are the recommended properties we suggest to get going for a functional idle popover. Optionally, configure the `BackgroundColor`,`BackgroundImage`, `BorderColor`, and `BorderWidth` properties.

### Add a cookie popover to your Presentation

#### Overview

You can add a cookie notice popover to your Presentation that notifies users of which cookies are being collected. When a user visits the page, the page will check to see if a igmck cookie with a value of `TRUE` already exists. If it does, nothing will happen. If it does not, a cookie banner will display. When the user closes the banner, a cookie will be set with a value of `TRUE` and an expiration date of 120 days.

To add the cookie notice popover, you must add the `Cookie Notice V3` component as a child to the `Page V3` component. Follow the step-by-step guide below for more instructions.

#### Step-by-step guide

Arrange the components:

1. From the CMS, select the **hierarchy** button and choose a level (`Client`, `Newspaper Group`, or `Newspaper`).
2. Select **Subscription Panel**, then choose **Presentations**.
3. From the drop-down menu, select the Presentation you wish to edit. The Presentation's structure and components will appear below.
4. Using the Component Selector tool, drag the `Cookie Notice V3` component into your Presentation and make it a child to any `Page V3` component.
5. Select **save**.

Configure various component properties:

1. Navigate to the `Cookie Notice V3` component and select the **details** button.
2. Enter values for the following property fields:
    `CookieText` - The text that appears on the banner, typically explaining that by continuing the user agrees to the cookies.
    `CookieLink` - A link typically to your privacy policy.
    `CookieLinkText` - The text of your link.
3. (Optionally, enter values for the following property fields:)
    `Styling BackgroundColor` - a hexadecimal field for the banner color. If not used, the default color will be used.
    `Styling TextColor` - a hexadecimal field for the text color.
4. Select **save**.

