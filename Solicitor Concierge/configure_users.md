### Configure users, sales teams, and team members

#### Overview and goal

The goal of this guide is to show you how to configure various user accounts in SolCon. This guide explores three categories:

- A `user` is the most general category. This is anyone who has access to your SolCon application. `Users` have various types and privileges. 
- A `Sales Team` is a group of users that has access to sell Sales Products, Divisions, and Offer Groups.
- a `Team Member` is a `user` that has been added to a particular `Sales Team`.

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