---
title: Troubleshooting the Shopify and Business Central synchronization
description: Learn what to do if something goes wrong when you synchronize data between Shopify and Business Central.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 01/27/2025
ms.custom: bap-template
ms.search.form: 30118, 30119, 30120, 30101, 30102 
ms.service: dynamics-365-business-central
---

# Troubleshooting the Shopify and Business Central synchronization

You might run into situations where you need to troubleshoot issues when synchronizing data between Shopify and [!INCLUDE[prod_short](../includes/prod_short.md)]. This page defines troubleshooting steps for some typical scenarios.

## Run tasks in the foreground

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and choose the related link.
2. Select the shop for which you want to troubleshoot to open the **Shopify Shop Card** page.
3. Turn off the **Allow Background Syncs** toggle.

Now, when the sync action is triggered, the task runs in the foreground. If an error occurs, you get an error dialog with a **Copy details** link. Use the link to copy information to a text editor for further analysis.

## Logs

The logging features can make it easier to identify why an error occurred. On the **Shopify Shop Card** page, in the **Logging Mode** field, you can specify the level of detail you want to capture about errors. The field provides the following options:

- **Disabled** - Don't log information about errors.
- **Error Only** - Log only the error message, without the request/response pairs. This setting is the default for new shops.
- **All** - Log the request/response pairs for all transactions, including successful pairs. Logging all errors continuously can slow down [!INCLUDE [prod_short](../includes/prod_short.md)]. Use this mode when the data exchange doesn't result in error, but you want insights about the data that was sent and received. Some data is always logged, regardless of whether logging is turned on. For more information, see [Data capture](#data-capture).

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

## Troubleshoot export issues

When you export data to Shopify, the Shopify Connector skips records that Shopify will reject or that aren't valid for export for other reasons. While the behavior is expected, you might be confused if some information wasn't processed as you expected. You can find those entries on the **Shopify Skipped Records** page, which shows all skipped records and provides the reasons and the date and time the records were skipped.

The **Logging Mode** field controls the content of the **Shopify Skipped Records** page.

> [!NOTE]
> The **All** option works in the same way as **Error Only** and logs only skipped entries. It won't log entries that were previously skipped.

Over time, the number of records on the Shopify Skipped Records pageTo help you keep the size of your database under control, you can use a retention policy. To learn more about retention policies, go to [Define Retention Policies](/dynamics365/business-central/admin-data-retention-policies).

### Cases that the Shopify Connector logs

Customer:

- A customer has an empty email.
- A customer with the same email or phone number exists.

Posted sales invoice:

- Customer doesn't exist in Shopify.
- Payment term mapping is missing.
- Customer number is the default customer number for the Shopify Shop.
- Customer number is used in the Shopify customer template.
- No lines exist in the sales invoice.
- Invalid (negative or fractional) quantity.
- Empty number value.

Product:

- Item is blocked/sales blocked (item variant).
- Item is blocked.
- Item description is empty.

Catalog:

- Price sync if the catalog isn't found in Shopify.

Shipments:

- Related Shopify order doesn't exist.
- No lines in the posted sales shipment are applicable for fulfillment.
- No corresponding fulfillment is found in Shopify.

If you run sync in the foreground you will get a notification if records were skipped. Choose **View Skipped Records** to open the **Shopify Skipped Records** page.

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

If [!INCLUDE[prod_short](../includes/prod_short.md)] doesn't connect to your Shopify account, request the access token from Shopify. You might need to request a new token if there were changes to the security keys or required permissions (application scopes).

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify shops**, and choose the related link.
2. Select the shop for which you want to get the access token to open the **Shopify Shop Card** page.
3. Choose the **Request Access** action.
4. If prompted, sign in to your Shopify account.

The **Has AccessKey** toggle is turned on.

## Verify and enable permissions to make HTTP requests in a nonproduction environment

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

To calculate prices, the Shopify Connector creates a temporary sales document (quote) for a temporary customer (Shop Code) and uses the standard price calculation logic. If a partner extension subscribes to events on a temporary sales document, the header might not be available. We recommend that you contact the extension provider. Ask them to modify their code to check for temporary records. In some cases, they just need to add the `IsTemporary` method in the right place. To learn more about `IsTemporary`, go to [IsTemporary](/dynamics365/business-central/dev-itpro/developer/methods-auto/record/record-istemporary-method).

