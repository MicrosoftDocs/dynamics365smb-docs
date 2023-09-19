---
title: Set up and use the Shopify Connector
description: Various integration scenarios for demonstrating workflow between Shopify and Business Central
ms.date: 06/21/2022
ms.topic: article
ms.service: dynamics365-business-central
ms.search.form: 30101, 30102, 30106, 30107, 30113, 30115, 30126
ms.reviewer: solsen
author: brentholtorf
ms.author: bholtorf
---

# Walkthrough: Set up and use the Shopify Connector

This section demonstrates some typical scenarios and takes you through the steps to test or train users on the workflow of the integrated [!INCLUDE[prod_short](../includes/prod_short.md)] and the Shopify store.

## Prerequisites 

### Shopify

You must have:

- A Shopify account
- A Shopify online store

Learn more about how to create Shopify trials and recommended settings at [Creating and Setting Up Shopify Account](shopify-account.md).

### Business Central

You must have a [!INCLUDE[prod_short](../includes/prod_short.md)] account. 

For example, you can create demo account or start trial. Learn more at [Prepare Demonstration Environments of Dynamics 365 Business Central](/dynamics365/business-central/dev-itpro/administration/demo-environment) and [Sign up for the trial](../trial-signup.md). 

## Connect Business Central to the Shopify shop

In [!INCLUDE[prod_short](../includes/prod_short.md)], do the following steps:

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, and then choose the related link.
2. Choose the **New** action.
3. In the **Code** field, enter `DEMO1`.
4. In the **Shopify URL** field, enter the URL to the online shop that you want to connect to.
5. Activate the **Enabled** toggle, review and accept the terms and conditions.

Configure the Shopify shop as described in the following steps:

1. Turn off the **Allow Background Syncs** toggle.
2. Select *To Shopify* in the **Sync Item** field.
3. Select *To Shopify* in the **Sync Item Images** field.
4. Turn on the **Sync Item Attributes** toggle.
5. Turn on the **Inventory Tracked** toggle.
6. Select *Deny* in the **Default Inventory Policy** field.
7. Turn on the **Auto Create Unknown Customers** toggle.
8. Fill in the **Customer Template Code** field with the appropriate template.
9. Fill in the **Shipping Cost Account**, the **Tip Account** with the revenue account. For example, in the US, use `40100`.
10. Turn on the **Auto Create Orders** toggle.

Configure location mapping:

1. Choose the **Locations** action to open **Shopify Shop Locations**.
2. Choose the **Get Shopify Locations** action to import all locations defined in the Shopify. Select your default location in Shopify
3. In the **Location Filter**, enter `''|EAST|MAIN`.
4. Turn on the **Default Product Location** toggle.
5. Select *Projected Available Balance at Today* in the **Stock Calculation** field to enable inventory sync for selected Shopify location.

## Walkthrough: Start selling products online

### Scenario

Let's say that you want to try Shopify as an online store without spending much time on setting up things, especially because you already maintain your items in [!INCLUDE[prod_short](../includes/prod_short.md)] properly. After you launch your Shopify online store, you immediately get new customers who are happy with your shop and their buying experience. So, they decide to leave tips at checkout.

### Steps

In [!INCLUDE[prod_short](../includes/prod_short.md)] go through the following steps:

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and choose the related link.
2. Choose the **Add Items** action.
3. In the **Shop Code** field, enter *DEMO1*.
4. Set the filter `CHAIR` on the **Item Category Code** field (add filter field if necessary).
5. Select **OK** and wait until initial synchronization of items and prices is completed.
6. Choose the **Sync Product Images** action.
7. Choose the **Sync Inventory** action.

In **Shopify online store**
> [!Tip]  
> Open **Shopify admin**, by navigating to URL specified in the **URL** field of the **Shopify Shop Card** page. Then choose eye icon next to the **Online Store** sales channel, located in the sidebar of **Shopify admin**. 

Open the product catalog. Notice:

* Product titles, images, and prices.
* Availability indicator (sold out for out-of-stock products).

Choose any product that can be sold, for example, the `BERLIN Swivel Chair, yellow`. Notice that the description contains item attributes.

Choose the **Buy it now** button and proceed to checkout.

1. In the **Email or mobile phone number** field, enter `cl@contoso.com` (or email where you want to receive order and shipping confirmations).
2. In the **First name** and **Last name**, enter `Claudia Lawson`.
3. Enter the local address.
4. Choose the **Save this information for next time** checkbox.
5. Choose the **Continue to shipping** button.
6. Keep `Standard` as the shipping method and then choose the **Continue to payment** button.
7. Select `10%` tip.
8. In the **Credit Card** field, enter `1` if you use *(for testing) Bogus Gateway*, or enter `5555 5555 5555 4444` if you use *Shopify payments* in test mode.
9. Fill in the **Name on card** field.
10. In the **Expiration date** field, enter the current month/year.
11. In the **Security code**, enter `111`.
12. Choose the **Pay now** button.

