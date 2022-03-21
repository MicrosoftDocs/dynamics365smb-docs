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


