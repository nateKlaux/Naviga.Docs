
Two images -- 

subcon site is self-service account manager.

home page= non secure page, after credentials are given all other pages are secure.

==============================

# CMS/SubCon Site Documentation

## Overview

Our Content Management System (CMS) allows you to manage your Subscriber Concierge Site (SubCon Site). The SubCon Site is the self-service, end-user website that allows subscribers to manage their account and subscriptions.

### Diagram

This diagram details how the CMS and SubCon Site work together in tandem. As you make your way through the guide, please refer to this diagram.

(INSERT AND CREATE DIAGRAM)

<!-- Diagram of how CMS functions alongside SubCon Site. Should also specify some functionality like Cache Management and Hierarchy. This will be similar to SubPanel Diagram. -->

### Navigating CMS UI

The screenshot below is an annotated screenshot that depicts the various features of the CMS. View the **CMS Definitions** heading below for detailed descriptions.

<!-- Annotated screens of CMS UI. Similar to docs before. -->

### CMS Definitions

The following list provides high-level definitions for the various features of the CMS. This section isn't meant to explore these features at length, but to provide a general overview of what you can accomplish with the CMS. Check out the [**Tutorials**](example.com) for in-depth how-to guides that explore how to accomplish particular tasks.

**Cache**: Use this feature to clear your cache so that any changes you make take effect. You will want to use `CMS + Site` button to clear the caches of the CMS and SubCon Site.

**CMS Hierarchy**: Use this feature to select a hierarchical level:

1. Client
2. Newspaper Group
3. Newspaper

Newspapers are a part of a Newspaper Group, and a Newspaper Group is a part of a Client. Settings can be applied at each level, but settings at the Client level act as the default and apply to lower levels as well. However, changes made at lower levels (e.g. Newspaper or Newspaper Group) will not automatically apply to higher levels. Lower level changes are called **overrides** since they override higher level settings.

> **Tip**: We suggest organizing the hierarchy by configuring widely used settings at the Client level, then overriding them at lower levels when necessary. In some cases, overriding is the best way to manage settings (e.g. overriding Attribute for different Newspapers) and doing so will save you headaches in the future.

**Attributes**: Use this feature to create attributes. Attributes are placeholders that you can use elsewhere. Call the attribute wth `{{Attribute_Name}}`.

**Benefits**: Use this feature to create benefit boxes that display on the SubCon Site home page. Theoretically, you can customize these to display anything, but we've designed them so that you can easily communicate the benefits of your subscriptions to your customers. You can toggle whether these display for individuals not currently logged in.

**Rewards**: Use this feature to create rewards boxes that display on the SubCon Site home page. Similar to the benefits boxes, you can customize these displays as you see fit, but we've designed them so that you can easily communicate customer rewards to your customers.

**Content**: Use this feature to add, edit, or delete content segments from your various pages. Use the drop-down menu to select a **Page** and see which segments are used by that **Page**. General information regarding the Segment will display, but you can also edit the segment (select **Edit**) and check which other division's use that segment (select **UsedBy**).

Check out the [Create a segment](example.com) tutorial to learn more about creating pages and segments.

**FAQ**: Use this feature to add an FAQ section to your SubCon Site.

**Images**: Use this feature to manage the various images in your SubCon Site. Select **Upload** to add new images to your databse. Select **Manager** to edit, preview, or delete existing images.

Each image has a category that determines where or how the image is used.

**Slideshow**: Use this feature to manage the image slideshow that appears on various pages of the SubCon Site. Typically, slideshows work best on the home page, but you can apply them elsewhere. You can schedule your slideshows to appear on predetermined dates/times. You can also create, edit, delete, or activate/deactivate slideshows.

**Notifications**: Use this tool to manage your notification's messages (i.e. the actual notification message). **Note**: use the **Notification New** > **Notifications New** to create new notifications; see the category below.

**Notifications New**: Use this tool to manage various notifications. There are four subcategories:

- **Notifications New** - a list of every notification
- **Notifications New Mngmt.** - tool to create new notifications
- **Test Notification New** - tool to test notifications
- **Consumer Items Mngmt.** - tool to create, edit, or delete consumer items

