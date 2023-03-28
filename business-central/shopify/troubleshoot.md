---
title: Troubleshooting the Shopify and Business Central Synchronization
description: Learn what to do if something goes wrong during the synchronization of data between Shopify and Business Central
ms.date: 03/27/2023
ms.topic: article
ms.service: dynamics365-business-central
ms.search.form: 30118, 30119, 30120, 30101, 30102 
author: edupont04
ms.author: andreipa
ms.reviewer: solsen
---

# Troubleshooting the Shopify and Business Central Synchronization

You might run into situations where you need to troubleshoot issues when synchronizing data between Shopify and [!INCLUDE[prod_short](../includes/prod_short.md)]. This page defines troubleshooting steps for some typical scenarios.

## Run tasks in the foreground

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and choose the related link.
2. Select the shop for which you want to troubleshoot to open the **Shopify Shop Card** page.
3. Turn off the **Allow Background Syncs** toggle.

Now, when the sync action is triggered the task will run in the foreground and if an error occurs, you'll get an error dialog with **Copy details** link. Use this link to copy additional information to a text editor for the further analysis.

## Logs

If a synchronization task fails, you can turn on the **Log Enabled** toggle on the **Shopify Shop Card** page to activate logging. Then you can manually trigger the synchronization task and review logs.

### To enable logging

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and choose the related link.
2. Select the shop for which you want to troubleshoot to open the **Shopify Shop Card** page.
3. Turn on the **Log Enabled** toggle.

### To review logs

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Log Entries**, and choose the related link.
2. Select the related log entry and open the **Shopify Log Entry** page.
3. Review the request, status code and description, and response values. You can download the request and response values as files in a text format.

Later, remember to switch logging off to avoid negative performance impacts and increases in database size.

From the **Shopify Log Entries** page, you can trigger the deletion of all log entries or ones older than seven days.

## Data capture

Regardless of the **Log Activated** settings, some Shopify responses always get logged so you can inspect or download them using the **Data Capture List** page.

Choose the **Retrieved Shopify Data** action on one of the following pages:

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
2. Select the **Shopify Connector** extension.
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

### Error: The Sales Header does not exist. Identification fields and values: Document Type='Quote',No.='YOU SHOPIFY STORE'

To calculate prices the Shopify Connector creates temporary sales document (quote) for temporary customer (Shop Code) and lets the standard price calculation logic to do its job. It is typical scenario when a third party extension subscribes to events in sales line but doesn't check that the record is temporary, so the header might not be accessible. Our recommendation is to reach out to the supplier of the extension and ask them to modify their code to check whether records are temporary. In some cases, adding the `IsTemporary` method ìn the right place is enough. To learn more about IsTemporary, go to [IsTemporary](/dynamics365/business-central/dev-itpro/developer/methods-auto/record/record-istemporary-method). 

To verify that the problem is caused by a third party extension, use the **Copy information to clipboard** link in the error message and copy the content into text editor. The information contains an **AL call stack**, where the top line is the line where error occurred. The following is an example of an AL call stack.

AL call stack: 
```AL
[Object Name]([Object type] [Object Id]).[Function Name] line [XX] - [Extension Name] by [Publisher] 
...
"Sales Line"(Table 37)."No. - OnValidate"(Trigger) line 98 - Base Application by Microsoft
"Shpfy Product Price Calc."(CodeUnit 30182).CalcPrice line 20 - Shopify Connector by Microsoft
"Shpfy Create Product"(CodeUnit 30174).CreateTempProduct line 137 - Shopify Connector by Microsoft
"Shpfy Create Product"(CodeUnit 30174).CreateProduct line 5 - Shopify Connector by Microsoft
"Shpfy Create Product"(CodeUnit 30174).OnRun(Trigger) line 12 - Shopify Connector by Microsoft
"Shpfy Add Item to Shopify"(Report 30106)."Item - OnAfterGetRecord"(Trigger) line 2 - Shopify Connector by Microsoft
"Shpfy Products"(Page 30126)."AddItems - OnAction"(Trigger) line 5 - Shopify Connector by Microsoft
```

Remember to the share AL call stack information with the supplier of the extension.

### Error: Gen. Bus. Posting Group must have a value in Customer: 'YOU SHOPIFY STORE'. It cannot be zero or empty

On the **Shopify Shop Card** page, fill in the **Customer Template Code** field with the template that has **Gen. Bus. Posting Group** populated. The customer template is used not only for the creation of customers but also for the calculation of the sales price and during the creation of sales documents.

### Error: Importing data to your Shopify shop isn't enabled. Go to the shop card to enable it

On the **Shopify Shop Card** window, turn on the **Allow Data Sync to Shopify** toggle. This toggle is intended to protect the online shop from getting demo data from [!INCLUDE[prod_short](../includes/prod_short.md)].

### Error: Oauth error invalid_request: Could not find Shopify API application with api_key

It seems you use the [Embed App](/dynamics365/business-central/dev-itpro/deployment/embed-app-overview), where the client URL has the format: `https://[application name].bc.dynamics.com`. The Shopify connector doesn't work for Embed Apps. For more information, see [Which Microsoft products are the Shopify connector available for?](shopify-faq.md#which-microsoft-products-are-the-shopify-connector-available-for).

## See also

[Get Started with the Connector for Shopify](get-started.md)
