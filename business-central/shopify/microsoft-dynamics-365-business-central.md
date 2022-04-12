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

#TBD - move to other articles:
====================



## Setup Shops


-   Select the language code.   //TBD: to be moved to Customer sync

-   Activate the log.   //TBD: to be moved to "other, part trouleshouting. 

-   Select 'Allow Background Syncs' if you want to run the synchronization in background.    //TBD: to be moved to "other, part trouleshouting. 



-   Select how want to import your customers from Shopify

    -   Not

    -   With order import

    -   All customers

-   Select how you want to map customers

    -   By email/phone

    -   By bill-to info

-   Select if you automatically want to create unknown customers.

-   Select a customer template based on which customers from Shopify, automatically or not, are created in Dynamics 365 Business Central.

-   Define which fields in Business Central needs to be filled with which fields in Shopify.

-   Select a customer on which the orders should be created if you do not want to create a customer in Business Central for each customer in Shopify.

-   Define if you only want to create or also update customers.

-   Define if you want to export your customers to Shopify.

![](media/image23.png)

The last step is to do some settings for order processing.

-   Enter the 'Shipping cost Account', the Sold Gift Card account and the Tip account.

-   Select if you want to show your Shopify Order No. in the lines of your Sales document in Dynamics 365 Business Central

-   Tax Area Source

**There are some <u>restrictions</u> for the Tax/VAT setup.**

-   The VAT/Tax setup must be the same in the Shopify shop and in Business Central.

-   When you use multiple VAT/tax percentages, Business Central should be leading. If Business Central is not leading and you use Collections in Shopify to handle Taxes you should use the same naming convention in Business Central for Tax setup, furthermore, the item should already exist in Business Central. When this is not the case a new item is created based on the defined item template and uses the VAT/tax percentage defined in this template, not the one set in the Shopify Shop.


