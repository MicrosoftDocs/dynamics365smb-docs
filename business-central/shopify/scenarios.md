---
title: Test and training scenarios
description: In this walkthrough, we take you through various integration scenarios between Shopify and Business Central
ms.date: 03/21/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
manager: 
---


# Test and training scenarios

## Preparation

Start by creating an Azure Active Directory tenant and getting administration login and password. For more information, see [Preparing demonstrations of [!INCLUDE[prod_short](../includes/prod_short.md)]](/dynamics365/business-central/dev-itpro/administration/demo-environment.md).
You can stop at step 6, once you got the administrator account that you got as part of your demo account, typically called something like *admin@CRMbc123456.onmicrosoft.com*.

Navigate to https://www.shopify.com/ and use this administrator account to sign for a free 14-day trial.

In the **Shopify Admin** of created shop do following **Settings**:
*	Disable **Automatically archive the order** in the **Order Processing** section of the [**Checkout**](https://www.shopify.com/admin/settings/checkout) settings in your **Shopify admin**.
*	Consider selecting *Accounts are optional* option in the **Customer accounts** section of the Checkout setting.
*	Consider selecting *Company name - Optional* option in the **Customer information** section of the Checkout setting.
*	Enable **Show tipping options at checkout** in the **Tipping** section of the Checkout setting, if you plan to demonstrate [Tipping scenario](TBD).
*	Activate *(for testing) Bogus Gateway* as test payment provider in the [**Payments**](https://www.shopify.com/admin/settings/payments) settings.

Install **Dynamics 365 Business Central** app to your Shopify online store
1. Find [Dynamics 365 Business Central](https://fwlink/?=TDB) app on the [Shopify AppStore](https://apps.shopify.com/).
2. Choose **Add App** button. Login into your Shopify account if prompted. 
3. Review privacy and permissions details and choose **Install App** button. You can find and open installed **Dynamics 365 Business Central** app in the Apps section on the sidebar of **Shopify admin**.
4. Choose **Sign up now** to start [!INCLUDE[prod_short](../includes/prod_short.md)] trial, use administrator account.

In created [!INCLUDE[prod_short](../includes/prod_short.md)] do following:
1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and then choose the related link.
2. Choose the **New** action.
3. Fill *DEMO1* in the **Code** field.
4. Fill in **Shopify URL** field with URL to online shop you want to connect to.
5. Choose the **Request Access** action.

Configure Shopify shop as describen below:
1. Enable the **Log Enabled** toggle.
2. Disable the **Allow Background Syncs** toggle.
3. Select **To Shopify** in the **Sync Item Images** field.
4. Enable the **Sync Item Attributes** toggle.
6. Enable **Inventory Tracked** toggle.
7. Select **Deny** in the **Default Inventory Policy**
8. Enable the **Auto Create Unknown Customers** toggle
9. Fill in the **Customer Template Code** field with appropriate template
10. Fill in the **Shipping Cost Account**, the **Tip Account** with revenue account. For example, in US use *40100*.
11. Enable the **Auto Create Orders** toggle.

Configure location mapping.
1. Choose the **Locations** action to open **Shopify Shop Locations**.
2. Choose the **Get Shopify Locations** action to import all locations defined in the Shopify. 
3. Fill in *''|EAST|MAIN* the **Location Filter**.
4. Remove toggle from the **Disabled** field to enable inventory sync for selected Shopify location



## Walkthrough: Start selling products online

### Scenario
You want try Shopify as an online store and don’t want to spend much time on setting things up, especially because you already maintain your items in [!INCLUDE[prod_short](../includes/prod_short.md)] properly. You immidiatelly get new customer, who are so happy with your shop that they decide to leave some tips.

### Steps
In **[!INCLUDE[prod_short](../includes/prod_short.md)]**

1.	Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and then choose the related link.
2.	Choose the **Add Items** action.
3.	Fill *DEMO1* in the **Shop Code** field. 
4.	Set filter *CHAIR* on the **Item Category Code** field (add filter field if necessary).
5.	Click **ok** and wait till initial synchronization of items and prices is competed.
6.	Choose the **Sync Product Images** action.
7.	Choose the **Sync Inventory** action.

In **Shopify online store**.
Open product catalog. Notice:
- Product titles, images, prices.
- Availability indicator.
Open *MEXICO Swivel Chair, black*. Notice that description contains with item attributes

Choose **Buy it now** button and proceed to checkout.

1. Fill *cl@contoso.com* (or email where you want to receive order and shipping confirmations) in **Email or mobile phone number**
2. Fill *Claudia Lawson* in the **First name** and **Last name**.
3. Fill in local address.
4. Enable **Save this information for next time** checkbox.
5. Choose **Continue to shipping** button.
6. Keep *Standard* shipping method and choose **Continue to payment** button.
7. Select 10% tip
8. Fill *1* in the **Credit Card** field.
9. Fill in the **Name on card** field.
10. Fill in the **Expiration date** field with current month/year.
11. Fill *111* in the **Security code**.
12. Choose **Pay now** button.

In **[!INCLUDE[prod_short](../includes/prod_short.md)]**

1.	Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Orders**, and then choose the related link.
2.	Choose the **Sync Orders From Shopify** action.
3.	Click ok.

Imported order is ready for processing.
1. Select imported order to open **Shopify Order** window.
2. Notice that new customer was created, as well as sales order.
3. Explore **Risk** and **Shipping Cost** actions.
4. Choose the **Sales Order** action to open **Sales Order** window.
Sales order is a demand, that if necessary, with help of planning engine can be covered with Assembly, Production, or by Purchase. It also supports various warehouse handling processes with complete separation of duties. 
4. Choose the **Reopen** action.
5. Fill *DHL* in the **Agent** field.
6. Fill *123456789* in the **Package Tracking No.**. 
7. Choose the **Post** action, keep **Ship and Invoice** option and click **Ok**.

Now physical and financial data is registered in [!INCLUDE[prod_short](../includes/prod_short.md)]. It’s time to notify Shopify about changes.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sync Shipments to Shopify**, and then choose the related link.
2. Click **Ok**.

In **Shopify Admin**. 

Notice that the order is now marked as *Fulfilled*. You can also review Shipment details and see Tracking URL there. If you run **Sync Orders From Shopify** again, order will be archived in both systems.


## Walkthrough: Invite your customers to your new online store

### Scenario
After quick success with launch of your new online store, you want your current customers to start use it for placing orders.

### Steps
In **[!INCLUDE[prod_short](../includes/prod_short.md)]**
1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and then choose the related link.
2. Select the *DEMO1* Shop for which you want to synchronize customers to open the **Shopify Shop Card** page.
3. Choose the **Sync Customers** action.

In **Shopify Admin**. 

Notice that customers were imported.
Open one of customers, notice that first name and last name are comming from the **Contact Name** field of the **Customer Card**. The company name can be found in the default address, linked to the customer.
Choose **Send account invite** to invite customer.

## Walkthrough: Fine tuning of item management

### Scenario
You would like to add more flexibility and control to your processes around managing of items. You want to imporove product description. You also want to add additional review steps, before products become available to end-customer.

### Steps
In **[!INCLUDE[prod_short](../includes/prod_short.md)]**

Prepare data.
1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customer Price Group**, and then choose the related link.
2. Add new price group. Fill *SHOPIFY* in the **Code** field. 
3. Close the **Customer Price Group** window.

1.	Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
2.	Select item *1896-S, Athens Desk*.
3.	Choose **Variants** action, and add two varians *PREMIUM, Athens Desk, Premium edition* and *ESSENTIAL, Athens Desk, Essential edition*.
4.	Choose **Extended Text**, create new extended text valid for all language codes. Fill *Shopify* in the **Description** field.
5.	Add following description with HTML tags: <b>Simple stylish design</b> blends with any ensemble. <i>Available in two editions.</i>
6.	Choose **Sales Prices**, and add new prices:

|Line|**Sales Type**|**Sales Code**|Type|Code|Variant Code<br>(add field via personalization)|Unit Price|
|------|------------|------------|------------|------------|------------|------------|
|1|Customer Price Group|SHOPIFY|Item|1896-S|ESSENTIAL|700|
|2|Customer Price Group|SHOPIFY|Item|1896-S|PREMIUM|1000|

7.	Choose **Sales Discounts**, and add new discount:
- **Sales Type** *Customer Disc. Group*, 
- **Sales Code** *RETAIL*, 
- **Type** *Item*,
- **Code** *1896-S*
- **Unit of Measure Code** *PCS*
- **Line Discount %** *10*
8. Choose **Item References** and add lines

|Line|**Reference Type**|**Reference No.**|Variant Code|
|------|------------|------------|------------|
|1|Barcode|77777777|ESSENTIAL|
|2|Barcode|11111111|PREMIUM|

9. Close **Item Card**.

10.	Select item *1920-S, ANTWERP Conference Table*.
11. Choose **Adjust Inventory** and fill *100* in the **New Inventory** field for locations *EAST* and *WEST*. Choose Ok.
12. Close **Item Card**.

Adjust synchronization settings.
1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and then choose the related link.
2. Select the *DEMO1* Shop for which you want to synchronize items to open Shopify Shop Card page.
3. Select *SHOPIFY* in the **Customer Price Group** field.
4. Select *RETAIL* in the **Customer Discount Group** field.
5. Enable the **Sync Item Extended Text** field.
6. Select *Item No.+ Variant Code* in the **SKU Mapping** field.
7. Select **Draft** in the **Status for Created Products** field.
8. Select **Status to Archived** in the **Action for Removed Product** field.

Execute sync.
1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and then choose the related link.
2. Select the *DEMO1* Shop for which you want to synchronize items to open the **Shopify Shop Card** page.
3. Choose the **Products** action to open **Shopify Products** window.
4. Choose the **Add Items** action.
5. Set filter *TABLE* on the **Item Category Code** field.
6. Choose the **Sync Product Images** action.
7. Choose the **Sync Inventory** action.

3 products are added. Notice status is set to *Draft*, hence items are not visible in the Shopify online store.
1. Select line with item *1920-S, ANTWERP Conference Table*. Fill *Rectangular meeting table Antwerp, 10 seats, black* in the **SEO Title**
2. Select *Active* in the **Status** field.
3. Select line with item *1906-S, ATHENS, Mobile Pedestal* and choose the **Delete** action.

In **Shopify Admin**. 

Notice that all products have different statuses.
- *ANTWERP Conference Table* is *Active* because we changed status in **Shopify Product** window.
- *ATHENS Desk* is *Draft* because we configured default status for all added products to be *Draft*.
- *ATHENS Mobile Pedestal* is *Archived* because we configured shop to automatically assign status *Archived* for deleted products.

Notice that Inventory for ANTWERP Conference Table is 100, because we configured system to use inventory only from two locations MAIN and EAST. Inventory on other locations (WEST) is ignored.

Open *ANTWERP Conference Table*, notice **Custom Type**, **Vendor**, **Weight**, **Cost per item** fields and **Search engine listing preview** section.
Open *Athens Desk*, scroll down to **Variants** section, notice how **SKU** is populated. 
Choose **Edit** to review barcode and prices.
Change status of *Athens Desk* to *Active* and choose **Preview** action.

In **Shopify online store**.

Open product catalog, find *ATHENS Desk*  product. Notice that different options are available. When selecting different optins prices are different. Pay attention to discount information.
