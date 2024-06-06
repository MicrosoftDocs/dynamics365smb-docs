---
title: Set up and use the Shopify Connector
description: Various integration scenarios for demonstrating workflow between Shopify and Business Central
ms.date: 06/21/2022
ms.topic: article
ms.service: dynamics-365-business-central
ms.search.form: 30101, 30102, 30106, 30107, 30113, 30115, 30126, 30156, 30157
ms.reviewer: bholtorf
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

Learn more about how to create Shopify trials and recommended settings at [Create and Set Up a Shopify Account](shopify-account.md).

### Business Central

You must have a [!INCLUDE[prod_short](../includes/prod_short.md)] account. 

For example, you can create a demo account or start a trial. Learn more at [Prepare Demonstration Environments of Dynamics 365 Business Central](/dynamics365/business-central/dev-itpro/administration/demo-environment) and [Sign up for the trial](../trial-signup.md). 

## Connect Business Central to the Shopify shop

In [!INCLUDE[prod_short](../includes/prod_short.md)], do the following:

1. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, and then select the related link.
2. Select the **New** action.
3. In the **Code** field, enter `DEMO1`.
4. In the **Shopify URL** field, enter the URL for the online shop that you want to connect to.
5. Activate the **Enabled** toggle and then review and accept the terms and conditions.

To configure the Shopify shop, follow these steps:

1. Turn off the **Allow Background Syncs** toggle.
2. Select *To Shopify* in the **Sync Item** field.
3. Select *To Shopify* in the **Sync Item Images** field.
4. Turn on the **Sync Item Attributes** toggle.
5. Turn on the **Inventory Tracked** toggle.
6. Select *Deny* in the **Default Inventory Policy** field.
7. Turn on the **Auto Create Unknown Customers** toggle.
8. Fill in the **Customer/Company Template Code** field with the appropriate template.
9. Fill in the **Shipping Cost Account**, the **Tip Account** with the revenue account. For example, in the US, use `40210`.
10. Turn on the **Auto Create Orders** toggle.
11. Turn off the **Auto Release Sales Orders** toggle.

Configure location mapping:

1. Select the **Locations** action to open **Shopify Shop Locations**.
2. Select the **Get Shopify Locations** action to import all locations defined in the Shopify. Select entry with **Is Primary** toggle is selected.
3. In the **Location Filter**, enter `''|EAST|MAIN`.
4. Select *Projected Available Balance at Today* in the **Stock Calculation** field to enable an inventory sync for a selected Shopify location.

## Walkthrough: Start selling products online

### Scenario

Let's say that you want to try Shopify as an online store without spending much time on setup, especially because you already maintain your items in [!INCLUDE[prod_short](../includes/prod_short.md)] properly. After you launch your Shopify online store, you immediately get new customers who are happy with your shop and their buying experience. So, they decide to leave tips at checkout.

### Steps

In [!INCLUDE[prod_short](../includes/prod_short.md)], follow these steps:

1. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and select the related link.
2. Select **Add Items**.
3. In the **Shop Code** field, enter `DEMO1`.
4. Set the filter `CHAIR` on the **Item Category Code** field .
5. Turn on the **Sync Product Images** toggle.
6. Turn on the **Sync Inventory** toggle.
7. Select **OK** and wait until initial synchronization of items, prices, images and inventory is completed.

In the **Shopify online store**:
> [!Tip]  
> Open **Shopify admin** by navigating to the URL specified in the **URL** field of the **Shopify Shop Card** page. Select the eye icon next to the **Online Store** sales channel, located in the sidebar of **Shopify admin**. 

Open the product catalog. Notice:

* Product titles, images, and prices.
* Availability indicator (sold out for out-of-stock products).

Choose any product that can be sold—for example, the `BERLIN Swivel Chair, yellow`. Notice that the description contains item attributes.

Select **Buy it now** and proceed to checkout.

