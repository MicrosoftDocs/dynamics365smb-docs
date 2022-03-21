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

