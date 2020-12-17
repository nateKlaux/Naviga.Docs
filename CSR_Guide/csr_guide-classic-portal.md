## Redirect to classic portal

For any features not yet implemented in the _CSR Portal_, you can use the **lookup classic portal** button to navigate to the classic portal.

### Prerequisites

Before you can redirect to the classic portal, complete the following prerequisites:

- Configure NCS to support the CTI API. Provide the API URL to Naviga for implementation.
- Submit database names to Naviga for implementation.
- Establish a reference between the classic portal and the CSR portal. Instructions for this task are below.
- Log into both instances _before_ selecting the **lookup classic portal** button.

To establish a reference between the classic portal and the CSR portal: 
- Configure usernames and `KeyID` in all NCS Circ instances.
- Add the CSR username to the Subscribe Portal.  
- Add the NCS `KeyID` to the CSR username in Subscribe Portal:
   1. Select **users** in the CSR Portal.
   2. Select the pencil icon that corresponds to the desired username.
   3. Add the NCS `KeyID` in the **key id** field.
   4. Select **save**.

### Redirect to the classic portal

The **lookup classic portal** button is located on any **subscription search** tab. Perform a [subscription search](www.example.com), then select the button from the bottom of any tab.

> [!NOTE]
> The information displayed in this tab returns in real-time from our circulation databases.
> You must have NCS Circ `2018.5` or greater for current integration.
