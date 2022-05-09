---
title: Troubleshoot
description: Learn what to do if something when wrong during synchronization of data between Shopify and Business Central
ms.date: 03/21/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
manager: 
---


# Troubleshoot

## Logs

If a synchronization task fails, you can activate logging by enabling **Log Enable** toggle in the **Shopify Shop Card** and manually trigger synchronization task and review logs.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Log Entries**, and then choose the related link.
2. Select related log entry and open the **Shopify Log Entry** window.
3. Review request, status code and description, response.

Remember to disable logging to avoid negative performance impact and increasing size of database.

From the **Shopify Log Entries** window you can trigger deletion of all log entries or ones that are older than 7 days.

## Data Capture

Regardless of the **Log Activated** setting, system always logs some responses from Shopify that you can inspect or download using the **Data Capture List** windows.

Choose the **Retrieved Shopify Data** action in one of following pages:
- **Shopify Order**
- **Shopify Order Fulfillments**
- **Shopify Order Shipping Costs**
- **Shopify Order Transactions**
- **Shopify Payouts**
- **Shopify Payment Transactions**
- **Shopify Transactions**

## Reset sync

For performance reason system imports only Customers, Product, and Orders created or changed since previous synchronization. On the **Shopify Shop card**, there are functions available to change date/time of previous synchronization or completely reset it. This function ensures that when the sync is executed, all data is synced and not just the changes that have happened compared to the previous sync.

This function only applies to syncs from Shopify to [!INCLUDE[prod_short](../includes/prod_short.md)] and can be useful if you need to restore deleted master data and or order.

## Update access token

If [!INCLUDE[prod_short](../includes/prod_short.md)] can not connect to your Shopify account, try resetting access token.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and then choose the related link.
2. Select the Shop for which you want to get access token to open **Shopify Shop Card** page.
3. Fill in the **Code** field.  
4. Choose the **Request Access** action.
5. If prompted login into your Shopify account.