**Navigation**: Use this tool to manage links for the following categories:

- **Links** - create, edit, or delete all of your links in your in your SubCon Site.
- **Menu** - create, edit, or delete links in the menu.
- **Footer** - create, edit, or delete links and styling in the footer of your SubCon Site.

**Email Content**: Use this tool to manage ... need more info.

**Admin**: Use this tool to manage various admin features:

- **User Management** - add, edit, or delete users or user information. 
- **Page/Segment Mngmt.** - add, edit, or delete **Pages** or **Segments**, and assign segments to pages.
- **Notification Management** - add, edit, or delete notifications.
- **Newspaper Management** - add, edit, or delete newspapers (divisions).
- **Clearcache Urls** - add, edit, or delete clearcache URLs.
- **CMS Settings** -  manage various CMS settings.

## Tutorials

This section of the guide presents task-based tutorials.
The tutorials are organized around the categories of the CMS sidebar (e.g. attributes, benefits, rewards, etc.).

----------

### Manage attributes

You can easily create, edit, or delete attributes from the CMS.

**_To create an attribute_**:

1. From the CMS, select **Attributes** in the sidebar. Every attribute appears in a searchable table.
2. Select **+ Add**. The attribute creation row appears at the top of the table.
3. Fill in the required fields, then select **Save**.

**_To edit an attribute_**:

1. From the CMS, select **Attributes** in the sidebar. Every attribute appears in a searchable table.
2. Navigate to the desired attribute in the table (a search bar is available), then select **Edit**.
3. Edit your desired fields, then select **Save**.

**_To delete an attribute_**:

1. From the CMS, select **Attributes** in the sidebar. Every attribute appears in a searchable table.
2. Navigate to the desired attribute in the table (a search bar is available), then select **Delete**.
3. Confirm your decision and select **Confirm**. The attribute is removed from the table.

**_To import attributes_**:

**Note**: This tool is for _all_ the attributes, and will override existing attributes if used.

1. From the CMS, select **Attributes** in the sidebar.
2. Select the **Options** drop-down, and choose **Import**. The import dialogue appears.
3. Select the **Select File** button, then choose an XML file to upload. **Note**: Currently, this system only consumes XML.
4. Select **Import**, then confirm that you have selected the correct file and select **Import**.

**_To export attributse_**:

1. From the CMS, select **Attributes** in the sidebar.
2. Select the **Options** drop-down, and choose **Export**.
3. Choose how or where you would like to save your exported XML.

----------

### Manage benefits

You can easily add, update, and delete benefit statements, as well as arrange their display order. Benefits display on the home page, and you can choose whether they appear to users not currently logged in.

**_To add a benefit_**:

1. From the CMS, select **Benefits** from the sidebar. The benefit management screen appears.
2. Select the **+ Add** button. The benefit fields become active.
3. Fill in the required fields:
    Title - add a title for the benefit
    Name - add a name for the benefit
    Display for - check whether the benefit displays while logged out and logged in
4. Select **Save**.

**_To edit a benefit_**:

1. From the CMS, select the **Benefits** from the sidebar. The benefit management screen appears.
2. Choose the desired benefit from the **Select a Benefit** drop-down.
3. Edit the desired fields.
4. Select **Save**.

**_To arrange the benefit display order_**:

1. From the CMS, select **Benefits** from the sidebar. The display order screen appears below.
2. Drag the benefits into the desired order. The top-most position displays on the left and the bottom-most position displays on the right.
3. Select **Save**.

**_To delete a benefit_**:

1. From the CMS, select **Benefits** from the sidebar. The benefit management screen appears.
2. Choose the desired benefit from the **Select a Benefit** drop-down.
3. Select the **- Delete** button.
4. Confirm that you wish to delete this benefit, then select **Confirm**.

----------

### Manage rewards

You can easily manage your rewards section. Rewards appear on the homepage below any benefits to customers currently logged in.

**_To create a reward_**:

1. From the CMS, select **Rewards** from the sidebar. The rewards management screen appears.
2. Select the **+ Add** button. The reward fields become active.
3. Fill in the required fields:
    Title - add a title for the reward
    Name - add a name for the reward
    Reward code - the circulation code for the reward.
    Reward category - the category of the reward.
    Total tickets available - the total number of reward tickets available.
    Display for - check whether the benefit displays while logged out and logged in
