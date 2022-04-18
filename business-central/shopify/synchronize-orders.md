---
title: 
description: 
ms.date: 03/21/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
manager: 
---

# Setup Order Processing

On the **Shopify Shop Card**, you can define some setup for order processing.

- **Shipping Cost Account**  
    Define the g/l account that should be used for shipping costs.

- **Sold Gift Card Account**  
    Define the g/l account that should be used for the sale of gift cards.

- **Tip account**  
    Define the g/l account that should be used for obtained tips.

- **Shopify Order No. on Doc. Line**  
    Check this option if you want to create sales line of type Comment with Shopify order number.

- **Auto Create Orders**  
    Select if sales document in [!INCLUDE[prod_short](../includes/prod_short.md)] must be created automatically.

- **Tax area source  
    **Define your tax area source and the sequence that needs to be followed.

    -   No taxes
    -   Ship-to &gt; Sell-to &gt; Bill-to
    -   Ship-to &gt; Bill-to &gt; Sell-to
    -   Sell-to &gt; Ship-to &gt; Bill-to
    -   Sell-to &gt; Bill-to &gt; Ship-to
    -   Bill-to &gt; Sell-to &gt; Ship-to
    -   Bill-to &gt; Ship-to &gt; Sell-to

## Shipment method translations

When you have synchronized orders, the Shopify delivery methods are retrieved in [!INCLUDE[prod_short](../includes/prod_short.md)]. Go to your Shopify Shop and open the 'Shipment Method Translations'.

Name is the delivery method in Shopify. In 'Code', you set the corresponding shipping method in [!INCLUDE[prod_short](../includes/prod_short.md)].

>[!NOTE] if multiple shipping charges assosiated with Sales Order - only one will be used in the Header.

## Shipping agents

When you navigate to the list of Shipping agents in [!INCLUDE[prod_short](../includes/prod_short.md)], the column 'Shopify Tracking Company' is added. Select the tracking company in Shopify where you can track your items.

![](media/image77.png)

## Payment method translations

When you have synchronized orders, the Shopify payment methods are retrieved in Business Central. Go to your Shopify Shop and open the 'Shipment payment Translations'.

You can define Payment Method translations for your Shopify Shop. The fields 'Gateway' and 'Credit Card Company' retrieved from Shopify. In 'Payment method' you define the corresponding method in [!INCLUDE[prod_short](../includes/prod_short.md)].

If a customer pays part via visa card and part via maestro, you can assign priorities. The payment method with the highest priority will be entered in the order. If both payment methods have the same priority, the payment method of the highest amount will be used.





## Execute Order Synchronization

There are number of possibilities to perform import and update of sales orders.
>[!NOTE] Archived orders in Shopify will can not be imported. Disable **Automatically archive the order** in the **Order Processing** section of the **Checkout** settings in your **Shopify admin** to make sure that all orders are imported to [!INCLUDE[prod_short](../includes/prod_short.md)]. If you need to import archived order, use **Unarchive Orders** action in the [Orders](https://www.shopify.com/admin/orders) page of Shopify Admin.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and then choose the related link.
2. Select the Shop for which you want to synchronize items to open **Shopify Shop Card** page.
3. Choose the **Orders** action. 
4. Choose **Sync Orders From Shopify**
5. Define filters on orders as necessary. For example you can import fully paid orders or with low risk level.
6 Click ok.

Alternativelly you can search for **Sync Orders From Shopify** batch job.

>[!NOTE] You can navigate to the **Shopify Orders** window directly, in this case you will see orders from all shops, but only open. To review completed orders you need to open **Shopify Orders** page from the specific **Shopify Shop Card** window.





# Synchronize orders from Shopify

Synchronize the orders from Shopify again to update the fulfillment status in [!INCLUDE[prod_short](../includes/prod_short.md)].

![](media/image106.png)

Enter your Shopify Shop

![](media/image107.png)

Open the Shopify Orders of the Shopify Shop

![](media/image108.png)

![](media/image109.png)

![](media/image110.png)



## Transactions

The transactions that took place in Shopify can be viewed in [!INCLUDE[prod_short](../includes/prod_short.md)] via 'Transactions'. They are synchronized together with the orders.

![](media/image112.png)

![](media/image113.png)




# Manually create customers

When the customer is not automatically created for one reason or another, it can be created manually.

In the Shopify Order, you can select a customer template code and create the customer via the function 'Create new customer' or you can select an existing customer.

![](media/image70.png)

![](media/image71.png)

In the Shopify Shop Customer List, you can select open the Shopify customer card and select an existing customer.

![](media/image72.png)


# Process Shopify Orders

Navigate to the Shopify Orders.

![](media/image90.png)

Edit the Shopify order.

![Graphical user interface  application  table Description automatically generated](media/image91.png)

On the Shopify Order Card, you can find all the information about the Shopify Order, for example the shipping costs, fulfillments, risk level … You can navigate easily to the Sales order, sales invoice.

![Graphical user interface  text  application Description automatically generated](media/image92.png)

Via 'Inspect', you can go to the 'Shopify Status Page' to see the order confirmation sent to the customer. The 'Retrieved Shopify Data' shows you the data from Shopify that was retrieved.

![Graphical user interface  application Description automatically generated](media/image93.png)

![Text Description automatically generated](media/image94.png)

If the customer is not found automatically, you can select the correct customer, or create a new customer directly from the Shopify Order.

![Graphical user interface  application Description automatically generated](media/image95.png)

When the customer is selected, you can process the Shopify Order to a Sales Order.

## By action 'Create Sales Document'

You can process the Shopify order to a sales order by using the action "Create Sales Document".

![Graphical user interface  text  application  email Description automatically generated](media/image96.png)

![Graphical user interface  application  Word Description automatically generated](media/image97.png)

A sales order is now created and can be handled by using the standard Dynamics 365 Business Central functionalities.

![Graphical user interface  application Description automatically generated](media/image98.png)

Shipment costs are added to the sales order.
If you checked the field 'Shopify order no. on doc. Line', the Shopify order number is visible in the sales lines.

Remark: If no sales order can be created for the Shopify Order, an error message is displayed.

![Graphical user interface  application  table Description automatically generated](media/image99.png)

<u>Remark:</u> If no sales order can be created for the Shopify Order, an error message is displayed.

![](media/image100.png)




# Synchronize Shipments to Shopify

When a sales order that is created from a Shopify Order, is shipped, you can synchronize the shipments to Shopify.

The customer will automatically receive a shipment notice email.
When a Shipping Agent and a Tracking Code is specified on the shipment, the tracking information will be included in the email.

>[!NOTE] Remember to execute Synchronize Orders from Shopify because the batch job not only imports status of order - like Fulfilled, but also archives completelly paid and fulfilled orders in both Shopify and in [!INCLUDE[prod_short](../includes/prod_short.md)]

![](media/image102.png)

## By batch task

You can synchronize the shipment by executing the task "Synchronize Shipments To Shopify".

This task can be found by using the search function on the Role Center.

![](media/image103.png)

![](media/image104.png)

