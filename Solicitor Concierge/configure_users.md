### Configure users, sales teams, and team members

#### Overview and goal

The goal of this guide is to show you how to configure the various user accounts in the SolCon application:

**Users** is a fundamental account type. There are various types of user accounts, each with their own roles and permissions. View the [Roles and Permissions Matrix](http://example.com) for extensive definition.

**Sales Teams** consist of either one or more Team Members. The purpose of a Sales Team is give Team Members the ability to sell Offer Groups.

**Team Members** consist of either one or more Users and *must* be a part of a Sales Team.

As an admin, you must create your accounts in this order:

1. Users
2. Sales Teams
3. Team Members

This order is important because when you attempt to create Team Members, you must also assign them to a Sales Team (and therefore already have a Sales Team created).

This diagram show the general relationship between users, team members, and sales teams.

(SCREEN OF DIAGRAM)

Team Members can only sell the Offer Groups associated with their Sales Team. You can create multiple Team Members, both part of the sames Sales Team, but each with distinct Offer Groups. 

>
> An Example:
Let's say there exists five Offer Groups, one Sales Teams, three Team Members, and many Users. In this scenario, out of the five total Offer Groups, the Sales Team only has collective access to OG1, OG2, and OG3 (OG4 and OG5 are used in a Sales Team not discussed here).
>
> Team Members 1 is part of the Sales Team, but only has access to OG1 and OG2, whereas Team Members 2 is part of the same Sales Team, but only has access to OG 2 and OG 3. In this scenario, Users will only have access to the Offer Groups that there Team Members group has access to, even if the Sales Team is associated with more Offer Groups.
>
>However, Team Members 3 is designated as default, which means all of the associated Users will have access to all of the Offer Groups at the Sales Team level.
>
>This example is visuzlied below as a spread sheet:

(SCREEN OF SPREAD SHEET)

#### Before you start

Make sure you meet the following pre-requisites before starting the tutorial steps:

* Ensure the default Sales Teams for the platforms `Kiosk (LTE)` and `SubconAdmin` have been created
* Have admin privileges in your SolCon account

#### Create a user

In this section, you will learn how to create a general user.

Create a user:

1. Select the **admin** menu in the SolCon dashboard, then choose **users**. A list of SolCon users will display.
2. Select the **+ new** button. A creation window will appear.
3. Enter a `user name`, as well as an email address and password. `User names` must not contain special characters.
4. Select the **role** box then double-click or drag to add a role. Role types are defined in the table below. Only one role can be selected.
5. Select **save**.

|  |  |  |  |  |  |
|-|-|-|-|-|-|
| **User role type:** | Direct sales/Kiosk Admin | Direct sales/Kiosk User | Marketing Admin | Marketing Power User | Marketing Limited |
| **Offer Groups:** |  |  |  |  |  |
| Create New Offer Group | Read | X | Write | Write | Write |
| Save Existing Offer Group as New Draft | Read | X | Write | Write | Write |
| Save Offer Group as Draft | Read | X | Write | Write | Write |
| Edit Draft Offer Group | Read | X | Write | Write | Write |
| Save Offer Group As Published | Read | X | Write | Write | X |
| Edit Published Offer Group | Read | X | Write | Write | X |
| **Promotion:** |  |  |  |  |  |
| Create New Promotion | Read | X | Write | Write | Write |
| Edit Existing Promotion | Read | X | Write | Write | Write |
| **Inventory:** |  |  |  |  |  |
| Marketing Text | X | X | Write | Write | Write |
| Terms & Conditions | X | X | Write | Write | Write |
| Sales Platforms | X | X | Read | X | X |
| Log | X | X | Read | Read | Read |
| Divisions | X | X | Read | Read | Read |
| Division Bundle | X | X | Write | Write | Write |
| Coding | X | X | Read | Read | X |
| Image | X | X | Read | Read | Read |
| Billing Plan | X | X | Read | Read | X |
| Service Type | X | X | Read | Read | X |
| Household Level | X | X | Read | X | X |
| Price Rules | X | X | Read | X | X |
| SubCon Product | X | X | Read | Read | X |
| SolCon Product | X | X | Write | Read | Read |
| SolCon Product Bundle | X | X | Write | Write | Write |
| Premium | X | X | Write | Write | Read |
| Available Area | X | X | Read | Read | Read |
| Name Value Pair | X | X | Write | Write | X |
| Attribute | X | X | Write | Write | Write |
| **Sales Team/Team Members:** |  |  |  |  |  |
| Sales Team | Write | X | Write | Write | Read |
| Team members | Write | X | Write | Write | Read |
| **Admin:** |  |  |  |  |  |
| Users | Write | X | Write | Write | Read |

#### Create a sales team

To create a sales team:

1. Select the **teams** menu in the SolCon dashboard, then choose **sales team**. A list of sales teams will display.
2. Select the **+ new** button. A creation window will appear.
3. Enter a name for the sales team (typically the vendor's name), then select the platform the team will be using.
4. Select the **divisions** box, then double-click or drag to add divisions the team will use.
4. Select the **Offer Groups** box, then double-click or drag to add Offer Groups the team will use.
5. (Optionally, if you've already created team members, you can add them to the team by selecting the **team members** box.)
6. Fill in any contact or bank account information and select **save**.

#### Create a team member

To create a team member:

1. Select the **teams** menu in the SolCon dashboard, then choose **team members**. A list of team members will display.
2. Select the **+ new** button. A creation window will appear.
3. Enter a name for the team member.
4. Select the **team member** box, then double-click or drag to add teams the member will be a part of.
5. Select the **divisions** and **Offer Groups** boxes, then double-click or drag to add divisions and Offer Groups the team member will use.
6. Select the **users** box, then double-click or drag the `user` to associate the `user` and `team member` hierarchies.
7. Select **save**.

#### What you've learned

Congratulations! You've created various types of users. To recap, you've learned about `users`, `sales team`, and `team members`, as well as how the three relate to each other.