4. Select **Submit**.

**_To edit a reward_**:

1. From the CMS, select the **Reward** from the sidebar. The reward management screen appears.
2. Choose the desired reward from the **Select a Reward** drop-down.
3. Edit the desired fields.
4. Select **Submit**.

**_Schedule a reward to appear at a set time_**:

1. From the CMS, select the **Reward** from the sidebar. The reward management screen appears.
2. Choose the desired reward from the **Select a Reward** drop-down.
3. Navigate to the **Display Settings** section, then edit the following fields:
    Active - toggles whether the reward is currently active
    Scheduled - if set to `On`, then `Start`/`End` dates appears. After you select a date, `AM`/`PM` times appear.
    Term - determines how often the reward appears (e.g, once, daily, weekly, or monthly).
4. Select **Submit**.

**_To delete a reward_**:

1. From the CMS, select **Reward** from the sidebar. The reward management screen appears.
2. Choose the desired reward from the **Select a Reward** drop-down.
3. Select the **- Delete** button.
4. Confirm that you wish to delete this reward, then select **Confirm**.

----------

### Manage content and pages

To manage pages and segments, you must complete the following steps:

1. Create a page
2. Create a segment
3. Assign a segment to a page
4. Edit the content of the segment

The procedures below show you how to accomplish each of these tasks.

As a general overview, in the **admin section**, you can create, edit, delete, and assign/unassign pages and segments. In the **content section**, you can edit the _content_ of already created segments. The content manages what the segment actually looks like on the SubCon Site.

You can also import/export segments in XML.

> **Note**: View the [Page Mapping]() section for visualizations about how and which segments affect what on an actual page.

#### Admin section

**_To create a page_**:

1. From the CMS, select **Admin** from the sidebar, then select **Page/Segment Mngmt.** The page and segment management screen appears.
2. Select the **+ Add** button in the **Page Management** container. The page fields become active.
3. Fill in the following fields:
    Name - the page's unique name
    URL - the page's URL
    Active - toggle to either `On` or `Off` to determine whether the page will be active
4. Select **Submit**.

**_To delete a page_**:

1. From the CMS, select **Admin** from the sidebar, then select **Page/Segment Mngmt.** The page and segment management screen appears.
2. Select a page from the **Page** drop-down menu.
3. Select the **- Delete** button.
4. Confirm that you wish to delete this page, then select **Confirm**.

**_To create a segment_**:

1. From the CMS, select **Admin** from the sidebar, then select **Page/Segment Mngmt.** The page/segment management screen appears.
2. Select the **+ Add** button in the **Segment Management** container. The segment fields become active.
3. Fill in the following fields:
    Name - the segment's unique name
    ControlId - the segment's control id
    Description - a description of the segment
4. Select **Submit**.

**_To delete a segment_**:

1. From the CMS, select **Admin** from the sidebar, then select **Page/Segment Mngmt.** The page and segment management screen appears.
2. Select a segment from the **Segment** drop-down menu.
3. Select the **- Delete** button.
4. Confirm that you wish to delete this segment, then select **Confirm**.

**_To assign a segment from a page_**:

1. From the CMS, select **Admin** from the sidebar, then select **Page/Segment Mngmt.** The page/segment management screen appears.
2. Select a the desired page from the **Assign Segments** container. The assigned segment field becomes active, and all (if any) currently assigned segments appear. 
3. Select some empty space in the field and a drop-down with the available segments appears.
4. Either search or begin typing, then hit your **return** key once you locate your desired segment. The segment is now assigned to the page.

**_To remove a segment from a page_**:

1. From the CMS, select **Admin** from the sidebar, then select **Page/Segment Mngmt.** The page/segment management screen appears.
2. Select a the desired page from the **Assign Segments** container. The assigned segment field becomes active, and all (if any) currently assigned segments appear. 
3. Select the **X** that corresponds with the desired segment. The segment is now removed from the page.

#### Content section

> **Note**: View the [Page Mapping]() section for visualizations about how and which segments affect what entities on an actual page.