In [!INCLUDE[prod_short](../includes/prod_short.md)], do the next steps:

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Orders**, and then choose the related link.
2. Choose the **Sync Orders From Shopify** action.
3. Choose **OK**.

The imported order is ready for processing.

1. Select the imported order to open the **Shopify Order** window.
2. Notice that the new customer and sales order are created.
3. Explore the **Risk** and **Shipping Cost** actions.
4. Choose the **Sales Order** action to open the **Sales Order** window. Sales order is a demand, that if necessary, can be covered with assembly, production, or by purchase with the help of the planning engine. It also supports various warehouse handling processes with complete separation of duties.
5. Choose the **Reopen** action.
6. In the **Agent** field, enter `DHL`.
7. In the **Package Tracking No.**, enter `123456789`.
8. Choose the **Post** action, keep **Ship and Invoice** option, and then choose the **OK** button.

Now physical and financial data is registered in [!INCLUDE[prod_short](../includes/prod_short.md)]. It’s time to notify Shopify about the changes.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sync Shipments to Shopify**, and choose the related link.
2. Choose **OK**.

In **Shopify Admin** notice that the order is now marked as *Fulfilled*. You can also review Shipment details and see the Tracking URL there. If you run **Sync Orders From Shopify** again, the order will be archived in both systems.

## Walkthrough: Invite your customers to your new online store

### Scenario

After a successful quick launch of your new online store, you want your current customers to visit it and start placing orders.

### Steps

In [!INCLUDE[prod_short](../includes/prod_short.md)], do the following steps:

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, and choose the related link.
2. Select the **DEMO1** Shop for which you want to synchronize customers to open the **Shopify Shop Card** page.
3. Choose the **Sync Customers** action.

In **Shopify Admin** notice that the customers were imported. Open one of the customers and notice that the first and last names of the customer are coming from the **Contact Name** field of the **Customer Card**. The company name can be found in the default address, linked to the customer. Choose **Send account invite** to invite the customer.

## Walkthrough: Fine tuning of item management

### Scenario 

You'll like to add more flexibility and control to your processes around items management. You want to improve product description and like to add more review steps before products become available to end-customer.

### Steps

In [!INCLUDE[prod_short](../includes/prod_short.md)], do the following steps:

Prepare data.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customer Price Group**, and choose the related link.
2. Add new price group. In the **Code** field, enter `SHOPIFY`.
3. Close the **Customer Price Group** window.
4. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and choose the related link.

Select item **1896-S, Athens Desk** and run following steps.

1. Choose the **Variants** action and then add two variants `PREMIUM, Athens Desk, Premium edition` and `ESSENTIAL, Athens Desk, Essential edition`.
2. Choose the **Extended Text** action, create a new extended text valid for all language codes. In the **Description** field, enter `Shopify`. 
3. Add following text with HTML tags: `<b>Simple stylish design</b> blends with any ensemble. <i>Available in two editions.</i>`. Close the **Exteneded Text** page and return to item card.
4. Choose the **Sales Prices** action and add new prices as shown in the following table:

  |Line|**Sales Type**|**Sales Code**|Type|Code|Variant Code<br>(add the field via personalization)|Unit Price|
  |------|------------|------------|------------|------------|------------|------------|
  |1|Customer Price Group|SHOPIFY|Item|1896-S|ESSENTIAL|700|
  |2|Customer Price Group|SHOPIFY|Item|1896-S|PREMIUM|1000|

5. Choose **Sales Discounts** action and add a new discount:

* **Sales Type** *Customer Disc. Group*
* **Sales Code** *RETAIL*
* **Type** *Item*
* **Code** *1896-S*
* **Unit of Measure Code** *PCS*
* **Line Discount %** *10*

6. Choose **Item References** action and the following add lines:

  |Line|**Reference Type**|**Reference No.**|Variant Code|
  |------|------------|------------|------------|
  |1|Barcode|77777777|ESSENTIAL|
  |2|Barcode|11111111|PREMIUM|


Select the item **1920-S, ANTWERP Conference Table** and run following steps.

1. Choose **Adjust Inventory** and in the **New Inventory** field, enter `100` for the locations *EAST* and *WEST*. 
2. Choose **OK**.

