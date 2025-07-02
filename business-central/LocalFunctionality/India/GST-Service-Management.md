---
title: GST on Service Management
description: Learn how GST is applied to service management processes in Business Central for India, including service orders, invoices, and credit memos.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, service management, service order, service invoice, service credit memo
ms.date: 06/24/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# GST on service management

Business Central has included GST on Service Management feature to Indian Localization.

Service Management has been designed to streamline your organization’s service operations, enhancing efficiency and profitability. Easily manage customer calls and queries, track support tickets, allocate resources, create reports. GST is an integral part of the service management and this article explains the process of GST calculation on **Service Order**, **Service Invoice**, and **Service Credit Memo**.

## GST on service order

- Create Service Order

  1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Service Order**, and then choose the related link.
  1. Select relevant **Customer Code** in **Customer No.** field. **GST Customer Type** field should have a value on Customer Card.
  1. Then go to Service Order **Line** Tab > select **Order** > **Service Lines**. Select Item Code for Goods, G/L Account for Service Sales, Resource or Service Cost on **Service line**. **GST Group Code**, **HSN/SAC** Code shouldn't be blank on the Item, G/L Account, Resource or Service Cost.

## GST on service invoice

- Create Service Invoice

  1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Service Invoice**, and then choose the related link.
  1. Select relevant **Customer Code** in **Customer No.** field. **GST Customer Type** field should have a value on Customer Card.
  1. Select Item Code for goods, G/L Account for service sales, Resource or Service Cost on Service Invoice line. **GST Group Code**, **HSN/SAC** Code shouldn't be blank on the Item, G/L Account, Resource or Service Cost.
  
## GST on service credit memos

- Create Service Credit Memos

  1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Service Credit Memos**, and then choose the related link.
  1. Select relevant **Customer Code** in **Customer No.** field. **GST Customer Type** field should have a value on Customer Card.
  1. Select Item Code for goods, G/L Account for service sales, Resource or Service Cost on Service Credit Memo line. **GST Group Code**, **HSN/SAC** Code shouldn't be blank on the Item, G/L Account, Resource or Service Cost.

> [!NOTE]
> Accounting entries are similar to accounting entries generated for sales transactions.

## Related information

[GST Input Service Distribution Overview](GST-Input-Service-Distribution-Overview.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]