1. In the **Email or mobile phone number** field, enter `cl@contoso.com` (or email where you want to receive order and shipping confirmations).
2. In the **First name** and **Last name** fields, enter `Claudia Lawson`.
3. Enter the local address.
4. Select the **Save this information for next time** checkbox.
6. Keep *Standard* as the shipping method.
8. In the **Credit Card number** field, enter `1` if you use *(for testing) Bogus Gateway*, or enter `5555 5555 5555 4444` if you use *Shopify payments* in test mode.
9. Fill in the **Name on card** field.
10. In the **Expiration date** field, enter the current month/year.
11. In the **Security code**, enter `111`.
7. Optional: Select `10%` tip.
8. 12. Select **Pay now**.

In [!INCLUDE[prod_short](../includes/prod_short.md)], do the next steps:

1. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Orders**, and then select the related link.
2. Select the **Sync Orders From Shopify** action.
3. Select **OK**.

The imported order is ready for processing.

1. Select the imported order to open the **Shopify Order** window.
2. Notice that the new customer and sales orders are created.
3. Explore the **Risk** and **Shipping Cost** actions.
4. Select **Sales Order** to open the **Sales Order** window. Sales order is a demand that, if necessary, can be covered with assembly, production, or by purchase with the help of the planning engine. It also supports various warehouse handling processes with complete separation of duties.
6. In the **Agent** field, enter `DHL`. Reopen order if needed by choosing **Reopen** action.
7. In the **Package Tracking No.**, enter `123456789`.
8. Select **Post**, keep the **Ship and Invoice** option, and then select **OK**.

Now physical and financial data is registered in [!INCLUDE[prod_short](../includes/prod_short.md)]. It’s time to notify Shopify about the changes.

1. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sync Shipments to Shopify**, and select the related link.
2. Select **OK**.

In **Shopify Admin**, notice that the order is now marked as *Fulfilled*. You can also review shipment details and see the tracking URL there. If you run **Sync Orders From Shopify** again, the order will be archived in both systems.

## Walkthrough: Add your customers to your new online store

### Scenario

After a successful quick launch of your new online store, you want your current customers to visit it and start placing orders. Depending on your Shopify plan and process you can try B2B and DTC flows.

### DTC Steps

In [!INCLUDE[prod_short](../includes/prod_short.md)], do the following:

1. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Customers**, and select the related link.
2. Select **Add Customers**.
3. In the **Shop Code** field, enter `DEMO1`.
4. Set the filter `20000` on the **No.** field.
5. Select **OK** and wait until initial synchronization of customers is completed.

In **Shopify Admin**, notice that the customer was imported. Open the customers and notice that the first and last names of the customer are coming from the **Contact Name** field of the **Customer Card**. The company name can be found in the default address, linked to the customer. If you use *Classic customer accounts*, then you can select **Send account invite** to invite the customer. With *New customer accounts* a password isn't required for customers to log in, instead Shopify lets your customers log in using a one-time 6-digit verification code sent by email. 

### B2B Steps

[!INCLUDE [shopify-preview](../includes/shopify-preview.md)]

In [!INCLUDE[prod_short](../includes/prod_short.md)], do the following:

1. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Companies**, and select the related link.
2. Select **Add Company**.
3. In the **Shop Code** field, enter `DEMO1`.
4. Set the filter `30000` on the **No.** field.
5. Select **OK** and wait until initial synchronization of customers is completed.

In **Shopify Admin**, notice that both the Company and the customer was imported. Open the customers and notice the Company fact box with link to Company, location and assigned permissions. 
Select **[...]** in the **Copmany fact box, then select **Send B2B access email** to invite the customer.

## Walkthrough: Fine-tuning of item management

### Scenario 

You'd like to add more flexibility and control to your processes around items management. You want to improve product descriptions and would like to add more review steps before products become available to all customers.

### Steps

In [!INCLUDE[prod_short](../includes/prod_short.md)], do the following:

Prepare data.

1. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customer Price Group**, and select the related link.
2. Add a new price group. In the **Code** field, enter `SHOPIFY`.
3. Close the **Customer Price Group** window.
4. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and select the related link.
5. Select item *1896-S, Athens Desk* and then follow these steps:

6. Select the **Variants** action and then add two variants: `PREMIUM, Athens Desk, Premium edition` and `ESSENTIAL, Athens Desk, Essential edition`.
7. Select the **Marketing Text** action and use the **Draft with Copilot**  to get creative and engaging text. If marketing text suggestion is not enabled, just enter: '**Simple stylish design** blends with any ensemble. *Available in two editions.*'. 
8. Select the **Sales Prices** action and add new prices as shown in the following table:

   |Line|Sales Type|Sales Code|Type|Code|Variant Code<br>(add the field via personalization)|Unit Price|
   |------|------------|------------|------------|----------------|------------|------------|
   |1|Customer Price Group|SHOPIFY|Item|1896-S|ESSENTIAL|700|
   |2|Customer Price Group|SHOPIFY|Item|1896-S|PREMIUM|1000|

9. Select the **Sales Discounts** action and add a new discount:

   * **Sales Type** *Customer Disc. Group*
   * **Sales Code** *RETAIL*
   * **Type** *Item*
   * **Code** *1896-S*
   * **Unit of Measure Code** *PCS*
   * **Line Discount %** *10*

10. Select the **Item References** action and the following add lines:

   |Line|Reference Type|Reference No.|Variant Code|
   |------|------------|------------|------------|
   |1|Barcode|77777777|ESSENTIAL|
   |2|Barcode|11111111|PREMIUM|

11. Select the item *1920-S, ANTWERP Conference Table* and then follow these steps:
12. Select **Adjust Inventory** and in the **New Inventory** field, enter `100` for the locations *EAST* and *WEST*. 
13. Select **OK**.

Adjust the synchronization settings.

1. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, and select the related link.
2. Select the `DEMO1` shop for which you want to synchronize items to open the **Shopify Shop Card** page.
3. Enable the **Sync Marketing Text** field.
4. Select *Item No.+ Variant Code* in the **SKU Mapping** field.
5. Select *Continue* in the **Default Inventory Policy** field.
6. Select *Draft* in the **Status for Created Products** field.
7. Select *Status to Archived* in the **Action for Removed Product** field.
8. Select *SHOPIFY* in the **Customer Price Group** field.
9. Select *RETAIL* in the **Customer Discount Group** field.
 
Run the synchronization.

1. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, and select the related link.
2. Select the `DEMO1` shop for which you want to synchronize items to open the **Shopify Shop Card** page.
3. Select **Products** to open the **Shopify Products** window.
4. Select the **Add Items** action.
5. Set the filter *TABLE|DESK* on the **Item Category Code** field.
6. Turn on the **Sync Product Images** toggle.
7. Turn on the **Sync Inventory** toggle.
8. Select **OK** and wait until initial synchronization of items, prices, images and inventory is completed.

Products are added. Notice that the status is set to *Draft*, and therefore items aren't visible in the Shopify online store.

1. Select the line with item *1920-S, ANTWERP Conference Table*. In the **SEO Title**, enter `Rectangular meeting table Antwerp, 10 seats, black`.
2. Select *Active* in the **Status** field.
3. Select the line with item *1906-S, ATHENS, Mobile Pedestal* and then select **Delete**.

In **Shopify Admin**, notice that all products have different statuses.

* *ANTWERP Conference Table* is *Active* because we changed its status in the **Shopify Product** window.
* *ATHENS Desk* is *Draft* because we configured the default status for all added products to be *Draft*.
* *ATHENS Mobile Pedestal* is *Archived* because we configured the shop to automatically assign status *Archived* for deleted products.

Notice that Inventory for ANTWERP Conference Table is 100, because we configured the system to use inventory only from two locations, MAIN and EAST. Inventory on another location (WEST) is ignored.

