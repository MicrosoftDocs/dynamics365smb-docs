---
title: Getting started with connector for Shopify
description: First steps when configuring connection between Business Central and Shopify
ms.date: 03/27/2023
ms.topic: article
ms.service: dynamics365-business-central
ms.reviewer: solsen
ms.search.form: 30100, 30101, 30102, 30103, 30104, 30135, 
author: brentholtorf
ms.author: bholtorf
---

# Get Started with the Shopify Connector

Connect your Shopify store (or stores) with [!INCLUDE [prod_short](../includes/prod_short.md)] and maximize your business productivity. Manage and view insights from your business and your Shopify store as one unit.

To use Shopify with [!INCLUDE [prod_short](../includes/prod_short.md)], there are a couple of things you have to do first. This article serves as a guide to integrate your Shopify store with [!INCLUDE [prod_short](../includes/prod_short.md)].

## Prerequisites for Shopify

You must have:

- A Shopify account
- A Shopify online store

To learn more about how to create Shopify trials and the recommended settings, go to [Creating and Setting Up Shopify Account](shopify-account.md).

## Prerequisites for Business Central

- Make sure that the **[Shopify Connector](https://go.microsoft.com/fwlink/?linkid=2196238)** app is installed.

  The app is pre-installed for all new sign-ups and trials. Learn more about installing apps from AppSource at [Installing and Uninstalling Extensions](../ui-extensions-install-uninstall.md#install). Follow the steps listed below if you don't have [!INCLUDE[prod_short](../includes/prod_short.md)].

- Ensure that the user has the right permissions. Shopify Connector is covered by the **Shopify – Admin (SHPFY – ADMIN)** permission set. Learn more at [Create Users According to Licenses](../ui-how-users-permissions.md) and [Assign Permissions to Users and Groups](../ui-define-granular-permissions.md).

## Install the Dynamics 365 Business Central app to your Shopify online store

For existing instances of [!INCLUDE[prod_short](../includes/prod_short.md)], this step is optional and can be skipped.

1. Locate the [Dynamics 365 Business Central](https://apps.shopify.com/dynamics-365-business-central) app on the [Shopify AppStore](https://apps.shopify.com/)
2. Choose the **Add App** button. Sign in to your Shopify account if prompted. Select the online shop if you have more than one.
3. After reviewing privacy and permissions, choose the **Install App** button.

   You can find and open the installed **Dynamics 365 Business Central** app in the **Apps** section on the sidebar of the **Shopify admin** page.
4. Choose **Sign up now** to start the [!INCLUDE[prod_short](../includes/prod_short.md)] trial, or **Sign in** if you already have [!INCLUDE[prod_short](../includes/prod_short.md)]. You'll be redirected to your [Business Central](https://businesscentral.dynamics.com) page.
5. Do the next steps in [!INCLUDE[prod_short](../includes/prod_short.md)].

## Connect Business Central to the Shopify online store

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop** and choose the related link.
2. Choose the **New** action.  
3. In the **Code** field, enter a code that will make it easy to find in [!INCLUDE[prod_short](../includes/prod_short.md)]. For example, the name might reflect what a shop sells, such as "Furniture" or "Coffee", or the country or region it serves.
4. In the **Shopify URL** field, enter the URL of the online shop that you're connecting. Use the following format: `https://{shop}.myshopify.com/`.
5. Turn on the **Enabled** toggle, and then review and accept the terms and conditions.
6. If prompted, sign in to your Shopify account. Review the privacy terms and permissions, and then choose the **Install App** button.

Repeat steps 2-6 for all online shops that you want to connect.

### Known issues

- The browser blocks the pop-up window. When you turn on the **Enabled** toggle, [!INCLUDE [prod_short](../includes/prod_short.md)] opens the **Waiting for a response - do not close this page** page while it waits for an access token from Shopify. If that page is closed or blocked, you can't connect to Shopify. Learn more at [Request the access token](troubleshoot.md#request-the-access-token)
- It might be a good idea to have Shopify admin open in the same browser as [!INCLUDE [prod_short](../includes/prod_short.md)]
- [Error: Oauth error invalid_request: Could not find Shopify API application with api_key](troubleshoot.md#error-oauth-error-invalid_request-could-not-find-shopify-api-application-with-api_key)
- [Error: Oauth error invalid_request: Your account does not have permission to grant the requested access for this app.](troubleshoot.md#error-oauth-error-invalid_request-your-account-does-not-have-permission-to-grant-the-requested-access-for-this-app)
- [Can't connect from sandbox](troubleshoot.md#verify-and-enable-permissions-to-make-http-requests-in-a-non-production-environment)

## Next steps

Now your online shop is connected to [!INCLUDE[prod_short](../includes/prod_short.md)]. In the next steps, you'll define how and what to synchronize.

- [Synchronize Items](synchronize-items.md)
- [Synchronize Customers](synchronize-customers.md)
- [Synchronize Orders](synchronize-orders.md)

## Testing strategies

There are different approaches to testing an integration, and each approach has its pros and cons.

You can connect [!INCLUDE[prod_short](../includes/prod_short.md)] and Shopify accounts as often as you like. The Shopify Connector affects only the environment, or to be more precise, the company where it's enabled. You can connect to the same Shopify online store from multiple environments or companies. You can disable and re-enable the connector.

It's easy to re-run synchronization tests. The connector allows you to delete imported data, such as products, customers, and orders, and then import them again. Just [reset sync](troubleshoot.md#reset-sync).

### Shopify sandbox and Business Central sandbox

This is probably the safest way to test integration. Instead of using a Shopify Sandbox, you can also use a trial subscription or Development Store. In [!INCLUDE[prod_short](../includes/prod_short.md)], you can also use a test company in a production environment.

To learn more about [!INCLUDE[prod_short](../includes/prod_short.md)] sandboxes, go to [Create a new environment](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-environments#create-a-new-environment).

### Shopify sandbox and Business Central production

This is *not* a recommended configuration for testing because the Shopify connector can create or modify items and customers. It can also create sales documents such as orders and invoices. These documents can be difficult to undo.
 
If you must use this configuration, we recommend that you review and probably disable the following settings:

* **Auto Create Unknown Item** to not create items
* **Shopify can update items** to not update mapped items
* **Auto Create Unknown Customer** to not create customers and contacts
* **Shopify can update customers** to not update existing customers
* **Auto Create Sales Order** to not create sales orders and sales invoices

For more information, see [Restoring an Environment](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-backup-restore).

### Shopify production and Business Central sandbox

It might be a good idea to backup your data. For example, export your products and customers. For more information, see [Using CSV files to back up store information](https://help.shopify.com/en/manual/shopify-admin/duplicate-store#using-csv-files-to-back-up-store-information).

Turn off the **Allow Data Sync to Shopify** toggle so that [!INCLUDE[prod_short](../includes/prod_short.md)] doesn't write to Shopify. In this case, you'll be able to import products, images, customers, and orders from Shopify. But you won't be able to send item, prices, inventory levels, customers, fulfillment information to Shopify.

If you keep the **Allow Data Sync to Shopify** toggle enabled, then additional protective measures are:

*	Select **Draft** in the **Status for Create Product** field to ensure that exported products aren't available to buyers. You can verify how products look in the online store, synchronize prices, options, and stock levels. Just make sure to use filters on the **Add Item to Shopify** page to limit the number of exported items.
* Turn off the **Export Customer to Shopify** toggle so that you don't send customers to Shopify.

## See also

[Walkthrough: Setting Up and Using Shopify Connector](walkthrough-setting-up-and-using-shopify.md)  