To verify that the problem is caused by a partner extension, use the **Copy information to clipboard** link in the error message and copy the content to a text editor. The information contains an **AL call stack**, where the top line is the line where the error occurred. The following example shows an AL call stack.

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

Remember to share the AL call stack information with the supplier of the extension.

### Error: Gen. Bus. Posting Group must have a value in Customer: 'YOUR SHOPIFY STORE'. It cannot be zero or empty

On the **Shopify Shop Card** page, in the **Customer Template Code** field, choose the template that has **Gen. Bus. Posting Group** populated. The customer template is used to create customers and to calculate sales prices on sales documents.

### Error: Importing data to your Shopify shop isn't enabled. Go to the shop card to enable it

On the **Shopify Shop Card** page, turn on the **Allow Data Sync to Shopify** toggle. This setting helps protect the online shop from getting demo data from [!INCLUDE[prod_short](../includes/prod_short.md)].

### Error: Oauth error invalid_request: Could not find Shopify API application with api_key

The [Embed App](/dynamics365/business-central/dev-itpro/deployment/embed-app-overview) might use the client URL with the format: `https://[application name].bc.dynamics.com`. The Shopify connector doesn't work for Embed Apps. To learn more, go to [Which Microsoft products work with the Shopify Connector?](shopify-faq.md#which-microsoft-products-work-with-the-shopify-connector).

### Error: Internal Error. Looks like Something Went Wrong on Our End. Request ID: XXXXXXXX-XXXX-XXXX-XXXX-XXXX

Contact Microsoft support via your Business Central partner within seven days of experiencing this error, and provide the Request ID. To learn more, see [Support for the Shopify Connector](shopify-support.md).

### Error: Oauth error invalid_request: Your account does not have permission to grant the requested access for this app

The user who requested access doesn’t have the rights to manage apps (the ability to manage and install apps and channels, as well as potentially approve app charges). You might be able to resolve  issue by installing the app as the account owner. Alternatively, you can check the **App permission** for the user in the [**User and permissions**](https://www.shopify.com/admin/settings/account) settings in your **Shopify admin**.  

### You need permissions to update Dynamics 365 Business Central. Ask the store owner to update this app. Or contact them for access to: [PERMISSION]

The updated version of the connector requires more permissions (application scopes) than the user who requested access has. You might be able to resolve this issue by installing the app as the account owner. Alternatively, you can check the **App permission** for the user in the [**User and permissions**](https://www.shopify.com/admin/settings/account) settings in your **Shopify admin**. If the required permissions are missing, which you can see in the error message, ask the account owner to grant the required permissions.

### Error: The application scope is changed, please request a new access token for the store 'YOUR SHOPIFY STORE'

Request a new token because the updated version of the connector requires more permissions (application scopes). To learn more, go to [Request access token](#request-the-access-token).

### [{"message":"Access denied for FIELD field.","locations":[{"line":0,"column":0}],"path":["path"],"extensions":{"code":"ACCESS_DENIED","documentation":https://shopify.dev/api/usage/access-scopes}}]

Request a new token because the updated version of the connector requires more permissions (application scopes). To learn more, go to [Request access token](#request-the-access-token).

### [API] Invalid API key or access token (unrecognized login or wrong password)

Request a new token because the updated version of the connector requires more permissions (application scopes). To learn more, go to [Request access token](#request-the-access-token).

### The app couldn’t be loaded. This app can’t load due to an issue with browser cookies. Try enabling cookies in your browser, switching to another browser, or contacting the developer to get support

It seems that you tried to get an access token multiple times. Make sure that the browser allows pop-ups. If you're using a sandbox environment, [Verify and enable permissions to make HTTP requests in a nonproduction environment](#verify-and-enable-permissions-to-make-http-requests-in-a-nonproduction-environment).

## See also

[Get Started with the Connector for Shopify](get-started.md)
