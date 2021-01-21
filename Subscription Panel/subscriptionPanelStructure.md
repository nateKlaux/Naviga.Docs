# Subscription Panel User Guide

## Welcome

Welcome to the Subscription Panel User Guide!

The Subscription Panel is a section of the CMS that allows you to manage the look, feel, and content of your website's new-subscription screen. Every detail is manageable, from what offers display to what colors are used.

### Guide structure

This guide is composed of three main elements:

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

Newspapers are a part of a Newspaper Group, and a Newspaper Group is a part of a Client. Each level can contain properties, but properties set at the Client level act as the default and apply to lower levels as well. However, changes made at lower levels (e.g. Newspaper or Newspaper Group) will not apply to higher levels. Lower level changes are called **overrides** since they override properties set at a higher level.

> **Tip**: We suggest organizing the hierarchy by configuring widely used settings at the Client level, then overriding at lower levels when necessary. Doing so will save you headaches in the future.

#### Choose a hierarchy

You can navigate between the hierarchical levels. To do so:

1. Select the **hierarchy button**. (The button will display the current level's name.) After selecting the button, the CMS Hierarchy screen will appear.
2. Choose the level you wish to be on. The window will disappear. Any change you now make will apply to the selected and lower levels.

#### Overrides

There are two types of overrides:

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

### Component manager

#### Description

The Component Manager subsection allows you to manage your Subscription Panel components. Components are the building blocks for your presentations. Each component has a name, class, and code. Components themselves contain various properties, which you can manage when you edit or create a component.

Each component is comprised of the following things:

- Name - The display name for the component
- Class - The overarching class the component falls into (e.g. address components or payment components)
- Code - The code used to call and refer to the component

> **Note**: Typically, Naviga developers create your components with an SQL script. This ensures that your components are correctly named and ordered. However, you can [create components](example.com) manually.

#### UI

The image below depicts the Component Manager UI.

![Component Manager UI](./screens/component-manager-UI.png)

If you select the **+ add new** button to create a new component, the following screen appears.

![Property UI](./screens/property-UI.png)

-----------

### Structure Admin

#### Description

The Structure Admin subsection allows you to _structure_ components to build a Presentation Template. Whereas components are just the building blocks of your presentation, a template is the _arraignment_ of the building blocks in a particular way.

You can have multiple Presentation Templates. Each Presentation Template contains a Template Name and a Presentation Type, and is comprised of various components.

You can drag the components to arrange their order, or designate certain components as either a parent or child component.

> **Note**: Typically, Naviga developers create your Presentation Templates. This ensures they are created to spec. However, you can [create Presentation Templates](example.com) manually.

#### UI

This image shows two components. One is a parent component and has multiple child components.

![Presentation Template UI](./screens/presentation_templateUI.png)

This image shows the component selector tool. Use it to drag components into your Presentation Template.

![Component Selector](./screens/component-selector.png)

### Presentations

#### Description

The Presentations subsection allows you to manage the _presentation_ of your _arranged components_. Instead of creating or arranging components, you are creating, previewing, editing, or deleting the final presentation of all of your work. Similar to how you use various components to create a Presentation Template, you now fine tune your Presentation Template(s) to create various Presentations.

#### UI

---------------------------------------

## Tutorials
