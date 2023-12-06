---
title: Troubleshooting the Shopify and Business Central Synchronization
description: Learn what to do if something goes wrong when you synchronize data between Shopify and Business Central.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 04/24/2023
ms.custom: bap-template
ms.search.form: 30118, 30119, 30120, 30101, 30102 
---

# Troubleshooting the Shopify and Business Central Synchronization

You might run into situations where you need to troubleshoot issues when synchronizing data between Shopify and [!INCLUDE[prod_short](../includes/prod_short.md)]. This page defines troubleshooting steps for some typical scenarios.

## Run tasks in the foreground

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and choose the related link.
2. Select the shop for which you want to troubleshoot to open the **Shopify Shop Card** page.
3. Turn off the **Allow Background Syncs** toggle.

Now, when the sync action is triggered the task runs in the foreground. If an error occurs, you get an error dialog with a **Copy details** link. Use the link to copy information to a text editor for further analysis.

## Logs

The logging features can make it easier to identify why an error occurred. On the **Shopify Shop Card** page, in the **Logging Mode** field, you can specify the level of detail you want to capture about errors. The field provides the following options:

- **Disabled** - Don't log information about errors.
- **Error Only** - Log only the error message, without the request/response pairs. This setting is the default for new shops.
- **All** - Log the request/response pairs for all transactions, including those that were successful. Logging all errors continuously can slow down [!INCLUDE [prod_short](../includes/prod_short.md)]. Use this mode when the data exchange doesn't result in error, but you want to get more insights about the data that was actaully sent and received. Note that some data is always logged, regardless of whether logging is turned on. For more information, see [Data capture](#data-capture).

### To review logs

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Log Entries**, and choose the related link.
2. Select the related log entry, and then open the **Shopify Log Entry** page.
3. Review the request, status code and description, and response values.

> [!TIP]
> If you must contact Shopify support for help with troubleshooting, note the information in the **Request ID** field. That information can help support resolve the issue more quickly.

You can download the request and response values as files in a text format.

### Manage log entry data

To help keep the size of your database under control, log entries are included in a data retention policy named **Shpfy Log Entry**. Retention policies let you specify how long you want to store different types of data. By default, Shopify log entries are kept for one month. To learn more about retention policies, go to [Define Retention Policies](../admin-data-retention-policies.md).

Also, on the **Shopify Log Entries** page, you can delete all log entries, or just the entries that are older than seven days.

## Data capture

Regardless of whether logging is turned on, some Shopify responses are always logged. You can inspect or download the logs from the **Data Capture List** page.

Choose the **Retrieved Shopify Data** action on one of the following pages:

- **Shopify order**
- **Shopify order line**
- **Shopify fulfillments**
- **Shopify order shipping costs**
- **Shopify order transactions**
- **Shopify return**
- **Shopify return line**
- **Shopify refund**
- **Shopify refund line**
- **Shopify payouts**
- **Shopify payment transactions**
- **Shopify transactions**

## Reset sync

For optimal performance, the connector imports only customers, products, and orders that were created or changed after the last synchronization. On the **Shopify Shop Card** page, there are functions that change the date/time of the last synchronization, or completely reset it. This function ensures that all data synchronizes, rather than just the changes since the last sync.

This function only applies to syncs from Shopify to [!INCLUDE[prod_short](../includes/prod_short.md)]. It can be useful if you need to restore deleted data such as products, customers, or deleted orders.

## Request the access token

If [!INCLUDE[prod_short](../includes/prod_short.md)] won't connect to your Shopify account, try to request the access token from Shopify. You might need to request a new token if there were changes to the security keys or required permissions (application scopes).

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify shops**, and choose the related link.
2. Select the shop for which you want to get the access token to open the **Shopify Shop Card** page.
3. Choose the **Request Access** action.
4. If prompted, sign in to your Shopify account.

The **Has AccessKey** toggle is turned on.

## Verify and enable permissions to make HTTP requests in a non-production environment

To work correctly, the Shopify Connector extension requires permission to make HTTP requests. HTTP requests are prohibited for all extensions when you run tests in sandbox environments.

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Extension Management**, and then choose the related link.
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

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify shops**, and then choose the related link.
2. Select the shop for which you want to rotate the access token to open the **Shopify Shop Card** page.
3. Choose the **Request Access** action.
4. If prompted, sign in to your Shopify account, review privacy and permissions, and then choose the **Install App** button.

## Known issues

### Error: The Sales Header does not exist. Identification fields and values: Document Type='Quote',No.='YOUR SHOPIFY STORE'

To calculate prices, the Shopify Connector creates a temporary sales document (quote) for a temporary customer (Shop Code) and uses the standard price calculation logic. If a third-party extension subscribes to events on a temporary sales document, the header might not be available. We recommend that you contact the extension provider. Ask them to modify their code to check for temporary records. In some cases, they just need to add the `IsTemporary` method ìn the right place. To learn more about `IsTemporary`, go to [IsTemporary](/dynamics365/business-central/dev-itpro/developer/methods-auto/record/record-istemporary-method). 

To verify that the problem is caused by a third-party extension, use the **Copy information to clipboard** link in the error message and copy the content to a text editor. The information contains an **AL call stack**, where the top line is the line where the error occurred. The following example shows an AL call stack.

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

### Error: Gen. Bus. Posting Group must have a value in Customer: 'YOUR SHOPIFY STORE'. It cannot be zero or empty

On the **Shopify Shop Card** page, in the **Customer Template Code** field, choose the template that has **Gen. Bus. Posting Group** populated. The customer template is used to create customers and to calculate sales prices on sales documents.

### Error: Importing data to your Shopify shop isn't enabled. Go to the shop card to enable it

On the **Shopify Shop Card** page, turn on the **Allow Data Sync to Shopify** toggle. This setting helps protect the online shop from getting demo data from [!INCLUDE[prod_short](../includes/prod_short.md)].

### Error: Oauth error invalid_request: Could not find Shopify API application with api_key

It seems you use the [Embed App](/dynamics365/business-central/dev-itpro/deployment/embed-app-overview), where the client URL has the format: `https://[application name].bc.dynamics.com`. The Shopify connector doesn't work for Embed Apps. To learn more, go to [Which Microsoft products are the Shopify connector available for?](shopify-faq.md#which-microsoft-products-are-the-shopify-connector-available-for).

### Error: Internal Error. Looks like Something Went Wrong on Our End. Request ID: XXXXXXXX-XXXX-XXXX-XXXX-XXXX

Contact Shopify support within seven days of experiencing this error, and provide the Request ID. To learn more, go to [Support options for Shopify](shopify-faq.md#shopify).

### Error: Oauth error invalid_request: Your account does not have permission to grant the requested access for this app. 

It seems that user which requests access doesn’t have rights to manage apps (ability to manage and install apps and channels, as well as potentially approve app charges). You may be able to resolve this issue by installing the app as the account owner. Alternatively you can check the **App permission** for the user in the [**User and permissions**](https://www.shopify.com/admin/settings/account) settings in your **Shopify admin**.  

### [{"message":"Access denied for FIELD field.","locations":[{"line":0,"column":0}],"path":["path"],"extensions":{"code":"ACCESS_DENIED","documentation":https://shopify.dev/api/usage/access-scopes}}]

Request a new token because the updated version of the connector requires more permissions (application scopes). To learn more, go to [Request access token](#request-the-access-token).

## See also

[Get Started with the Connector for Shopify](get-started.md)