* Open *ANTWERP Conference Table*, notice the **Custom Type**, **Vendor**, **Weight**, and **Cost per item** fields, and the **Search engine listing preview** section.
* Open *Athens Desk*, scroll down to the **Variants** section, and notice how **SKU** is populated.
* Select **Edit** to review barcode and prices.
* Change the status of *Athens Desk* to *Active* and select **Preview**.

In the **Shopify online store**, open the product catalog and find the *ATHENS Desk* product. Notice that different options are available. For different options, prices are different. Pay attention to discount information.

### Additional steps for B2B

[!INCLUDE [shopify-preview](../includes/shopify-preview.md)]

You can configure connector to create and assign catalog for exported Companies automatically. The steps below are useful if you want more precise control of what is available for B2B customers.

In **Shopify Admin** Create and assign catalog.

1. Select **Products** and then **Catalogs** in the sidebar of **Shopify admin**.
2. Create catalog for Specific products. Give in title 'B2B'. 
3. Choose **Manage** and then **Manage products and pricing**.
4. Select *Excluded* filter, find *ATHERN Desk* and choose **Include in catalog**.
5. Select **Customers** and then **Companies** in the sidebar of **Shopify admin**.
6. Select *School of Fine Art* and choose **[...]** and then **Add catalogs** and add *B2B* catalog created earlier.

In [!INCLUDE[prod_short](../includes/prod_short.md)], do the following:

Prepare data.

1. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and select the related link.

2. Select item **1896-S, Athens Desk** and then follow these steps:

3. Select the **Sales Discounts** action and add a new discount:

   * **Sales Type** *Customer Disc. Group*
   * **Sales Code** *LARGE ACC*
   * **Type** *Item*
   * **Code** *1896-S*
   * **Unit of Measure Code** *PCS*
   * **Line Discount %** *25*

4. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Catalogs**, and select the related link.
5. Select **Get Catalogs**.
6. In the **Shop Code** field, enter `DEMO1`.
7. Select entry with name *B2B* catalog for which you want to synchronize prices.
8. Enable the **Sync Prices** toggle.
9. Select *SHOPIFY* in the **Customer Price Group** field.
10. Select *LARGE ACC* in the **Customer Discount Group** field.
11. Choose **Sync Prices** and wait until synchronization of prices is completed.

In **Shopify Admin**, explore prices for *B2B* catalog.

In the **Shopify online store**, open the product catalog and find the *ATHENS Desk* product. Note prices are discount information.