**_To edit the content of a segment_**:

1. From the CMS, select **Content** from the sidebar. The content management screen appears.
2. Choose the desired page from the **Filter by Page** drop-down menu. Every segment assigned to that page appears in a table.
3. Navigate to the desired segment and select **Edit**. The fields become active.
4. Edit the segment's content and, once finished, select **Save**.

**_To import segments_**:

1. From the CMS, select **Content** from the sidebar. The content management screen appears.
2. Select the **Options** drop-down, and choose **Import**. The import dialogue appears.
3. Select the **Select File** button, then choose an XML file to upload. **Note**: Currently, this system only consumes XML.
4. Select **Import**, then confirm that you have selected the correct file and select **Import**.

**_To export segments_**:

1. From the CMS, select **Content** in the sidebar. The content management screen appears.
2. Select the **Options** drop-down, and choose **Export**.
3. Choose how or where you would like to save your exported XML.

----------

### Manage the FAQ section

You can easily create FAQ sections on your SubCon Site. To create an FAQ section, you will want to:

1. Create an FAQ group (category, such as "Home Delivery" or "Billing")
2. Create FAQ questions and answers, then assign those questions to the FAQ group

**_To create an FAQ group_**:

1. From the CMS, select **FAQ** in the sidebar. The FAQ management screen appears.
2. Under the **Groups** container, select the **+ Add** button. An FAQ Group row becomes active in the table below.
3. Add a name to the group, then toggle **Active** to `On`.
4. Select **Save** from that row.

**_To arrange FAQ Groups display order_**:

1. From the CMS, select **FAQ** in the sidebar. The FAQ management screen appears.
2. Under the **Groups Display Order** container, arrange your groups' order. The top-most box appears to the right while the bottom-most box appears to the left.
3. Once finished, select **Save**.

**_To create an FAQ question_**:

1. From the CMS, select **FAQ** in the sidebar. The FAQ management screen appears.
2. Under the **Questions & Answers** container, select the **+ Add** button. An FAQ question and answers row becomes active in the table below.
3. Select the group that the question/answer belongs to.
4. Enter the question in the **Question** field, then enter the answer in teh **Answer** field.
5. Determine whether you want the question to be active, then select **Save**.


----------
### Manage images

You can easily upload and manage how/where your images are used.

**_To upload an image_**:

1. From the CMS, select **Image** from the sidebar, then select **Upload** The image uploader screen appears.
2. Select the **+ Add files** button, then choose the images files you want to upload (up to 5MB of JPG, GIF, or PNG). The image appears in the image queue and provides information.
3. For each image, fill in the following fields:
    Category assignment - determines where the image will be used
    Alternate text - optional, but adds image description text
4. Select either **Start Upload** to upload all images in the queue, or **Start** next to an image in a row to upload that single image.

**_To edit an image_**:

1. From the CMS, select **Image** from the sidebar, then select **Manager** The image manager screen appears and displays all of your uploaded images.
2. (Optionally, filter your images by category by selecting an image category.)
3. Navigate to the desired image and hover your pointer over it.
4. Select the **Pencil/editing** icon. The image editing screen appears.
5. Make your changes, then select **Save Changes**.

**_To preview an image_**:

1. From the CMS, select **Image** from the sidebar, then select **Manager** The image manager screen appears and displays all of your uploaded images.
2. (Optionally, filter your images by category by selecting an image category.)
3. Navigate to the desired image and hover your pointer over it.
4. Select the **Magnifying Glass** icon. The image appears in a modal.
5. However your pointer to the left/right of the image and select the **Arrow** button to navigate through your images. Otherwise, select the **X** to close the screen.

**_To delete an image_**:

1. From the CMS, select **Image** from the sidebar, then select **Manager** The image manager screen appears and displays all of your uploaded images.
2. (Optionally, filter your images by category by selecting an image category.)
3. Navigate to the desired image and hover your pointer over it.
4. Select the **X** icon. The image deletion screen appears.
5. Confirm that you want to delete this image, then select **Confirm**.

**_To add an image category_**:

1. From the CMS, select **Image** from the sidebar, then select **Manager** The image manager screen appears.
2. Select the **+** button next to the image categories. A text field appears.
3. Fill in the text field with the name of your category, then select the **Save Icon**.

