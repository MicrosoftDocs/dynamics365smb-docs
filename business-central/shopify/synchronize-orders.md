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

On the tab 'Order Processing' of the Shopify Shop Card, you can define some setup for order processing.

![](media/image73.png)

- **Shipping Cost Account**  
    Define the g/l account that should be used for shipping costs.

- **Sold Gift Card Account**  
    Define the g/l account that should be used for the sale of gift cards.

- **Tip account**  
    Define the g/l account that should be used for obtained tips.

- **Shopify Order No. on Doc. Line  
 **Check this option if you want to show the Shopify order number on the sales lines.

![](media/image74.png)

- **Auto Create Orders**  
    Determine whether order in Microsoft Dynamics 365 Business Central may be created automatically.

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

When you have synchronized orders, the Shopify delivery methods are retrieved in Business Central. Go to your Shopify Shop and open the 'Shipment Method Translations'.

Name is the delivery method in Shopify. In 'Code', you set the corresponding shipping method in Microsoft Dynamics 365 Business Central.

![](media/image75.png)

![](media/image76.png)

## Shipping agents

When you navigate to the list of Shipping agents in Microsoft Dynamics 365 Business Central, the column 'Shopify Tracking Company' is added. Select the tracking company in Shopify where you can track your items.

![](media/image77.png)

## Payment method translations

When you have synchronized orders, the Shopify payment methods are retrieved in Business Central. Go to your Shopify Shop and open the 'Shipment payment Translations'.

![](media/image78.png)

You can define Payment Method translations for your Shopify Shop. The fields 'Gateway' and 'Credit Card Company' retrieved from Shopify. In 'Payment method' you define the corresponding method in Microsoft Dynamics 365 Business Central.

If a customer pays part via visa card and part via maestro, you can assign priorities. The payment method with the highest priority will be entered in the order. If both payment methods have the same priority, the payment method of the highest amount will be used.

![](media/image79.png)






# Execute Order Synchronization

## By batch task

When an order is placed in Shopify, you can synchronize this to Dynamics 365 Business Central by executing the task "Sync Orders from Shopify".

You can find this task by using the search function from the Role Center:

![](media/image80.png)

![](media/image81.png)

It is possible to apply filters to synchronize only a limited number of orders, e.g. only those who have been paid in full or whose risk level is low.

When executing this task, the Shopify Orders are imported in Dynamics 365 Business Central.

## By action 'Sync orders from Shopify'

When you navigate to the Shopify Orders via your Shopify Shop, you can execute the function 'Sync Orders From Shopify' to synchronize the orders from your Shopify Account.

![Graphical user interface  text  application Description automatically generated](media/image82.png)

![Graphical user interface  application Description automatically generated](media/image83.png)

## By job queue

You can also schedule a job that runs for example every few minutes.

You can find the job queue entries by using the search function from the Role Center:

![](media/image84.png)

Define the recurrence of the job queue and start the job queue 'Sync Orders from Shopify'.

![](media/image85.png)


# View Shopify Orders

You can find the Shopify Orders using the search function from the Role Center.

![](media/image86.png)

## All Shopify Orders

This are all the open orders of all Shopify Shop Accounts

![Graphical user interface  application Description automatically generated](media/image87.png)

## Shopify Orders of a specific shop

Navigate to the Shopify Shop to get an overview of all the Shopify Orders for this Shop.

![](media/image88.png)

![](media/image89.png)



# Synchronize orders from Shopify

Synchronize the orders from Shopify again to update the fulfillment status in Dynamics 365 Business Central.

![](media/image106.png)

Enter your Shopify Shop

![](media/image107.png)

Open the Shopify Orders of the Shopify Shop

![](media/image108.png)

![](media/image109.png)

![](media/image110.png)

## Reset sync

On the Shopify Shop card, there are functions available to reset the sync. This function ensures that when the sync is executed, all data is synced and not just the changes that have happened compared to the previous sync.

This function only applies to syncs from Shopify to Business Central.

![](media/image111.png)

## Transactions

The transactions that took place in Shopify can be viewed in Business Central via 'Transactions'. They are synchronized together with the orders.

![](media/image112.png)

![](media/image113.png)

##  Gift Cards

In the Shopify Shop, you can buy gift cards. When you synchronize orders, gift cards are also synchronized to 'Gift Cards'.

![](media/image114.png)

You get an overview of the sold gift cards and the used amount of de gift card with the relevant transactions.

![](media/image115.png)

## Payouts

If your store has Shopify Payments enabled, then you receive payments through Shopify Payouts when a customer pays using Shopify Payments and specific accelerated checkouts.

The payouts can also be synchronized to Microsoft Dynamics 365 Business Central.

Go to your Shopify Shop and execute 'Sync Payouts'.

![](media/image116.png)

You get an overview of the payouts if you navigate to 'Scaptify' and then to 'Payouts'. You get a view of the details of the payouts.

![](media/image117.png)

![](media/image118.png)

## Troubleshooting

When a synchronization task from / to Shopify fails, you can activate logging on the tab 'General' in the Shopify Shop Card:

![](media/image119.png)

After you start the synchronization task again, you can check the Scaptify Log Entries for any errors / information:

![](media/image120.png)

![](media/image121.png)

![](media/image122.png)

Make sure to disable the logging when not needed, or to delete the entries periodically.

![](media/image123.png)


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

## By job queue

You can also schedule a job to process the Shopify orders that runs for example every few minutes.

You can find the job queue entries by using the search function from the Role Center:

![](media/image84.png)

Define the recurrence of the job queue 'Process Shopify Orders' and start the job queue.

![](media/image101.png)
