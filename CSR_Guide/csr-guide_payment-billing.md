## Billing and Payment Management

This guide explores the payment and billing management functionality of the SubCon Admin Portal. It describes and provides instructions for each feature of the **payment/billing** tab. You can:

- view a subscription's billing status, saved payment methods, and transactions
- make payments and update payment methods
- enroll subscriptions into automatic renewal (auto-renew)
- switch auto-renew subscriptions back into invoices
- enroll/unenroll subscriptions into an electronic bill (eBill)

Tip: To quickly show an accounts current balance, select the show balance button in the upper right corner. If the displayed number is negative, the account is past due.

### Navigation

To view the **payment/billing** tab, perform a [subscription search](www.example.com), and then select the **payment/billing** tab.

(GIF OF PROCESS)

### Status Details

The **status details** section of this tab displays information about a subscription's status. These values are processed in real-time. The source column indicates which database the values come from, either Subscribe or Circulation.

| Term or phrase | Description | Source |
|-|-|-|
| Auto-renew | Indicates whether the subscription is enrolled in automatic payment renewal. Values can be either `Yes` or `No`. | Subscribe |
| Payment method type | The payment method used for the last transaction (e.g. `CreditCard` or `BankDraft`) **Note**: Will not display if subscription is enrolled in auto-renew. | Circulation |
| Current payment method | The last four digits of the payment's account number. **Note**: will only display if subscription is enrolled in auto-renew. | Circulation |
| Paid through date | The date through which the subscription has been paid (`MM-DD-YYYY`). **Note**: Currently, paid through date and expiration date will always be the same. | Subscribe |
| Expiration date | The date at which the subscription expires (`MM-DD-YYYY`). **Note**: Currently, paid through date and expiration date will always be the same. | Subscribe |
| eBill | Indicates whether the subscription is enrolled in an electronic/paperless billing system. If so, the email address that is invoiced will display here. | Subscribe |

### Saved Payment Methods

The **saved payment methods** grid displays a subscription's saved payment methods. The values come in real-time from the circulation system.

| Term or phrase| Description |
|-|-|
| Payment method type | Indicates the type of saved payment method (e.g., `CreditCard` or `BankDraft`).
| Account number | Either the credit card or bank draft's account number. |

### Subscription Financial Transactions

The **subscription financial transactions** grid displays a subscription's transaction history. Use the drop-down menu to apply length filters. Select the icon in the details column to view detailed transaction information.

The values come in real-time from the circulation system.

**Transaction Terms**

| Term or phrase | Description |
|-|-|
| Amount | The total amount of the transaction. |
| Transaction type | Indicates whether the transaction is auto-renew (`AutoPay`), a one-time payment (`Payment`), or a declined payment (`PymtDecline`).  |
| Payment method | Indicates whether the payment method was `Bank Account`, `Credit Card`, `Check` or `Cash`. |
| Status | Indicates whether the payment was completed (`Captured`) or declined (`Declined`).  |
| Add date | The date the transaction was made. |
| Details | Select this icon to view detailed transaction information.  |

**Detailed Transaction Information**
To view these details, select the icon in the details column. **Important**: The payment amount includes any adjustments, coupons or discounts.

The values come in real-time from the circulation system.

| Term | Description |
|-|-|
| Transaction ID | Transaction's identification number |
| Payment amount | Cost of the subscription before tax and tip. |
| Tax amount | The tax of the subscription. |
| Tip | Optional tip added on top of the subscription. |
| Adjustment amount | A credit or debit made to the account’s balance but unrelated to the subscription cost (e.g. an activation fee). There can be multiple fees. Only the total displays. **Note**: This value will only be included in the total amount _if_ cash flag = `Yes` in the circulation system. |
| Coupon amount | A percent or flat amount reduction off the price of a subscription indicated by a detachable voucher. **Note**: This value is _not_ included in the total amount. |
| Discount | The difference in price from the immediately previous transaction. |
| Bank name | The name of the subscriber's bank. Note: This field only appears if payment method is `Check`. |
| Check number | The check number of the particular payment. Note: This field only appears if payment method is `Check`. |

### Payments

#### Make a payment

You can make one-time payments only on subscriptions not currently enrolled in auto-renew.

You can only make one payment every 24 hours. 

To make a payment:

1. Select the **make a payment** button.
2. Choose a payment term and rate.
3. Confirm whether the subscriber wishes to add a tip. 
4. Confirm whether the subscriber wishes to enroll in auto-renew. If so, check the **auto-renew** box. The activation fee is a flat rate charged each time a payment is made. The fee amount is configurable in the Subscribe database.
5. Confirm the disclaimer text to the subscriber and select **pay with credit card**.
6. Enter the credit card details and select **submit**. The request is processed in real-time with the circulation system.

### Auto-renew

#### Enroll in auto-renew

You cannot enroll a subscription into auto-renew if a payment has been made in the last 24 hours.

To enroll a subscription into auto-renew:

1. Select the **auto-renew sign up** button. The sign up form appears.
2. Confirm a payment term with subscriber. `Term` is the number of weeks per billing cycle. `Total payment` is the amount due today.
3. Confirm the disclaimer text to the subscriber and select **pay with credit card**.
4. Enter the credit card details and select **submit**. The request is processed in real-time with the circulation system. 

The new payment method will appear in the saved payment methods grid after selecting the refresh button.

#### Update a payment method

You can update the payment methods only of subscriptions enrolled in auto-renew. 

This feature allows you to update a payment method (e.g. switching credit cards) or change a payment method (e.g. switch from a credit card to a bank account). 

To update or change a payment method:

1. Select the **update payment method** button. The feature appears.
2. Confirm the disclaimer text with the subscriber.
3. Determine if the subscriber will update or change their payment method. If only updating, select the **continue with…** button. If changing, select the **switch to…** button.
4. Fill in the new payment’s information.
5. Select either **submit** or **save**, depending on which option the subscriber chose. The updated payment information is processed in real-time with the circulation system.

The new payment method will display in the payment method grid on the next published day.

#### Switch to invoice

To switch to invoices:

1. Select the **switch to invoice** button.
2. Confirm the disclaimer text with the subscriber.
3. Select **submit**. The updated information is processed in real-time with the circulation system.

### eBill

#### Enroll for an eBill

You cannot enroll subscriptions for an eBill if they are enrolled in auto-renew.

To enroll a subscription for an eBill:

1. Select the **eBill sign up** button. The sign up form appears.
2. Verify the email address. If a subscription email is recorded, that will automatically populate here.
3. Confirm the disclaimer text to the subscriber and select **submit**. This request is processed in real-time with the circulation system. The new email address will populate in the eBill field under Status Details.

#### Update an eBill email address

Once a subscription has been enrolled into eBill, the corresponding email address can be updated in the **status details** section. Select the pencil icon the eBill row and enter a new email address. Any change will occur in real-time.

#### Unenroll from an eBill

To unenroll a subscription from an eBill:

1. Select the **cancel eBill** button. 
2. Confirm your decision and select **OK**. This request is processed in real-time with the circulation system. The email address will be removed from the eBill field under **Status Details**.

> [!NOTE]
> The information displayed in this tab returns in real-time from our circulation databases.
> You must have NCS Circ `2018.5` or greater for current integration.

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>