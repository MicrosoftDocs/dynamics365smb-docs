---
title: Troubleshooting the Shopify and Business Central synchronization
description: Learn what to do if something goes wrong during the synchronization of data between Shopify and Business Central
ms.date: 08/19/2022
ms.topic: article
ms.service: dynamics365-business-central
ms.search.form: 30118, 30119, 30120, 
author: edupont04
ms.author: andreipa
ms.reviewer: solsen
---

# Troubleshooting Shopify and Business Central synchronization

It's possible to run into situations where you need to troubleshoot issues when synchronizing data between Shopify and [!INCLUDE[prod_short](../includes/prod_short.md)]. This page defines troubleshooting steps for some common scenarios that may occur.

## Logs

If a synchronization task fails, you can activate logging by enabling the **Log Enable** toggle on the **Shopify Shop Card** page. Then you can manually trigger the synchronization task and review logs.

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Log Entries**, and choose the related link.
2. Select the related log entry and open the **Shopify Log Entry** page.
3. Review the request, status code and description, and response values.

Later,remember to switch logging off to avoid negative performance impacts and increases in database size.

From the **Shopify Log Entries** page, you can trigger the deletion of all log entries or ones older than seven days.

## Data capture

Regardless of the **Log Activated** settings, some Shopify responses always get logged so you can inspect or download them using the **Data Capture List** page.

Choose the **Retrieved Shopify Data** action on one of following pages:

- **Shopify order**
- **Shopify order fulfillments**
- **Shopify order shipping costs**
- **Shopify order transactions**
- **Shopify payouts**
- **Shopify payment transactions**
- **Shopify transactions**

## Reset sync

For optimal performance, the connector imports only customers, products, and orders created or changed since the last synchronization. On the **Shopify Shop Card** page, there are functions that change the date/time of the last synchronization or completely reset it. This function ensures that when the sync is run, all data is synced rather than just the changes since the last sync.

This function only applies to syncs from Shopify to [!INCLUDE[prod_short](../includes/prod_short.md)]. It can be useful if you need to restore deleted data such as products, customers, or deleted orders.

## Request the access token

If [!INCLUDE[prod_short](../includes/prod_short.md)] won't connect to your Shopify account, try to request the access token from Shopify. This request might be needed if there is a rotation of security keys or changes in required permissions (scopes).

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify shops**, and choose the related link.
2. Select the shop for which you want to get the access token to open the **Shopify Shop Card** page.
3. Choose the **Request Access** action.
4. If prompted, sign in to your Shopify account.

The **Has AccessKey** toggle will be activated.

### Verify and enable permissions to make http requests when running in a non-production environment

To work correctly, the Shopify Connector extension requires permission to make http requests. When testing in a sandbox, the http requests are prohibited for all extensions.

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **extension management**, and choose the related link.
2. Select the *Shopify Connector* extension.
3. Choose the **Configure** action to open the **Extension Setting** page.
4. Make sure that the **Allow HTTPClient Requests** toggle is enabled.

## Rotate the Shopify access token

The following procedures describe how to rotate the access token used by the Shopify connector to access your Shopify online shop.

### In Shopify

1. From your **Shopify Admin**, go to [Apps](https://www.shopify.com/admin/apps).
2. Select **Delete** in the row with the **Dynamics 365 Business Central** app.
3. Select **Delete** in the message that appears.

### In [!INCLUDE[prod_short](../includes/prod_short.md)]

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify shops**, and choose the related link.
2. Select the shop for which you want to rotate the access token to open the **Shopify Shop Card** page.
3. Choose the **Request Access** action.
4. If prompted, sign in to your Shopify account, review privacy and permissions, and then choose the **Install App** button.

## Known issues

The *Gen. Bus. Posting Group* cannot be zero or empty; there must be a value in the customer field. To correct:

On the **Shopify Shop Card** page, fill in the **Customer Template Code** field with the template that has **Gen. Bus. Posting Group** populated. The customer template is used not only for the creation of customers, but also for calculation of the sales price and during the creation of sales documents.

### Importing data to your Shopify shop isn't enabled. Go to the shop card to enable it

On the **Shopify Shop Card** window, turn on the **Allow Data Sync to Shopify** toggle.  This toggle is intended to protect the online shop from getting demo data from [!INCLUDE[prod_short](../includes/prod_short.md)].

## See also

[Get Started with the Connector for Shopify](get-started.md)