----------

### Manage slideshows

You can easily create and schedule slideshows. Slideshows are photo reels that appear on your SubCon Site's homepage.

**_To create a slideshow_**:

1. From the CMS, select **Slideshow** from the sidebar. The slideshow manager appears.
2. Select the **+ Add** button. The slideshow fields become active.
3. Fill in the required fields:
    Name - enter the slideshow's name
    Display for - determine where the slideshow appears
4. Navigate to the **Slideshow Images** portion, and drag an image into the slideshow.
5. (Optionally,) add a fill in a link to make the image clickable.
6. Select **Submit**.

**_To edit a slideshow_**:

1. From the CMS, select **Slideshow** from the sidebar. The slideshow manager appears.
2. Select a slideshow from the **Slideshow** drop-down menu. That slideshow's details populate.
3. Edit your desired fields, then select **Submit**.

**_To schedule a slideshow to appear at a set time_**:

1. From the CMS, select **Slideshow** from the sidebar. The slideshow manager appears.
2. Select a slideshow from the **Slideshow** drop-down menu. That slideshow's details populate.
3. Toggle **Scheduled** to `On`. A `Start`/`End` field appears. Once you choose a date, an `AM`/`PM` selection appears.
4. Select **Submit**.

**_To delete a slideshow_**:

1. From the CMS, select **Slideshow** from the sidebar. The slideshow manager appears.
2. Select a slideshow from the **Slideshow** drop-down menu. That slideshow's details populate.
3. Select the **- Delete** button, then confirm your decision and select **Confirm**.

---------

### Manage navigation/links

You can easily manage all of your links in your SubCon Site, as well as the menu and footer.

**_To add a link_**:

1. From the CMS, select **Navigation** from the sidebar, then select **Links**. The links manager screen appears.
2. Select the **+ Add** button. The link fields below become active.
3. Fill in the required fields; however over the **?** symbol for definitions.
4. Select **Save**.

**_To edit a link_**:

1. From the CMS, select **Navigation** from the sidebar, then select **Links**. The links manager screen appears.
2. Select a link from the **Select a Link** drop-down menu. That links information populates in the fields below.
3. Perform your desired edits, then select **Save**.

**_To edit a link_**:

1. From the CMS, select **Navigation** from the sidebar, then select **Links**. The links manager screen appears.
2. Select a link from the **Select a Link** drop-down menu. That links information populates in the fields below.
3. Select the **- Delete** button. The link is removed from your SubCon Site.

**_To create a menu_**:

1. From the CMS, select **Navigation** from the sidebar, then select **Menu**. The menu manager screen appears.
2. Under the **Links Assignment** container, select the **+ Add** button. The link menu fields below become active.
3. Fill out the required fields, then select the **Save Icon** button. Your menu now appears in the **Menu** drop-down list, and you can add links to it.

**_To assign links to a menu_**:

1. From the CMS, select **Navigation** from the sidebar, then select **Menu**. The menu manager screen appears.
2. Under the **Links Assignment** container, select a menu from the **Menu** drop-down list. The available links appear in the **Available Links** container to the left, and your menu's links container appears to the bottom.
3. Drag the desired links from the **Available Links** container to the **Menu Links** container. Arrange them to your desired order.
4. Once finished, select **Save**.

**_To edit a menu_**:

1. From the CMS, select **Navigation** from the sidebar, then select **Menu**. The menu manager screen appears.
2. Under the **Links Assignment** container, select a menu from the **Menu** drop-down list. Your menu's links information appears.
3. Perform any desired changes, then select **Save**.

**_To delete a menu_**:

1. From the CMS, select **Navigation** from the sidebar, then select **Menu**. The menu manager screen appears.
2. Under the **Links Assignment** container, select a menu from the **Menu** drop-down list.
3. Select the **- Delete** button.

### Manage footers

Once you have created your links, you can manage your footer. A footer can have multiple columns, each with multiple links. The columns appear horizontally, while the links stack vertically underneath each column.

> **Note**: If you use only a single column, the links will align vertically into a row.

**_To create a footer column_**:

