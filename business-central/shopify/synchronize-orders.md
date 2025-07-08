---
title: Synchronize and fulfill sales orders
description: Set up and run import and processing of sales orders from Shopify.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.date: 03/20/2025
ms.topic: how-to
ms.service: dynamics-365-business-central
ms.search.form: 30110, 30111, 30112, 30113, 30114, 30115, 30121, 30122, 30123, 30128, 30129, 30150, 30151, 30145, 30147
ms.custom: bap-template
---

# Synchronize and fulfill sales orders

This article describes the settings and steps that you must complete to synchronize and fulfill sales orders with Shopify in [!INCLUDE[prod_short](../includes/prod_short.md)].

## Set up the import of orders on the Shopify Shop Card

Enter a **currency code** if your online shop uses a different currency than the local currency (LCY). The specified currency must have exchange rates configured. If your online shop uses the same currency as [!INCLUDE[prod_short](../includes/prod_short.md)], leave the field empty. 

You can access the Store Currency in the [Store details](https://www.shopify.com/admin/settings/general) settings in your Shopify Admin. Shopify can be configured to accept different currencies. However, imported orders into [!INCLUDE[prod_short](../includes/prod_short.md)] use store currency.

Enable **Auto Sync Orders** to receive real-time notifications whenever a new order is created in a Shopify store. Once notification received the Connector will run **Sync Order from Shopify** batch job using **Job Queue Entries**. 
> [!NOTE]
> As Auto Sync Order releies on the job queue functionality it is not available to the delegated administrator.
> 
> When the **Auto Sync Orders** creates the Job Queue entry it doens't pass any parameters or fiters. 

A regular Shopify order can include costs in addition to the subtotal, such as shipping charges or, if enabled, tips. These amounts are posted directly to the G/L account you want to use for specific transaction types:

* **Shipping Charges Account**: You can choose different types of shipping charges, such as G/L account, item, or item charge, and specify the shipping agent and shipping agent service on the **Shipping Charges** page. To learn more, go to [Shipment method mapping](#shipment-method-mapping).
* **Sold Gift Card Account**: Learn more at [Gift Card](synchronize-orders.md#gift-cards)
* **Tip account**  

Enable **Auto Create Orders** to automatically create sales documents in [!INCLUDE[prod_short](../includes/prod_short.md)] once the Shopify order is imported.

It can be useful for people who work with Shopify Admin to see whether orders have been synchronized with [!INCLUDE[prod_short](../includes/prod_short.md)] and subsequently processed. In some cases, for example in high load environments, you might want to turn off synchronization. The **Add Business Central Doc. No. as Attribute** toggle provides you control over synchronization. When enabled, after an order has been processed in [!INCLUDE[prod_short](../includes/prod_short.md)] and the corresponding sales document has been created, the document number will be added as an attribute to the Shopify order. An entry will appear in the order’s timeline indicating that [!INCLUDE[prod_short](../includes/prod_short.md)] modified the order, the modified Shopify order will be included in the next round of order synchronization.

If you want to automatically release a sales document, turn on the **Auto Release Sales Order** toggle.

If you don't want to send automatic shipping confirmations to customers, turn off the **Send Shipping Confirmation** toggle. For example, you might turn off the toggle if you sell digital goods or want to use another notification mechanism.

If you select the **Shopify Order No. on Doc. Line** field, [!INCLUDE [prod_short](../includes/prod_short.md)] inserts sales lines of the type **Comment** with the Shopify order number.

> [!NOTE]
> The sales document in [!INCLUDE[prod_short](../includes/prod_short.md)] links to the Shopify order, and you can add the **Shopify Order No.** field to the list or card pages for sales orders, invoices, and shipments. To learn more about adding a field, go to [Start personalizing by using the personalization mode](../ui-personalization-user.md#start-personalizing-by-using-the-personalization-mode). 

In the **Tax area priority** field, prioritize how to select a tax area code for addresses on orders. The Shopify order you import contains information about taxes. Taxes are recalculated when you create sales documents, so it's important that the VAT or tax settings are correct in [!INCLUDE[prod_short](../includes/prod_short.md)]. To learn more about taxes, go to [Set Up Taxes for the Shopify Connection](setup-taxes.md).

Specify how you process returns and refunds:

* **Blank** specifies that you don't import and process returns and refunds.
* **Import only** specifies that you import information, but you manually create the corresponding credit memo.
* **Auto create credit memo** specifies that you import information and [!INCLUDE[prod_short](../includes/prod_short.md)] automatically creates the credit memos. This option requires that you turn on the **Auto Create Sales Order** toggle.

#### Setup returns and refunds

Specify a location for returns, and G/L accounts for refunds for goods and other refunds.

You can use the original return location from Shopify for refunds and returns. The location helps ensure that locations are accurate on credit memos, which reduces manual adjustments and streamlines the returns process.

To turn on the feature, on the **Shopify Shop Card** page, in the **Return Location Priority** field choose **Original > Default Location**.

The **Return Location Priority** field offers the following options:

* **Default Return Location**: This is the default option. It uses the value from the Default Return Location field when creating sales credit memos.
* **Original > Default Location**: Select this option if you want the connector to find the original location on the Shopify refund or, if applicable, the Shopify return document. If the connector can't find the original location, for example, when an item is restocked in several locations, it uses the **Default Return Location** defined on the **Shopify Shop Card** page.

* **Refund Account non-restock Items** specifies a G/L Account No. for items where you don't want to have an inventory correction.
* **Refund Account** specifies a G/L account for the difference in the total refunded amount and the total amount of the items.

Learn more at [Returns and refunds](synchronize-orders.md#returns-and-refunds)

#### Time zone consideration

There are several cases when the connector converts Date Time values received from Shopify to Date values in [!INCLUDE [prod_short](../includes/prod_short.md)]. The **Document Date** field on orders is one such field.

Shopify returns Date Time values as an ISO 8601-encoded date and time string. For example, 3:50 PM on September 7, 2019 in the time zone of UTC (Coordinated Universal Time) is represented as "2019-09-07T15:50:00Z." If your company time zone is different, that might lead to errors in conversions. To prevent that, go to the **Company Information** page, locate the **Post Code** field, and verify that the **Time Zone** value of selected post code entry is populated.

### Shipment method mapping

The **Shipment method code** for sales documents imported from Shopify can be filled in automatically. You need to configure the **Shipment Method Mapping**.

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, then choose the related link.
2. Select the shop for which you want to define a mapping to open the **Shopify Shop Card** page.
3. Choose the **Shipment Method Mapping** action. This action automatically creates records for shipping methods defined in the [**Shipping**](https://www.shopify.com/admin/settings/payments) settings in your **Shopify admin**.
4. In the **Name** field, you can see the name of the shipping method from Shopify.
5. Enter the **Shipment Method Code** with the corresponding shipping method in [!INCLUDE[prod_short](../includes/prod_short.md)].
6. To use different accounts for shipping fees than the account specified in the **Shipping Charges Account** field on the **Shopify Shop Card** page, fill in the **Shipping Charges Type** and **Shipping Charges No.** fields. The Shopify Connector supports the following types:

   * G/L Account
   * Item
   * Item Charge. Item Charge is automatically assigned to all items on the sales document.

7. You can also find the **Shipping Agent Code** and **Shipping Agent Service Code** fields on the **Shopify Shipment Methods** page. If you fill them in, they populate the corresponding fields on the sales document.

> [!NOTE]  
> If multiple shipping charges are associated with a sales order, only one will be selected as the shipping method and assigned to the sales document.
>
> Shopify lets you add multiple shipment fees to an order. For example, by editing the order in the Shopify Admin. When you receive several shipping fees with a Shopify order, the Shopify Connector uses the first one to initialize the **Shipment Method Code**, **Shipping Agent Code**, and **Shipping Agent Service Code** fields in the header of the document.
>
> In some cases, Shopify merges multiple shipping rates into one value called **Shipping** and doesn’t transfer individual rates.

### Location mapping

The location mapping is required to fill in the **Location Code** for sales document lines imported from Shopify. This mapping is important when the **Location Mandatory** toggle is enabled on the **Inventory Setup** card. Otherwise, you can't create sales documents.

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, then choose the related link.
2. Select the shop for which you want to configure the mapping of locations to open the **Shopify Shop Card** page.
3. Choose the **Locations** action to open the **Shopify Shop Locations**.
4. Choose the **Get Shopify Locations** action to import all the locations defined in Shopify. You can find them in the [**Locations**](https://www.shopify.com/admin/settings/locations) settings in your **Shopify admin** panel. 
5. Enter the **Default Location Code** with the corresponding location in [!INCLUDE[prod_short](../includes/prod_short.md)].

> [!NOTE]  
> Location mapping is also used to sync inventory. To learn more, go to [Sync inventory to Shopify](synchronize-items.md#sync-inventory-to-shopify).
  
## Run the order synchronization

The following procedure describes how to import and update the sales orders.

> [!NOTE]  
> You can't import orders that are archived in Shopify. If you need to check the order status, open the order from the [orders](https://www.shopify.com/admin/orders) page of the **Shopify admin** panel and review its details.
>
> Deactivate the **Automatically archive the order** option in the **Order Processing** section of the **General** settings in your **Shopify Admin** panel to make sure that all orders are imported to [!INCLUDE[prod_short](../includes/prod_short.md)]. If you need to import archived orders, use the **Unarchive Orders** action on the [Orders](https://www.shopify.com/admin/orders) page of the **Shopify admin** panel. 

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, then choose the related link.
2. Select the shop for which you want to import orders to open the **Shopify Shop Card** page.
3. Choose the **Orders** action.
4. Choose the **Sync Orders From Shopify** action.
5. Define filters on orders as necessary. For example, you can import fully paid orders or the ones with a low risk level.

   > [!NOTE]  
   > When filtering by tag, you should use filter tokens `@` and `*`. For example, if you want to import orders containing *tag1*, use `@*tag1*`. `@` will ensure the result is case insensitive, while `*` finds orders with multiple tags.

6. Choose the **OK** button.

Alternatively, you can search for the **Sync Orders From Shopify** batch job.

You can schedule the task to be performed automatically. Learn more at [Schedule recurring tasks](background.md#to-schedule-recurring-tasks).

### Under the hood

The Shopify Connector imports orders in two steps:

1. It imports order headers to the **Shopify Orders to Import** table when they match certain conditions:

   * They aren't archived. This means you can include or exclude orders from sync by archiving or unarchiving them in the Shopify Admin.
   * They were created or modified after the last sync. This means you can force reimport of a specific order if you modify it—for example, by adding **Notes** or **Tag**.

2. It imports Shopify orders and supplementary information.

   * The Shopify Connector processes all records in the **Shopify Orders to Import** table that match the filter criteria you defined on the **Sync Orders from Shopify** request page. For example, tags, channel, or the fulfillment status. If you don't specify filters, it processes all records.
   * When it imports a Shopify order, the Shopify Connector requests additional information from Shopify:

     * Order header
     * Order lines
     * Shipping and fulfillment information
     * Transactions
     * Returns and refunds, if configured

The **Shopify Orders to Import** page is useful for troubleshooting order import issues. It shows the newest orders on top. You can assess the orders that are available and take the next steps:

* Check whether an error blocked the import of a specific order, and explore the error's details. Check the **Has Error** field.
* Process only specific orders. Fill in the **Shop Code** field, select one or more orders, and then choose the **Import Selected Orders** action.
* Delete orders from the **Shopify Order to Import** page to exclude them from the sync.

## Review imported orders

After import completes, you can explore the Shopify order and find all related information. For example, the payment transactions, shipping costs, risk level, order attributes and tags, or fulfillments if the order was already fulfilled in Shopify. You can also see the order confirmation that was sent to the customer by choosing the **Shopify Status Page** action.

> [!NOTE]  
> You can navigate to the **Shopify Orders** window directly and you'll see orders with the *open* status from all shops. To review completed orders, you need to open the **Shopify Orders** page from the specific **Shopify Shop Card** page.

Before sales documents are created in [!INCLUDE[prod_short](../includes/prod_short.md)], you can use the **Synch order from Shopify** action in the **Shopify Order** page to reimport specific orders.

You can also mark an order as paid, which is useful in a B2B scenario where payments are processed outside Shopify checkout. Choose the **Mark as Paid** action on the **Shopify Order** page. Also, you can mark an order as canceled to start the refund flow in Shopify. Choose the **Cancel Order** action on the **Shopify Order** page, fill in the fields as necessary on the **Shopify Cancel Order** page, and press **OK**. Run order synchronization to import the updates to [!INCLUDE[prod_short](../includes/prod_short.md)].

## Create sales documents in Business Central

If the **Auto Create Orders** toggle is enabled on the **Shopify Shop Card**, [!INCLUDE[prod_short](../includes/prod_short.md)] tries to create a sales document after the order is imported. If issues such as a missing customer or product occur, fix the problems, and then create the sales order again.

### To create sales documents

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, then choose the related link.
2. Select the shop for which you want to synchronize orders to open the **Shopify Shop Card** page.
3. Choose the **Orders** action.
4. Select the order for which you want to create a sales document and choose the **Create Sales Documents** action.
5. Choose **Yes**.

If the Shopify order requires fulfillment, a **Sales Order** is created. For fulfilled Shopify orders, such as those orders that contain only a gift card or which are already handled in Shopify, a **Sales Invoice** gets created. 

A sales document is created and can be managed by using standard [!INCLUDE[prod_short](../includes/prod_short.md)] functionality.

If you want to recreate a sales document, you can use the **Unlink Processed Documents** action in the **Shopify Order** page. This action doesn't delete the already created sales document. You must process it manually.

### Manage missing customers

If your settings prevent creating a customer automatically and a matching customer isn't found, assign a customer to the Shopify order manually. There are a few ways to assign customers to orders:

* Assign the **Sell-to Customer No.** and **Bill-to Customer No.** directly on the **Shopify Orders** page by choosing a customer from the list of existing customers.
* Select a customer template, then create and assign the customer via the **Create new customer** action on the **Shopify Orders** page. The Shopify customer must have at least one address. Orders you create via the Shopify POS sales channel are often missing address details.
* Map an existing customer to the related **Shopify Customer** on the **Shopify Customers** page, and then choose the **Find Mapping** action on the **Shopify Orders** page.

### How the connector chooses which customer to use

The *Import order from Shopify* function tries to select customers in the following order:

1. If the **Default Customer No.** field is defined in the **Shopify Customer Template** for the **Ship-to Country/Region Code**, then the **Default Customer No.** is used, regardless of the settings in the **Customer Import From Shopify** and **Customer Mapping Type** fields. Learn more at [Customer Template per Country](synchronize-customers.md#customer-template-per-countryregion).
2. If the **Customer Import From Shopify** is set to *None* and the **Default Customer No.** is defined on the **Shopify Shop Card** page, then the **Default Customer No.** is used.

The next steps depend on the **Customer Mapping Type**.

* If it's **Always take the default customer**, then the connector uses the customer defined in the **Default Customer No.** field on the **Shopify Shop Card** page.
* If it's **By EMail/Phone**, the connector tries to find the existing customer by ID first, then by email, and then by phone number. If the customer isn't found, the connector creates a new customer.
* If it's **By Bill-to Info**, the connector tries to find the existing customer by ID first and then by the bill-to address information. If the customer isn't found, the connector creates a new customer.

> [!NOTE]  
> The connector uses information from the bill-to address and creates the bill-to customer in [!INCLUDE[prod_short](../includes/prod_short.md)]. The sell-to customer is the same as the bill-to customer.

For B2B orders, the flow is the similar although the connector uses the **Default Company No.**, **Company Import From Shopify**, and **Company Mapping Type** fields on the **Shopify Shop Card** page. There's no **Default Company No.** in the **Shopify Customer Template** because for B2B named customers are expected.

### Different processing rules for orders

You might want to process orders differently based on a rule. For example, orders from a specific sales channel, like POS, should use the default customer, but you want your online store to have real information about the customer.

One way to address this requirement is to create another Shopify Shop card and use filters in the **Sync Orders from Shopify** request page.

Example: You have an online store and a Shopify POS. For your POS, you want to use a fixed customer, but for your online store you want to create customers in [!INCLUDE[prod_short](../includes/prod_short.md)]. The following procedure lists the high-level steps. To learn more, go to the corresponding help articles.

1. Create a Shopify shop called *STORE* and link it to your Shopify account.
1. Configure item/product synchronization so that this store manages product information.
1. Specify that customers are imported with orders. The connector should find customers by looking for their email address. If it doesn't find an address, it uses the customer template to create a new customer.
1. Create a Shopify shop called *POS* and link it to the same Shopify account.
1. Make sure that item/product synchronization is disabled.
1. Configure the connector to use the default customer.
1. Create a recurring job queue entry for Report 30104 **Sync orders from Shopify**. Select **STORE** in the **Shopify Shop Code** field, and use filters to catch all orders except the ones that the POS sales channel creates. For example, **<>Point of Sale**
1. Create a recurring job queue entry for Report 30104 **Sync orders from Shopify**. Select **POS** in the **Shopify Shop Code** field, and use filters to catch orders generated by the POS sales channel. For example, **Point of Sale**.

Each job queue imports and processes orders within the defined filters and uses the rules from the corresponding Shopify Shop card. For example, they create point of sales orders for the default customer.

> [!IMPORTANT]
> To avoid conflicts when processing orders, use the same job queue category for both job queue entries.
> 
> You should not rely on the **Auto Sync Orders** setting as it doesn't support filters and request page paremeters. 

### Effect of order editing

In Shopify:

|Edit|Effect on Shopify Orders not yet processed in [!INCLUDE[prod_short](../includes/prod_short.md)] | Effect on Shopify orders already processed in [!INCLUDE[prod_short](../includes/prod_short.md)] |
|------|-----------|-----------|
|Change the fulfillment location | Fulfillment location is synched to [!INCLUDE[prod_short](../includes/prod_short.md)]. | Fulfillment location is synched to [!INCLUDE[prod_short](../includes/prod_short.md)].|
|Edit an order and increase quantity|Imported order uses the new quantity.| Connector detects the change and marks the orders. |
|Edit an order and decrease quantity|Imported order uses the new quantity. A Shopify refund with zero amount is imported that can't be converted to a credit memo.| Connector detects the change and marks the orders. |
|Edit an order and remove existing item |Removed item isn't imported. A Shopify refund with zero amount is imported that can't be converted to a credit memo.| Connector detects the change and marks the orders. |
|Edit an order and add new item | Original and added items are imported. | Connector detects the change and marks the orders. |
|Process order: fulfill, update payment information | Order header is updated. |Order header is updated. The fulfillment isn't synchronized with Shopify.|
|Cancel paid order | Order header is updated, to be processed separately |Connector detects the change and marks the orders. |
|Cancel unpaid order | Removed item isn't imported. A Shopify refund with zero amount is imported that can't be converted to a credit memo. |Connector detects the change and marks the orders. |

If an order was already processed in [!INCLUDE[prod_short](../includes/prod_short.md)], the connector displays the following error message: *The order has already been processed in Business Central, but an edition was received from Shopify. Changes were not propagated to the processed order in Business Central. Update the processed documents to match the received data from Shopify. If you wish to force the synchronization use the action "Sync order from Shopify" in the Shopify Order card page.*

Depending on status of the created sales document, you can perform following actions:

1. Delete created sales document
2. Choose the **Unlink Processed Documents** action to reset the **Processed** indicator.
3. Choose the **Synch order from Shopify** action to update the individual order with recent data from Shopify.

In [!INCLUDE[prod_short](../includes/prod_short.md)]:

|Edit|Effect|
|------|-----------|
|Change the location to another location. Post shipment. | Order is marked as fulfilled. Fulfillment location from Shopify is used. |
|Decrease quantity. Post shipment. | The Shopify order is marked as partially fulfilled. |
|Increase quantity. Post shipment. | The fulfillment won't synchronize with Shopify. It's the same if the fulfillment was split in Shopify but processed as one line in [!INCLUDE[prod_short](../includes/prod_short.md)]. |
|Add a new item. Post shipment. | The Shopify order is marked as fulfilled. New lines aren't added. |

## Export posted sales invoices to Shopify

You can export posted sales invoices to Shopify so that buyers can sign in to Shopify and access all their invoices, regardless of which app they were created in.

You can export posted sales invoices to Shopify as orders by using the **Sync Posted Invoices to Shopify** action on the Shopify Shop Card page, or you can use Tell Me search to find it. You can also run the report by using the job queue.

To enable the capability for a specific shop, go to the **Shopify Shop Card** page and turn on the **Posted Invoice Sync** toggle. You also need to configure the **Payment Terms Mapping**.

The sync includes invoices under the following conditions:

* The **Shopify Order ID** field contains **0**.
* The bill-to customer has a mapping in the **Shopify Customers** or **Shopify Companies** pages.
* The bill-to customer isn't used as the default customer on the **Shopify Shop Card** or **Shopify Customer Template**.
* The posted invoice has at least one non-comment line where the **No.** field has a value.

When you run the report, the following happens in [!INCLUDE [prod_short](../includes/prod_short.md)] and Shopify.

**Business Central**

Update the **Shopify Order ID** field based on the results of the sync:

* Successful export: update the **Shopify Order ID** field with the ID of the order in Shopify.
* Export failed: set "-1"
* Invoice is excluded from sync for a reason listed in the conditions mentioned earlier: set "-2"

>[!Note]
>The same pattern is used in the posted sales shipment, where the **Update Document** page lets you replace **-1** and **-2** with **0** to retry the export.

**Shopify**

The Shopify connector does the following steps:

* Creates a draft order with header and item lines
* Converts the draft order it to an order

**Fields export to order headers and lines**

The following fields export on the order header:

* The mapped bill-to customer/company is used.
* The **Fulfillment Status** field shows **Fulfilled**. Tracking details don't synchronize.
* The **Paid Status** field shows **Paid** or **Partially Paid**, based on the customer ledger entry linked to the sales invoice. For partially paid, it shows the **Remaining Amount** field.

The following fields export on the order lines:

* Items and lines of other types, such as **G/L Account** or **Item Charge** lines, export as custom products in Shopify.
* Shipping charges in Shopify aren't created. The shipping cost is registered as a custom product in Shopify.
* Tax amounts. Because the Graph API doesn't currently support the TaxLine object, the calculated tax is added as a custom product. Tax information from [!INCLUDE [prod_short](../includes/prod_short.md)] won’t be available in the tax report in Shopify Admin. To prevent Shopify from recalculating taxes, orders are marked as **Tax Exempt**.
* Quantity, in whole numbers. Shopify doesn’t support fractions.

### Effect on the process of synchronizing orders

Synchronization imports the order and checks whether it was exported earlier. If it was exported earlier:

* It marks the order as processed.
* It adds a link to the posted sales invoice (related documents, should happen automatically because the Shopify Order ID is already populated). Shopify might automatically archive fully paid and fulfilled orders, and the synchronization won't process them.

### Deal with updates

In Shopify, because the order is already fulfilled, the only meaningful changes are notes, payment status, and payment transactions. If payments are processed in Shopify, refunds and returns are as well.

[!INCLUDE [prod_short](../includes/prod_short.md)] doesn't track changes. Currently, if you want to mark the order as paid, use the **Mark as Paid** action on the **Shopify Order Card** page.

## Synchronize shipments to Shopify

When a sales order created from a Shopify order is shipped, you can synchronize the shipments with Shopify.

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sync Shipments to Shopify**, then choose the related link.
2. Define the filters on shipments as necessary. For example, you can update a shipment posted on a specific date.
3. Choose **OK**.

The order in Shopify is marked as fulfilled. The customer automatically receives a shipment notice email or text message (SMS). If a shipping agent and a tracking code are specified on the shipment, the tracking information is included in the email.

Alternatively, use the **Sync Shipments** action in the Shopify Sales Orders or Shopify Shop pages.

You can schedule the task to be performed in an automated manner. Learn more at [Schedule recurring tasks](background.md#to-schedule-recurring-tasks).

> [!Note]
> **Know limitations**. Orders with multiple lines of the same product will not be fulfilled. Mark such orders as fulfilled in Shopify Admin. This issue can occur when using the **Buy X get Y** discount with identical products for **Customer gets** and **Customer buys**.

Remember to run **Synchronize Orders from Shopify** to update the fulfillment status of an order in [!INCLUDE[prod_short](../includes/prod_short.md)]. The connector functionality also archives completely paid and fulfilled orders in both Shopify and [!INCLUDE[prod_short](../includes/prod_short.md)], provided the conditions are met. 

### Shipping agents and tracking URL

If the **Posted Sales Shipment** document contains the **Shipping Agent Code** and/or **Package Tracking No.**, this information is sent to Shopify and to the customer in the shipping confirmation email.

The tracking company is populated in the following order (from highest to lowest) based on the shipping agent record:

1. **Shopify Tracking Company**
1. **Name**
1. **Code**

If the **Package Tracking URL** field is filled in for the shipping agent record, the shipping confirmation contains a tracking URL.

>[!Tip]
>If you don't want to send automatic shipping confirmations to customers, turn off the **Send Shipping Confirmation** toggle on the **Shopify Shop card** page.
>
>The **Shipping Agent Code** and **Shipping Agent Service Code** can be automatically filled in based on settings on the **Shipping Charges** page. To learn more, go to [Shipment method mapping](#shipment-method-mapping).

## Returns and refunds

In an integration between Shopify and [!INCLUDE[prod_short](../includes/prod_short.md)], it's important to be able to synchronize as much business data as possible. That makes it easier to keep your finance and inventory levels up to date in [!INCLUDE[prod_short](../includes/prod_short.md)]. The data you can synchronize includes returns and refunds that were recorded in Shopify Admin or Shopify POS.

Returns and refunds are imported with their related orders if you enabled the processing type on the Shopify Shop Card.

Returns are imported for informational purposes only. No processing logic is associated with them.

Financial and, if needed, inventory transactions are processed via refunds. Refunds can include products or just amounts—for example, if a merchant decides to compensate shipping charges or some other amount.

You can create sales credit memos for refunds. The credit memos can have the following types of lines:

|Type|No.|Comment|
|-|-|-|
|G/L Account|Sold Gift Card Account| Use for refunds related to gift cards.|
|G/L Account|Refund Account Nonstock | Use for refunds related to products that weren’t restocked. |
|Item |Item No.| Use for refunds related to products that were restocked. Valid for direct refunds or refunds linked to returns. The location code on the credit memo line is set based on the value selected for the return location.|
|G/L Account| Refund Account | Use for other refunded amounts that aren't related to products or gift cards. For example, tips, or if you manually specified an amount to refund in Shopify. |

> [!Note]
> The return locations, including blank locations, defined in the **Shopify Shop Card** are used on the created credit memo. The system ignores the original locations from orders or shipments.

## Gift cards

In the Shopify shop you can sell gift cards, which can be used to pay for real products.

When dealing with gift cards, it's important to enter a value in the **Sold Gift Card Account** field in the **Shopify Shop Card** page. The sold gift card synchronizes together with the orders and added to sales document as line of type *G/L Account*. 

An applied gift card also imports with the order, but now as a payment transaction. The gift card doesn't reduce the amount to invoice. To learn how to reconcile payment transaction, see [Transactions and payouts](transactions-and-payouts.md).

To review the issued and applied gift cards, choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Gift Cards**, then choose the related link.

> [!NOTE]
> To import gift cards created manually or sold via old orders, that you don't want to import, you need to use configuration package. Use the  30110 **Shpfy Gift Card** table and **Id**, **Last Characters**, **Amount**.  You can export gift cards from Shopify Admin. You will need **Id**, **Last Charaters** and **Current Balance** fields. 

## Related information

[Get started with the Shopify Connector](get-started.md)  