## Walkthrough: Check out and order synchronization for Individual buyer and Company representative
This is a continuation of [Walkthrough: Start selling products online](walkthrough-setting-up-and-using-shopify.md#walkthrough-start-selling-products-online). You can also try with your own data—for example, your Shopify store or sandbox.

Individual buyer

1. In the **Shopify online store**. Choose **Account** icon. Enter email you have access to.
2. Log in using a one-time 6-digit verification code sent by email you entered.
3. Explore product catalog, you should be able to see all products with retail prices.
4. Select Essential variant and select **Buy it now** and proceed to checkout.
5. Fill in the **First name** and **Last name** fields.
6. Enter the local address.
7. Keep *Standard* as the shipping method.
8. In the **Credit Card Number** field, enter `1` if you use *(for testing) Bogus Gateway*, or enter `5555 5555 5555 4444` if you use *Shopify payments* in test mode.
9. In the **Expiration date** field, enter the current month/year.
10. In the **Security code**, enter `111`.
11. Fill in the **Name on card** field.
12. Select **Pay now**.
 
Company representative

[!INCLUDE [shopify-preview](../includes/shopify-preview.md)]

1. In **Shopify Admin**.
2. Select **Customers** and then **Companies** in the sidebar of **Shopify admin**.
3. Open *School of Fine Art* entry.
4. Choose **[...]** in the **Shcool of Fine Art** faxt box and then **Edit payment terms** and select *Due on fulfillment*.
5. Choose **[...]** in the **Customers** faxt box and then **Add customer** and add one with email you used to log in to the store earlier.
6. In the **Shopify online store**. Choose **Account** icon. Enter email you have access to.
7. Log in using a one-time 6-digit verification code sent by email you entered.
8. Explore product catalog, you should be able to see only product added to the *B2B* catalog with retail special prices.
9. Select Essential variant and select **Buy it now** and proceed to checkout.
10. Notice that account, Ship to, payment method are populated.
11. Fill in the **PO Number** fied with `PO-12345`.
12. Select **Submit order**.
 
In [!INCLUDE[prod_short](../includes/prod_short.md)], do the next steps:

1. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Orders**, and then select the related link.
2. Select the **Sync Orders From Shopify** action.
3. Select **OK**.

The imported order is ready for processing.

1. Select the imported order to open the **Shopify Order** window.
2. Notice that the though both orders were submitted by same person, they are linked to two different customers. 
3. In the order submitted on behalf of company you can see value in **PO Number** field, which is also transferred to the **External Document No.** field of created sales document.
4. Because we configured B2B Company to handle payments outside of Shopify the **Financial Status** is set to *Pending*. Once you received paiment, select the **Mark as Paid** action. Financial status will be updated in Shopify. 

## Walkthrough: Import items, customers, companies from Shopify

### Scenario 

You already have a successful online store and would like to start using [!INCLUDE[prod_short](../includes/prod_short.md)] as business management software. You would like to import as much data from Shopify as possible. 

### Steps

This is a continuation of [Walkthrough: Start selling products online](walkthrough-setting-up-and-using-shopify.md#walkthrough-start-selling-products-online) and [Walkthrough: Add your customers to your new online store](walkthrough-setting-up-and-using-shopify.md#walkthrough-add-your-customers-to-your-new-online-store). You can also try with your own data—for example, your Shopify store or sandbox.

In [!INCLUDE[prod_short](../includes/prod_short.md)], follow the steps listed next.

#### Prepare data

1. Switch to a free 30-day trial without sample data. For more information, see [Add your own data to an empty trial](/dynamics365/business-central/dev-itpro/administration/trials-subscriptions#add-your-own-data-to-an-empty-trial-company).
2. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, and then select the related link.
3. Select **New**.
4. In the **Code** field, enter `DEMO2`.
5. In the **Shopify URL** field, enter the URL to the online shop that you want to connect to.
6. Activate the **Enabled** toggle and then review and accept the terms and conditions.

Configure the Shopify shop as described here:

1. Deactivate the **Allow Background Syncs** toggle.
2. Select *From Shopify* in the **Sync Item** field.
3. Enable the **Auto Create Unknown Items** toggle.
4. Fill in the **Item Template Code** field with the appropriate template.
5. Select *From Shopify* in the **Sync Item Images** field.
6. Select *Item No.+ Variant Code* in the **SKU Mapping** field.
7. Select *All Customers* in **Customer Import from Shopify**.
8. Enable the **Auto Create Unknown Customer** toggle.
9. Fill in the **Customer/Company Template Code** field with the appropriate template.
10. Select *All Customers* in **Company Import from Shopify**.
11. Enable the **Auto Create Unknown Company** toggle.

#### Run the synchronization

1. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, and select the related link.
2. Select the *DEMO2* shop for which you want to synchronize data to open the **Shopify Shop Card** page.
3. Select **Sync Products**.
4. Select **Sync Product Images**.
5. Select **Sync Customers**.
6. Select **Sync Companies**

### Results

* Shopify Products are imported. To verify, select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and select the related link.
* Items with images are created. To verify, select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item**, and select the related link.
* Shopify Customers are imported. To verify, select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Customers**, and select the related link.
* Shopify Companies are imported. To verify, select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Companies**, and select the related link.
* Customers are created. To verify, select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and select the related link.


## See also

[Get Started with the Shopify Connector](get-started.md)  