1. From the CMS, select **Navigation** from the sidebar, then select **Footer**. The footer management screen appears.
2. Select the **+ Add** button from the **Link Assignment** container. The column creation window appears.
3. Enter a name for your column, then select **Confirm**. Your new column appears in the **Link Assignment** container.

**_To assign links to a column_**:

1. From the CMS, select **Navigation** from the sidebar, then select **Footer**. The footer management screen appears.
2. Drag and arrange **Available Links** into the desired footer. The order in which you arrange the links is the order in which the links will appear on the SubCon Site.

**_To arrange the order of your footer columns_**:

1. From the CMS, select **Navigation** from the sidebar, then select **Footer**. The footer management screen appears.
2. Navigate to the **Footer Columns Display Order** container, then arrange your footer columns. The top-most column appears on the left of your SubCon Site, while the bottom-most column appears to the right of your SubCon Site.
3. Select **Save**.

----------

### Manage notifications

You can easily create and manage notifications and their content. The creation of the actual notification is done from the CMS Admin section while the creation of the notification's content (i.e. the actual notification message) is done from the Notifications section.

**_To create a notification_**:

1. From the CMS, select **Admin** from the sidebar, then select **Notification Management**. The notification management screen appears.
2. Select the **+ Add** button. The notification fields become active.
3. Fill in the following fields:
    Lookup name - Enter a short name to use as a lookup.
    Type - Select the notification type (e.g. error, success, warning, etc.).
    Pages - Assign this notification to various pages. Select the box, then select or type the page name.
    Description - Enter a formal description of the notification.
4. Select **Submit**.

**_To edit a notification_**:

1. From the CMS, select **Admin** from the sidebar, then select **Notification Management**. The notification management screen appears.
2. Choose the desired notification from the **Notification** drop-down menu. The fields populate with that notification's information.
3. Complete your desired edits, then select **Submit**.

**_To delete a notification_**:

1. From the CMS, select **Admin** from the sidebar, then select **Notification Management**. The notification management screen appears.
2. Choose the desired notification from the **Notification** drop-down menu.
3. Select the **- Delete** button.

**_To edit the content of a notification_**:

1. From the CMS, select **Notifications** from the sidebar. The notification content management screen appears.
2. Choose the desired page from the **Filter by Page** drop-down menu. Every notification assigned to that page appears in a table.
3. Navigate to the desired notification and select **Edit**. The **Message** field become active.
4. Enter a notification message into the **Message** field, then select **Save**.

----------

### Manage newspapers (divisions) and newspaper groups

You can easily add, edit and delete newspapers and newspaper groups in the CMS.

**_To add a newspaper_**:

1. From the CMS, select **Admin** from the sidebar, then select **Newspaper Management**. The newspaper management screen appears.
2. Select the **+ Add** button. The newspaper fields become active.
3. Fill in the following fields:
    Name - Enter a name for the newspaper
    ParentDivision - Choose a client for the newspaper (typically there is only one option available).
    PaperCode - Enter the circulation code for the newspaper.
    SpURL - Enter the subscription panel URL.
    Default SubCon Admin presentation - Choose the default Subscription Panel Presentation to use.
    Id - Enter the newspaper's ID code
    Active - Toggle to `On` to set the newspaper to active.
4. Select **Save**.

**_To edit a newspaper_**:

1. From the CMS, select **Admin** from the sidebar, then select **Newspaper Management**. The newspaper management screen appears.
2. Select the desired newspaper (division) from the **Select a Division** drop-down menu. The newspaper's information populates in the fields below.
3. Perform your desired edits, then select **Save**.

**_To delete a newspaper_**:

1. From the CMS, select **Admin** from the sidebar, then select **Newspaper Management**. The newspaper management screen appears.
2. Select the desired newspaper (division) from the **Select a Division** drop-down menu.
3. Select the **- Delete** button. The newspaper is removed from your system.

> **NEWSPAPER GROUP NOTE**: To create, edit, or delete a **Newspaper Group**, follow the preceding procedures at Newspaper Group Level of the CMS Hierarchy. The CMS automatically determines whether the entity is a Newspaper or Newspaper Group from the CMS Hierarchy level.

