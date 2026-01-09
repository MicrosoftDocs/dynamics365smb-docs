---
title: Synchronize and fulfill sales orders
description: Set up and run import and processing of sales orders from Shopify.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.date: 01/09/2026
ms.topic: how-to
ms.service: dynamics-365-business-central
ms.search.form: 30110, 30111, 30112, 30113, 30114, 30115, 30121, 30122, 30123, 30128, 30129, 30150, 30151, 30145, 30147
ms.custom: bap-template
---

# Synchronize and fulfill sales orders

This article describes the settings and steps that you must complete if you want to synchronize and fulfill Shopify sales orders in [!INCLUDE[prod_short](../includes/prod_short.md)].

## Set up the import of orders on the Shopify Shop Card

Enter a **Currency code** if your online shop uses a different currency than the local currency (LCY). The specified currency must have exchange rates configured. If your online shop uses the same currency as [!INCLUDE[prod_short](../includes/prod_short.md)], leave the field empty.

You can access the store currency in the [Store details](https://www.shopify.com/admin/settings/general) settings in your Shopify Admin. You can configure Shopify to accept different currencies. However, the orders you import to [!INCLUDE[prod_short](../includes/prod_short.md)] use store currency.

Enable **Auto Sync Orders** to receive real-time notifications whenever a new order is created in a Shopify store. When a notification is received, the Connector runs the **Sync Order from Shopify** batch job using **Job Queue Entries**.

> [!NOTE]
> Because **Auto Sync Order** relies on the job queue features, it isn't available to people who have the Delegated Admin permission.
>
> When the **Auto Sync Orders** creates the job queue entry, it doesn't set any parameters or filters.

A regular Shopify order can include costs in addition to the subtotal, such as shipping charges or, if enabled, tips. These amounts are posted directly to the G/L account you want to use for specific transaction types:

* **Shipping Charges Account**. You can also choose different types of shipping charges, such as G/L account, item, or item charge, and specify the shipping agent and shipping agent service on the **Shipping Charges** page. To learn more, go to [Shipment method mapping](#shipment-method-mapping).
* **Sold Gift Card Account**. Learn more at [Gift Card](synchronize-orders.md#gift-cards)
* **Tip account**.
* **Cash Rounding Account No.**. Learn more at [Working with Shopify POS](shopify-pos.md#order-handling)
  
Turn on the **Auto Create Orders** toggle to automatically create sales documents in [!INCLUDE[prod_short](../includes/prod_short.md)] when you import a Shopify order. If the Shopify order requires fulfillment, a **Sales Order** is created. For fulfilled Shopify orders, such as orders that contain only a gift card or which were already handled in Shopify, you can turn on the **Create Invoices From Orders** toggle then a **Sales Invoice** gets created. That setting can be useful when you delay the posting of a sales document because invoice doesn't affect inventory availability, but the order does.

If you select the **Shopify Order No. on Doc. Line** field, [!INCLUDE [prod_short](../includes/prod_short.md)] adds sales lines of the type **Comment** with the Shopify order number.

> [!NOTE]
> The sales document in [!INCLUDE[prod_short](../includes/prod_short.md)] links to the Shopify order, and you can add the **Shopify Order No.** field to the list or card pages for sales orders, invoices, and shipments. To learn more about adding a field, go to [Start personalizing by using the personalization mode](../ui-personalization-user.md#start-personalizing-by-using-the-personalization-mode). 

People who work with Shopify Admin might want to check whether orders are synchronized with [!INCLUDE[prod_short](../includes/prod_short.md)] and processed. In some cases, for example in high load environments, you might want to turn off synchronization. The **Add Business Central Doc. No. as Attribute** toggle gives you control over synchronization. When enabled, after an order is processed in [!INCLUDE[prod_short](../includes/prod_short.md)] and the corresponding sales document is created, the document number is added as an attribute to the Shopify order. An entry appears in the order’s timeline to indicate that [!INCLUDE[prod_short](../includes/prod_short.md)] modified the order. The next round of order synchronization includes the modified Shopify order.

If you want to automatically release a sales document, turn on the **Auto Release Sales Order** toggle.

The **Archive Processed Shopify Orders** toggle specifies whether Shopify Connector should archive fully paid and fulfilled orders in Shopify, provided the orders meet the the following conditions.

- The **Fully Paid** field contains **Yes**.
- The **Fulfillment Status** field contains **Fulfilled**.
- The **Processed** field contains **Yes**, and either the **Sales Order No.** or **Sales Invoice No.** field has a value.
- For shopify orders linked to sales orders, all lines in the linked sales order are fully shipped. The connector checks whether the **Outstanding Quantity** isn't **zero**. 

The connector also archives fully paid and fulfilled orders in both Shopify and [!INCLUDE[prod_short](../includes/prod_short.md)], provided the orders meet the conditions.

In the **Tax area priority** field, prioritize how to select a tax area code for addresses on orders. The Shopify order you import contains information about taxes. Taxes are recalculated when you create sales documents, so it's important that the VAT or tax settings are correct in [!INCLUDE[prod_short](../includes/prod_short.md)]. To learn more about taxes, go to [Set Up Taxes for the Shopify Connection](setup-taxes.md).

If you don't want to send automatic shipping confirmations to customers, turn off the **Send Shipping Confirmation** toggle. For example, you might turn off the toggle if you sell digital goods or want to use another notification mechanism.

### Setup returns and refunds

Specify how you process returns and refunds:

* **Blank** specifies that you don't import and process returns and refunds.
* **Import only** specifies that you import information, but you manually create the corresponding credit memo.
* **Auto create credit memo** specifies that you import information and [!INCLUDE[prod_short](../includes/prod_short.md)] automatically creates the credit memos. This option requires that you turn on the **Auto Create Sales Order** toggle.

Specify a location for returns, and G/L accounts for refunds for goods and other refunds.

You can use the original return location from Shopify for refunds and returns. The location helps ensure that locations are accurate on credit memos, which reduces manual adjustments and streamlines the returns process.

To turn on the feature, on the **Shopify Shop Card** page, in the **Return Location Priority** field choose **Original > Default Location**.

The **Return Location Priority** field offers the following options:

* **Default Return Location**: This default option uses the value from the **Default Return Location** field when creating sales credit memos.
* **Original > Default Location**: Select this option if you want the connector to find the original location on the Shopify refund or, if applicable, the Shopify return document. If the connector can't find the original location, for example, when an item is restocked in several locations, it uses the **Default Return Location** defined on the **Shopify Shop Card** page.

Some amounts associated with a refund post directly to the G/L account. Choose the G/L accounts that you want to use for specific transaction types:

* **Refund Account non-restock Items** specifies a G/L account for items where you don't want to have an inventory correction.
* **Refund Account** specifies a G/L account for the difference in the total refunded amount and the total amount of the items.

Learn more at [Returns and refunds](synchronize-orders.md#returns-and-refunds)

### Time zone consideration

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
> If multiple shipping charges are associated with a sales order, only one is selected as the shipping method and assigned to the sales document.
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
>
> Shopify Connector also creates sales invoices for fulfilled documents and credit memos for refunds for locations where the **Directed Put-away and Pick** toggle is enabled. The warehouse entries post for the adjustment bin. To reconcile quantities with normal bins, use the **Warehouse physical inventory journal** page.

### Payment terms mapping

The payment mapping is used in the following cases:

* Defining the payment term code and due date when you import orders.
* Exporting posted sales invoices to Shopify.
* Importing and exporting payment terms details in a B2B company.

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, and then choose the related link.
2. Select the shop for which you want to configure the mapping of payment terms to open the **Shopify Shop Card** page.
3. Choose the **Payment Terms Mapping** action to open the **Shopify Payment Terms Mapping**.
4. Choose the **Refresh** action to import all payment terms defined in Shopify.
5. Enter the **Payment Terms Code** with the corresponding payment term in [!INCLUDE[prod_short](../includes/prod_short.md)].
6. Turn on the **Is Primary** toggle for the **Fixed Date** entry. When you export posted sales invoices, this setting lets you transfer the exact due date from [!INCLUDE[prod_short](../includes/prod_short.md)] to the order in Shopify. To learn more, go to [Export posted sales invoices to Shopify](#export-posted-sales-invoices-to-shopify)

> [!NOTE]  
> Shopify Connector keeps the due date from a Shopify order (such as for the payment terms **Fixed Date** or **Within X days**) in the sales document, regardless of the mapping. For payment terms without a set due date (such as **Due on receipt** or **Due on fulfillment**), the Connector calculates the due date using the formula from the mapped payment term. If no mapping exists, the customer's payment term applies. If that's also missing, the due date defaults to the document date.

### Staff-to-salesperson mapping

When you use Shopify POS or other sales channels, you can improve traceability and performance reporting. You can import staff member information from Shopify to salespersons in [!INCLUDE [prod_short](../includes/prod_short.md)] on sales documents.

To automatically fill in the **Salesperson code** field for sales documents imported from Shopify, configure **Shopify Staff Member Mapping**.

1. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, and select the related link.
2. Select the shop where you want to set up a mapping to open the **Shopify Shop Card** page.
3. Select the **Shopify Staff Member Mapping** action.
4. Select **Refresh** to import staff members enabled on Shopify.
5. Enter the **Salesperson Code** for the matching salesperson in [!INCLUDE [prod_short](../includes/prod_short.md)].

When you import orders from Shopify, the orders created via Shopify POS or via Draft Orders include the staff ID. If you configure the mapping on the **Shopify Staff Member Mapping** page, the connector adds the corresponding salesperson to the Shopify order and copy it to the sales document.

Known limitations:

* The mapping works for B2B stores only.
* You can't export salespersons from [!INCLUDE [prod_short](../includes/prod_short.md)] to Shopify.
* Not used during export of posted sales invoices to Shopify.

  
## Run the order synchronization

The following procedure describes how to import and update the sales orders.

> [!NOTE]  
> You can't import orders that are archived in Shopify. If you need to check the order status, open the order from the [orders](https://www.shopify.com/admin/orders) page of the **Shopify admin** panel and review its details.
>
> Deactivate the **Automatically archive the order** option in the **Order Processing** section of the **General** settings in your **Shopify Admin** panel to make sure that all orders are imported to [!INCLUDE[prod_short](../includes/prod_short.md)]. If you need to import archived orders, use the **Unarchive Orders** action on the [Orders](https://www.shopify.com/admin/orders) page of the **Shopify admin** panel. 

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, then choose the related link.
2. Select the shop for which you want to import orders to open the **Shopify Shop Card** page.
3. Choose the **Orders** action.
4. Choose the **Sync Orders from Shopify** action.
5. Define filters on orders as necessary. For example, you can import fully paid orders or the ones with a low risk level.

> [!NOTE]  
> When you filter by tags in the **Sync Order from Shopify** request page, remember that tags are stored as space-separated string, with each tag enclosed in square brackets: `[tag1] [tag2] [tag3]`.
>
> There can be multiple tags, so it's a good idea to use the `*` filter token. For example, if you want to import orders that contain *tag1*, use `*tag1*`. If you're unsure about the case, use the filter token `@` to ensure the the result isn't case sensitive. For example, use `@*tag1*` to get orders with tags such as *tag1*, *Tag1*, or *TAG1*.
>
> Other [filter criteria](../ui-enter-criteria-filters.md) also works. For example if you want several tags, use `*tag1*|*tag2*`, or if you want to skip some orders, use `<>*tag3*`.

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

### Review imported orders

After import completes, you can explore the Shopify order and find all related information. For example, the payment transactions, shipping costs, risk level, order attributes and tags, or fulfillments if the order was already fulfilled in Shopify. You can also see the order confirmation that was sent to the customer by choosing the **Shopify Status Page** action.

> [!NOTE]  
> The **Shopify Orders** page contains useful views, that allow you find all orders from all shops. If you want to focus on open orders only, use the **Open** view. You can also use views to show only unprocessed orders, orders where an error interrupted processing, or orders that have a conflict because they were updated in Shopify after they were processed in [!INCLUDE [prod_short](../includes/prod_short.md)].

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

If the Shopify order requires fulfillment, a **Sales Order** is created. For fulfilled Shopify orders, such as those orders that contain only a gift card or which are already handled in Shopify, a **Sales Invoice** gets created. If you turn off the **Create Invoices From Orders** toggle, a **Sales Order** gets created for fulfilled orders. By default, the toggle is turned on.

A sales document is created and can be managed by using standard [!INCLUDE[prod_short](../includes/prod_short.md)] functionality.

If you want to recreate a sales document, you can use the **Unlink Processed Documents** action in the **Shopify Order** page. This action doesn't delete the already created sales document. You must process it manually.

### Order Total FactBox

The **Order total** part in the **Shopify Orders** page displays totals from both the order in Shopify and the sales document in [!INCLUDE [prod_short](../includes/prod_short.md)]. The totals let you compare figures without opening each document, which can be helpful when you're testing customer and item templates.

### Manage missing customers

If your settings prevent creating a customer automatically and a matching customer isn't found, assign a customer to the Shopify order manually. There are a few ways to assign customers to orders:

* Assign the **Sell-to Customer No.** and **Bill-to Customer No.** directly on the **Shopify Orders** page by choosing a customer from the list of existing customers.
* Select a customer template, then create and assign the customer via the **Create new customer** action on the **Shopify Orders** page. The Shopify customer must have at least one address. Orders you create via the Shopify POS sales channel are often missing address details.
* Map an existing customer to the related **Shopify Customer** on the **Shopify Customers** page, and then choose the **Find Mapping** action on the **Shopify Orders** page.

### How the connector chooses which customer to use

The **Import order from Shopify** action tries to select customers in the following order:

1. If the **Default Customer No.** field is defined in the **Shopify Customer Template** for the **Ship-to Country/Region Code**, the **Default Customer No.** is used, regardless of the settings in the **Customer Import From Shopify** and **Customer Mapping Type** fields. Learn more at [Customer setup per country/region](synchronize-customers.md#customer-setup-per-countryregion).
2. If the **Customer Import From Shopify** is set to **None**, and the **Default Customer No.** is defined on the **Shopify Shop Card** page, the **Default Customer No.** is used.

The next steps depend on the **Customer Mapping Type**.

* If it's **Always take the default customer**, the connector uses the customer defined in the **Default Customer No.** field on the **Shopify Shop Card** page.
* If it's **By EMail/Phone**, the connector tries to find the existing customer by ID first, then by email, and then by phone number. If the customer isn't found, the connector creates a new customer.
* If it's **By Bill-to Info**, the connector tries to find the existing customer by ID first and then by the bill-to address information. If the customer isn't found, the connector creates a new customer.

If a customer is found, it's used to populate both the **Sell-to Customer No.** and the **Bill-to Customer No.** fields in the **Shopify Order** page. The connector ignores the **Bill-to Customer No.** value defined in the **Customer Card** page.
If a customer is identified, their information fills in both the **Sell-to Customer No.** and the **Bill-to Customer No.** fields. The connector disregards any value specified in the **Bill-to Customer No.** on the **Customer Card** page.

> [!NOTE]  
> The connector uses information from the bill-to address and creates the customer in [!INCLUDE[prod_short](../includes/prod_short.md)].
>
> The connector doesn't populate the **Bill-to Customer No.** field in the created customer.

For B2B orders, the flow is the similar although the connector uses the **Default Company No.**, **Company Import From Shopify**, and **Company Mapping Type** fields on the **Shopify Shop Card** page. There's no **Default Company No.** in the **Shopify Customer Template** page because named customers are expected for B2B.

B2B orders also contain company location details. The **Sell-to Customer No.** and **Bill-to Customer No.** fields, available on the **Shopify Company Location** page, can affect the mapping. By default, these fields are empty, but you can fill them in if needed. When you import a Shopify order associated with a B2B company and location, the connector uses the data in these fields to map the sell-to and bill-to customers in the sales order.

The following table shows examples of customer mappings.

|Value in the **Customer No.** field in the **Shopify Company**	|Value in the **Sell-to Customer No.** field in the **Shopify Company Location**	|Value in the **Bill-to Customer No.** field in the **Shopify Company Location**	|Proposed value for **Sell-to Customer No.** field in the Shopify Order	|Proposed value for **Bill-to Customer No.** field in the Shopify Order|
----|----|----|----|----
|10000	|*blank*	|*blank*	|10000	|10000|
|10000	|20000	|*blank*	|20000	|20000 (same as  Sell-to Customer No. in Company Location)|
|10000	|20000	|30000	|20000	|30000|
|10000	|*blank*	|30000  Not supported. Must be blank or the **Sell-to Customer No.** field must have a value.	|N/A|N/A|
|*blank*	|*blank*	|*blank*	|*blank*	|*blank*|

### Address information in the created sales document

Sales documents in [!INCLUDE[prod_short](../includes/prod_short.md)] have three groups of fields related to customers:

* Sell-to
* Ship-to
* Bill-to

Each group contains following fields: **Name**, **Name 2**, **Address**, **Address 2**, **Post code**, **City**, **Country Code**. Depending on your setup, they can also contain a state or province.

When you manually create a sales document, these fields contain information from the customer. If you use an alternative shipping address, they also contain information from the ship-to addresses entry. When working with Shopify orders, the address information is copied from Shopify. Both the Ship-to and Sell-to fields have information about shipping because Shopify doesn't differentiate between these two concepts. 

Bill-to fields have the billing address specified in the Shopify order. One reason for this is that addresses in Shopify are often more accurate than in [!INCLUDE[prod_short](../includes/prod_short.md)]. Using the address specified in the Shopify order is also useful for scenarios when a default customer number is defined in the **Shopify Shop Card** or **Customer Setup by Country/Region** pages.

> [!NOTE]  
> To ensure that you can review address details in the created sales document, set both the **Ship-to** and **Bill-to** fields to **Custom Address**.

### Locations in the created sales document

For each sales document line that requires fulfillment, the connector locates fulfillment order lines that link to the same order and contain an identical product and variant. The connector prioritizes fulfillment orders with statuses that differ from CLOSED. When it finds such fulfillment lines, the connector uses the **Location ID** from the fulfillment line. If multiple fulfillment lines for the same order line exist but reference different locations, only one location is used.

> [!NOTE]  
> The Shopify API doesn't show information about the connection between the order line and the fulfillment order line. The connector finds the corresponding fulfillment order line by filtering by product and variant. Usually, Shopify doesn't allow several lines with the same product and variant in the single order. However, you can do that via apps or when using the **Buy X get Y** discount with identical products for **Customer gets** and **Customer buys**. In these cases, the connector can't find fulfillment lines.

If the connector can't find corresponding fulfillment order lines, it uses the **Location ID** on the Shopify order line. When using non-Microsoft fulfillment services or the Business Central Fulfillment Service, this field contains accurate location data. If fulfillment is performed manually in **Shopify Admin**, the default location is applied. You can view the default location in your **Shopify admin**. Check the **Default location** section of the [Locations](https://www.shopify.com/admin/settings/locations) settings.

When you create sales documents, the connector checks the **Shopify Locations Mapping** page for a corresponding entry and applies the **Default Location Code** from the matched entity. To learn more, go to [Location Mapping](#location-mapping).

## Different processing rules for orders

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
> Don't rely on the **Auto Sync Orders** setting because it doesn't support filters and request page parameters.

## Effect of order editing

**In Shopify:**

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

If an order was already processed in [!INCLUDE[prod_short](../includes/prod_short.md)], the connector displays the following error message: *The order was already processed in Business Central, but an edition was received from Shopify. Changes weren't propagated to the processed order in [!INCLUDE[prod_short](../includes/prod_short.md)]. Update the processed documents to match the received data from Shopify. If you wish to force the synchronization use the action "Sync order from Shopify" in the Shopify Order card page.*

Depending on status of the created sales document, you can perform following actions:

1. Delete created sales document
2. Choose the **Unlink Processed Documents** action to reset the **Processed** indicator.
3. Choose the **Synch order from Shopify** action to update the individual order with recent data from Shopify.


**In [!INCLUDE[prod_short](../includes/prod_short.md)]:**

|Edit|Effect|
|------|-----------|
|Change the location to another location. Post shipment. | Order is marked as fulfilled. Fulfillment location from Shopify is used. |
|Decrease quantity. Post shipment. | The Shopify order is marked as partially fulfilled. |
|Increase quantity. Post shipment. | The fulfillment doesn't synchronize with Shopify. It's the same if the fulfillment was split in Shopify but processed as one line in [!INCLUDE[prod_short](../includes/prod_short.md)]. |
|Add a new item. Post shipment. | The Shopify order is marked as fulfilled. New lines aren't added. |

## Synchronize shipments to Shopify

When a sales order created from a Shopify order is shipped, you can synchronize the shipments with Shopify.

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sync Shipments to Shopify**, then choose the related link.
2. Define the filters on shipments as necessary. For example, you can update a shipment posted on a specific date.
3. Choose **OK**.

The sync includes posted sales shipments under the following conditions:

- The **Shopify Order Id** field doesn't contain *0* and a related shopify order exists.
- The **Shopify Fulfillment Id** field contains *0*.
- Posted shipment has at least one line of type item with quantity more than zero. The related shopify order line exists.
- The order in Shopify is marked as fulfilled. 

If the **Send Shipping Confirmation** toggle is enabled, the customer automatically receives a shipment notice email or text message (SMS). 

If a shipping agent and a tracking code are specified on the shipment, the tracking information is updated in the order in Shopify and included in the email to customer.

Update the **Shopify Fulfillment ID** field based on the results of the sync:

- Successful export: update the **Shopify Fulfillment ID** field with the ID of the fulfillment in Shopify.
- Export failed: set "-1"
- Posted shipment doesn't have any lines of type item with quantity more than zero: set "-2"
  
Alternatively, to sync shipments use the **Sync Shipments** action in the Shopify Sales Orders or Shopify Shop pages.

You can schedule the task to be performed in an automated manner. Learn more at [Schedule recurring tasks](background.md#to-schedule-recurring-tasks).

> [!Note]
> **Know limitations:**
> 
> - Orders with multiple lines of the same product will not be fulfilled. Mark such orders as fulfilled in Shopify Admin. This issue can occur when using the **Buy X get Y** discount with identical products for **Customer gets** and **Customer buys**.
> - A Shopify order line split across two locations (for example, *2* from *EAST* and *3* from *WEST*) appears in [!INCLUDE[prod_short](../includes/prod_short.md)] as a single sales order line with just one location—such as *WEST*. If you ship all *5* at the same time, the order won't be fulfilled. If you first modify the quantity to Ship in [!INCLUDE[prod_short](../includes/prod_short.md)] to *2* and post shipment, and then you post the shipment of the remaining *3*, the Shopify order is marked as partially fulfilled with *3* units fulfilled from the location selected in the sales order order line. In this example, it's *WEST*.   
> - Modification in sales order before posting might affect the connector's ability to synchronize shipments to Shopify. To learn more, go to the second table in the [Effect of order editing](#effect-of-order-editing) section.

Remember to run **Synchronize Orders from Shopify** to update the fulfillment status of an order in [!INCLUDE[prod_short](../includes/prod_short.md)]. 

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

### Troubleshooting shipment synchronizations

If you expect an order in Shopify to be marked as fulfilled but it isn't, double-check the following settings:

1.	Go to **Shopify Order** and check whether the corresponding order exists in [!INCLUDE[prod_short](../includes/prod_short.md)]. Without an order, the connector doesn't have the fulfillment details it needs.
2.	Go to **Shopify Order** and run **Sync order from Shopify** to retrieve the latest updates.
3.	Go to **Shopify Order** and then to the **Completed Fulfillments** page. If fulfillments are listed, fulfillment was already registered, for example, directly in Shopify Admin.
4.	Go to **Shopify Order**, and then to the **Fulfillment Orders** page, and check the statuses. Fulfillment orders indicate what you expect to ship. If they don't exist or are closed, nothing is sent to Shopify.
5.	Go to **Posted Sales Shipment**, and use Page Inspector to check the **Order ID** field in the header and the **Shopify Order line ID** in the lines. These fields determine whether to export the order to Shopify and link shipment lines to the original Shopify order lines. If the Shopify order line ID is missing on a posted shipment line (often due to manually recreated lines), the line isn’t included in the synchronization.

>[!Note]
> The **Update Document** page, which you can open for posted sales shipments, lets you replace *-1* and *-2* with *0* to retry the shipment export.

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

## Gift cards

In the Shopify shop, you can sell gift cards that customers can use to pay for products.

When dealing with gift cards, it's important to enter a value in the **Sold Gift Card Account** field in the **Shopify Shop Card** page. The sold gift card synchronizes together with the orders and added to sales document as line of type *G/L Account*.

An applied gift card also imports with the order, but now as a payment transaction. The gift card doesn't reduce the amount to invoice. To learn how to reconcile payment transaction, go to [Transactions and payouts](transactions-and-payouts.md).

To review the issued and applied gift cards, choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Gift Cards**, then choose the related link.

> [!NOTE]
> To import gift cards created manually or sold via old orders, that you don't want to import, you need to use configuration package. Use the 30110 **Shpfy Gift Card** table and **Id**, **Last Characters**, **Amount**. You can export gift cards from Shopify Admin. You need the **ID**, **Last Characters**, and **Current Balance** fields.

## Export posted sales invoices to Shopify

You can export posted sales invoices to Shopify so that buyers can sign in to Shopify and access all their invoices. Regardless of which app they were created in.

You can export posted sales invoices to Shopify as orders by using the **Sync Posted Invoices to Shopify** action on the Shopify Shop Card page, or you can use Tell Me search to find it. You can also run the report by using the job queue.

To enable the capability for a specific shop, go to the **Shopify Shop Card** page and turn on the **Posted Invoice Sync** toggle. You also need to configure the **Payment Terms Mapping**.

The sync includes invoices under the following conditions:

* The **Shopify Order ID** field contains **0**.
* The bill-to customer has a mapping in the **Shopify Customers** or **Shopify Companies** pages.
* The bill-to customer isn't used as the default customer on the **Shopify Shop Card** or **Shopify Customer Template**.
* The posted invoice has at least one noncomment line where the **No.** field has a value.

When you run the report, the following things happen in [!INCLUDE [prod_short](../includes/prod_short.md)] and Shopify.

**Business Central**

Update the **Shopify Order ID** field based on the results of the sync:

* Successful export: update the **Shopify Order ID** field with the ID of the order in Shopify.
* Export failed: set "-1"
* Invoice is excluded from sync for a reason listed in the conditions mentioned earlier: set "-2"

>[!Note]
> The **Update Document** page, that you can open for posted sales invoice lets you replace -1 and -2 with 0 to retry the export of invoice.


**Shopify**

The Shopify connector does the following steps:

* Creates a draft order with header and item lines
* Converts the draft order it to an order

**Fields that export to order headers and lines**

The following fields export on the order header:

* The mapped bill-to customer/company is used.
* The **Fulfillment Status** field shows **Fulfilled**. Tracking details don't synchronize.
* The **Paid Status** field shows **Paid** or **Partially Paid**, based on the customer ledger entry linked to the sales invoice. For partially paid, it shows the **Remaining Amount** field.

The following fields export on the order lines:

* Items and lines of other types, such as **G/L Account** or **Item Charge** lines, export as custom products in Shopify.
* Shipping charges in Shopify aren't created. The shipping cost is registered as a custom product in Shopify.
* Tax amounts. Because the Graph API doesn't currently support the TaxLine object, the calculated tax is added as a custom product. Tax information from [!INCLUDE [prod_short](../includes/prod_short.md)] isn’t available in the tax report in Shopify Admin. To prevent Shopify from recalculating taxes, orders are marked as **Tax Exempt**.
* Quantity, in whole numbers. Shopify doesn’t support fractions.
* For lines of the type **Items**, weight is exported. The weight comes from the **Net Weight** field of the sales invoice line. The **Weight Unit** from the **Shopify Shop Card** page is used as a unit of measure.

### Effect on the process of synchronizing orders

Synchronization imports the order and checks whether it was exported earlier. If it was exported earlier:

* It marks the order as processed.
* It adds a link to the posted sales invoice (related documents, should happen automatically because the Shopify Order ID is already populated). Shopify might automatically archive fully paid and fulfilled orders, and synchronization doesn't process them.

### Deal with updates

In Shopify, because the order is already fulfilled, the only meaningful changes are notes, payment status, and payment transactions. If payments are processed in Shopify, refunds and returns are as well.

[!INCLUDE [prod_short](../includes/prod_short.md)] doesn't track changes. Currently, if you want to mark the order as paid, use the **Mark as Paid** action on the **Shopify Order Card** page.

## Related information

[Shopify Connector overview](shopify-connector-overview.md)  
[FAQ for the Shopify connector](shopify-faq.md)  
[Troubleshoot the Shopify Connector](troubleshoot.md)  
[Walkthrough: Setting Up and Using Shopify Connector](walkthrough-setting-up-and-using-shopify.md)  
