---
title: Test and training scenarios
description: Learn what to do if something when wrong during synchronization of data between Shopify and Business Central
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
2. Choose the New action.
3. Fill *DEMO1* in the **Code** field.
4. Fill in **Shopify URL** field with URL to online shop you want to connect to.
5. Choose the **Request Access** action.

Configure Shopify shop as describen below:
1. Enable the **Log Activated ** toggle
2. Disable the **Allow Background Sync** toggle
3. Select **To Shopify** in the **Sync Item Images** field.
4. Enable the **Sync Item Attributes** toggle
5. Select **Item No.** in the SKU Type
6. Enable **Inventory Tracked** toggle
7. Select **Deny** in the **Default Inventory Policy**
8. Enable the **Auto Create Unknown Customers** toggle
9. Fill in the **Customer Template Code** field with appropriate template
10. Fill in the **Shipping Cost Account**, the **Sold Gift Card Account**, the **Tip Account** with revenue account. For example, in US use *40100*.
11. Enable the **Auto Create Orders** toggle.

Configure location mapping.
1. Choose the **Locations** action to open **Shopify Shop Locations**.
2. Choose the **Get Shopify Locations** action to import all locations defined in the Shopify. 
3. Fill in *EAST|MAIN* the **Location Filter**.
4. Remove toggle from the **Disabled** field to enable inventory sync for selected Shopify location



## Walkthrough: Start selling products online

### Scenario
You want try Shopify as an online store and don’t want to spend much time on setting things up, especially because you already maintain your items in [!INCLUDE[prod_short](../includes/prod_short.md)] properly. You immidiatelly get new customer, who are so happy with your shop that they decide to leave some tips.

### Steps
In [!INCLUDE[prod_short](../includes/prod_short.md)]
1.	Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and then choose the related link.
2.	Choose the **Add Items** action.
3.	Fill *DEMO1* in the **Shop Code** field. 
4.	Set filter *CHAIR* on the **Item Category Code** field.
5.	Click ok and wait till initial synchronization of items and prices is competed.
6.	Choose the **Sync Product Images** action.
7.	Choose the **Sync Inventory** action.

In Shopify online store, open product catalog. Notice:
- Product titles and images
- Availability indicator
Open BERLIN Guest Chair, yellow. Notice:
- Description with item attributes
- Price

Choose **Buy it now** buttin and proceed to checkout.

1. Fill *cl@contoso.com* (or email where you want to receive order confirmation and shipment notification) in **Email or mobile phone number**
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

In [!INCLUDE[prod_short](../includes/prod_short.md)]
1.	Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Orders**, and then choose the related link.
2.	Choose the **Sync Orders From Shopify** action.
3.	Click ok.

Imported order is ready for processing.
1. Select inported order to open **Shopify Order** window.
2. Notice that new customer was created, as well as sales order.
3. Explore **Risk** and **Shipping Cost** actions.
4. Choose the **Sales Order** action to open **Sales Order**
Sales order is a demand, that if necessary, with help of planning engine can be covered with Assembly, Production, or by Purchase. It also supports various warehouse handling processes with complete separation of duties. 
5. Fill *DHL* in the **Agent** field.
6. Fill *123456789* in the **Package Tracking No.**. 
7. Choose the **Post** action, keep **Ship and Invoice** option and click **Ok**.

Now physical and financial data is registered in [!INCLUDE[prod_short](../includes/prod_short.md)]. It’s time to notify Shopify about changes.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sync Shipments to Shopify**, and then choose the related link.
2. Click **Ok**.

In Shopify Admin. See that order is now marked as Fulfilled. You can also review Shipment details and see Tracking URL there. If you run **Sync Orders From Shopify** again, order will be archived in both systems.


