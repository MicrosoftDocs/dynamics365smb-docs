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


