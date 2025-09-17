---
title: Using the AMC banking 365 fundamentals extension
description: Learn how to easily exchange data with your banks by transforming data into the format that they require.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: bank, format, data
ms.search.form: 20100, 20101, 20102, 20105, 20106, 20107, 20109, 
ms.date: 07/18/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Use the AMC banking 365 fundamentals extension

The AMC Banking 365 Fundamentals extension makes it easier, and more accurate, to send data to your banks. The extension connects [!INCLUDE[prod_short](includes/prod_short.md)] with the AMC Banking 365 Fundamentals for Microsoft Dynamics 365 Business Central service, which can convert bank data from [!INCLUDE[prod_short](includes/prod_short.md)] into formats that are required by over 600 banks around the world. For example, this makes it easier to transfer payments and credits to vendors by entering the payments in [!INCLUDE[prod_short](includes/prod_short.md)], and then uploading them to your bank. The formats can also smooth out bank reconciliation processes. For more information, see [AMC Banking for Microsoft Dynamics 365 Business Central](https://www.amcbanking.com/bc-fundamentals/).

> [!NOTE]
> AMC Banking has built additional extensions that work with [!INCLUDE[prod_short](includes/prod_short.md)]. This topic describes only the Fundamental extension.

> [!NOTE]
> In the generic version of [!INCLUDE[prod_short](includes/prod_short.md)], a global provider of services to convert bank data to any file format that your bank requires is set up and connected. In North American versions, the same service can be used to send payment files as electronic funds transfer (EFT), for example the commonly used Automated Clearing House (ACH) network, however with a slightly different process.

## Use our demonstration account

[!INCLUDE[prod_short](includes/prod_short.md)] comes with a demonstration account that lets you try out the AMC Banking 365 Fundamentals extension. We provide default settings for connecting to AMC Banking, specifying the bank accounts to get data from in [!INCLUDE[prod_short](includes/prod_short.md)], plus a few data exchange definitions. You can view the connection settings on the **AMC Banking Setup** page. For bank accounts, the extension applies values in the **Bank Name**, **Credit Transfer Msg. Nos.**, **Bank Statement Import Format**, and **Payment Export Format** fields on bank account cards.

We provide the settings, but to try out the extension you must run the assisted setup guide to apply them. To run the guide, on the **AMC Banking Setup** page, choose the **Assisted Setup** action.

> [!NOTE]
> There are some limitations on the demo account. For example, when you convert payments, the amount in the converted file will not match the actual amount. Instead, the amount will always be five units of the currency that you use for payments.  

## Setting up the extension

Getting started with the extension involves just a few easy steps, and an assisted setup guide will make the connection and turn on the extension. The guide helps you things like install the data exchange definitions for bank statement export/import setups and initiate the number series used for credit transfer messages.  

### To set up the required permission sets

Before people can use this extension, your administrator must copy the following permission sets, edit them, and then assign the new permission sets to users instead of original:

* **D365 Basic**
* **D365 Team Member**
* **D365 Read**
* **IntelligentCloudBC**

For more information, see [To copy a permission set](ui-define-granular-permissions.md#copy-a-permission-set).

For each new permission set, grant only the **Read** permission for the **AMC Banking Setup table (20101)**. For more information, see [To create or modify permissions manually](ui-define-granular-permissions.md#create-a-permission-set).

### To connect the extension to AMC Banking

1. Get a module and a service plan for AMC Banking. To do that, visit the [AMC License](https://license.amcbanking.com/register) page.
2. In [!INCLUDE[prod_short](includes/prod_short.md)], [!INCLUDE[open-search](includes/open-search-lowercase.md)], enter **AMC Banking Setup**, and then choose the related link.  
3. On the **AMC Banking Setup** page, choose the **Assisted Setup** action.
4. Complete the steps in the assisted setup guide.

### To connect bank accounts to the extension

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Bank Accounts**, and then choose the related link.
2. Open the card for the bank account that you want to connect to the service.
3. In the **Name** field, choose the format that your bank requires.  

   The formats are filtered to show only those that are relevant for the country/region that is specified for the bank account.
4. In the **Credit Transfer Msg. Nos.** field, choose the number series to use for messages that accompany payments.
5. In the **Bank Statement Import Format** and **Payment Export Format** fields, choose the data exchange definitions that your bank requires.

## Use the extension

Using this extension is just a matter of exporting data on the **Payment Journals** page, and then uploading it to your bank's web service. For more information, see [Making Payments with Bank Data Conversion or SEPA Credit Transfer](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md).

> [!NOTE]
> You must fill in the **SWIFT Code** and **IBAN** fields for each bank account.

### To export data and submit it to your bank

> [!CAUTION]  
> When you export data by using the AMC Banking 365 Fundamentals extension, some of your business data will be exposed to the provider of the service. The service provider, AMC Consult A/S, is responsible for the privacy of this data. For more information, see [AMC Privacy Policy](https://go.microsoft.com/fwlink/?LinkId=510158).

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Payment Journals**, and then choose the related link.
2. Create the journal lines that you want to export.  

   > [!NOTE]
   > For each line, remember to choose **Electronic Payment** in the **Bank Payment Type** field.
3. Choose the **Export** action.

### To import and apply the converted file

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Payment Reconciliation Journals**, and then choose the related link.
2. Choose the **Import Bank Transaction** action, and then choose the converted file.  

   [!INCLUDE[prod_short](includes/prod_short.md)] will create a new payment reconciliation journal that contains the data in the file. For more information, see [Applying Payments Automatically and Reconciling Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md).

## Related information

[Customizing [!INCLUDE[prod_short](includes/prod_short.md)] Using Extensions](ui-extensions.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