Adjust the synchronization settings.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, and choose the related link.
2. Select the *DEMO1* Shop for which you want to synchronize items to open Shopify Shop Card page.
3. Select *SHOPIFY* in the **Customer Price Group** field.
4. Select *RETAIL* in the **Customer Discount Group** field.
5. Enable the **Sync Item Extended Text** field.
6. Select *Item No.+ Variant Code* in the **SKU Mapping** field.
7. Select *Draft* in the **Status for Created Products** field.
8. Select *Status to Archived* in the **Action for Removed Product** field.

Run the synchronization.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, and choose the related link.
2. Select the *DEMO1* Shop for which you want to synchronize items to open the **Shopify Shop Card** page.
3. Choose the **Products** action to open **Shopify Products** window.
4. Choose the **Add Items** action.
5. Set the filter *TABLE|DESK* on the **Item Category Code** field.
6. Choose the **Sync Product Images** action.
7. Choose the **Sync Inventory** action.

Products are added. Notice that the status is set to *Draft*, and therefore items aren't visible in the Shopify online store.

1. Select the line with item *1920-S, ANTWERP Conference Table*. In the **SEO Title**, enter `Rectangular meeting table Antwerp, 10 seats, black`.
2. Select *Active* in the **Status** field.
3. Select the line with item *1906-S, ATHENS, Mobile Pedestal* and then choose the **Delete** action.

In **Shopify Admin** notice that all products have different statuses.

* *ANTWERP Conference Table* is *Active* because we changed status in **Shopify Product** window.
* *ATHENS Desk* is *Draft* because we configured the default status for all added products to be *Draft*.
* *ATHENS Mobile Pedestal* is *Archived* because we configured the shop to automatically assign status *Archived* for deleted products.

Notice that Inventory for ANTWERP Conference Table is 100, because we configured system to use inventory only from two locations MAIN and EAST. Inventory on other locations (WEST) is ignored.

* Open *ANTWERP Conference Table*, notice **Custom Type**, **Vendor**, **Weight**, **Cost per item** fields, and **Search engine listing preview** section.
* Open *Athens Desk*, scroll down to **Variants** section, and notice how **SKU** is populated.
* Choose **Edit** to review barcode and prices.
* Change the status of *Athens Desk* to *Active* and choose **Preview** action.

In the **Shopify online store** open the product catalog, find the *ATHENS Desk*  product. Notice that different options are available. For different options, prices are different. Pay attention to discount information.

## Walkthrough: Import items from Shopify

### Scenario 

You already have a successful online store and would like to start using [!INCLUDE[prod_short](../includes/prod_short.md)] as business management software. You would like to import as much data from Shopify as possible. 

### Steps

This is a continuation of [Walkthrough: Start selling products online](walkthrough-setting-up-and-using-shopify.md#walkthrough-start-selling-products-online). You can also try with your own data, for example your Shopify store or sandbox.

In [!INCLUDE[prod_short](../includes/prod_short.md)], do the following steps:

#### Prepare data

1. Switch to a free 30-day trial without sample data. For more information, see [Add your own data to an empty trial](/dynamics365/business-central/dev-itpro/administration/trials-subscriptions#add-your-own-data-to-an-empty-trial-company).
2. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, and then choose the related link.
3. Choose the **New** action.
4. In the **Code** field, enter `DEMO2`.
5. In the **Shopify URL** field, enter the URL to the online shop that you want to connect to.
6. Activate the **Enabled** toggle, review and accept the terms and conditions.

Configure the Shopify shop as described below in the next steps:

7. Deactivate the **Allow Background Syncs** toggle.
8. Select *From Shopify* in the **Sync Item** field.
9. Enable the **Auto Create Unknown Items** toggle.
10. Fill in the **Item Template Code** field with the appropriate template.
11. Select *From Shopify* in the **Sync Item Images** field.
12. Select *All Customers* in the **Customer Import from Shopify**.
13. Enable the **Auto Create Unknown Customers** toggle.

#### Run the synchronization

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, and choose the related link.
2. Select the *DEMO2* Shop for which you want to synchronize data to open the **Shopify Shop Card** page.
3. Choose the **Sync Products** action.
4. Choose the **Sync Product Images** action.
5. Choose the **Sync Customers** action.

### Results

* Shopify Products are imported. To verify, choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and choose the related link.
* Items with images are created. To verify, choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item**, and choose the related link.
* Shopify Customers are imported. To verify, choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Customers**, and choose the related link.
* Customers are created. To verify, choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and choose the related link.


## See Also

[Get Started with the Shopify Connector](get-started.md)  
