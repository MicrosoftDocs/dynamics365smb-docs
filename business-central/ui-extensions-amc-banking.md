---
title: Using the AMC Banking 365 Fundamentals Extension | Microsoft Docs
description: Easily exchange data with your banks by transforming data into the format that they require.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: bank, format, data
ms.date: 04/01/2020
ms.author: bholtorf

---

# Using the AMC Banking 365 Fundamentals Extension
The AMC Banking 365 Fundamentals extension makes it easier, and more accurate, to send data to your banks. The extension connects [!INCLUDE[d365fin](includes/d365fin_md.md)] with the AMC Banking 365 Fundamentals for Microsoft Dynamics 365 Business Central service, which can convert bank data from [!INCLUDE[d365fin](includes/d365fin_md.md)] into formats that are required by over 600 banks around the world. For example, this makes it easier to transfer payments and credits to vendors by entering the payments in [!INCLUDE[d365fin](includes/d365fin_md.md)], and then uploading them to your bank. The formats can also smooth out bank reconciliation processes. For more information, see [AMC Banking for Microsoft Dynamics 365 Business Central](https://amcbanking.com/landing365bc/help).

> [!Note]
> AMC Banking has built additional extensions that work with [!INCLUDE[d365fin](includes/d365fin_md.md)]. This topic describes only the Fundamental extension.

## Using Our Demonstration Account
[!INCLUDE[d365fin](includes/d365fin_md.md)] comes with a demonstration account that lets you try out the AMC Banking 365 Fundamentals extension. We provide default settings for connecting to AMC Banking, specifying the bank accounts to get data from in [!INCLUDE[d365fin](includes/d365fin_md.md)], plus a few data exchange definitions. You can view the connection settings on the **AMC Banking Setup** page. For bank accounts, the extension applies values in the **Bank Name**, **Credit Transfer Msg. Nos.**, **Bank Statement Import Format**, and **Payment Export Format** fields on bank account cards.

We provide the settings, but to try out the extension you must run the assisted setup guide to apply them. To run the guide, on the **AMC Banking Setup** page, choose the **Assisted Setup** action.

> [!Note]
> There are some limitations on the demo account. For example, when you convert payments, the amount in the converted file will not match the actual amount. Instead, the amount will always be five units of the currency that you use for payments.  

## Setting Up the Extension
Getting started with the extension involves just a few easy steps, and an assisted setup guide will make the connection and turn on the extension. The guide will do things like install the data exchange definitions for bank statement export/import setups and initiate the number series used for credit transfer messages.  

### To set up the required permission sets
Before people can use this extension, your administrator must copy the following permission sets, edit them, and then assign the new permission sets to users instead of original:

* **D365 Basic**
* **D365 Team Member**
* **D365 Read**
* **IntelligentCloudBC**

For more information, see [To copy a permission set](ui-define-granular-permissions.md#to-copy-a-permission-set).

For each new permission set, grant only the **Read** permission for the **AMC Banking Setup table (20101)**. For more information, see [To create or modify permissions manually](ui-define-granular-permissions.md#to-create-or-modify-permissions-manually).

### To connect the extension to AMC Banking
1. Get a module and a service plan for AMC Banking. To do that, visit the [AMC License](https://license.amcbanking.com/register) page.
2. In [!INCLUDE[d365fin](includes/d365fin_md.md)], choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **AMC Banking Setup**, and then choose the related link.  
3. On the **AMC Banking Setup** page, choose the **Assisted Setup** action.
4. Complete the steps in the assisted setup guide.

### To connect bank accounts to the extension
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, and then choose the related link.
2. Open the card for the bank account that you want to connect to the service.
3. In the **Bank Name** field, choose the format that your bank requires.  

   The formats are filtered to show only those that are relevant for the country/region that is specified for the bank account.
4. In the **Credit Transfer Msg. Nos.** field, choose the number series to use for messages that accompany payments.
5. In the **Bank Statement Import Format** and **Payment Export Format** fields, choose the data exchange definitions that your bank requires.

## Using the Extension
Using this extension is just a matter of exporting data on the **Payment Journals** page, and then uploading it to your bank's web service. For more information, see [Making Payments with Bank Data Conversion or SEPA Credit Transfer](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md).

> [!Note]
> You must fill in the **SWIFT Code** and **IBAN** fields for each bank account.

### To export data and submit it to your bank
> [!CAUTION]  
>  When you export data by using the AMC Banking 365 Fundamentals extension, some of your business data will be exposed to the provider of the service. The service provider, AMC Consult A/S, is responsible for the privacy of this data. For more information, see [AMC Privacy Policy](https://go.microsoft.com/fwlink/?LinkId=510158).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Journals**, and then choose the related link.
2. Create the journal lines that you want to export.  

   > [!Note]
   > For each line, remember to choose **Electronic Payment** in the **Bank Payment Type** field.
3. Choose the **Export** action.

### To import and apply the converted file
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Reconciliation Journal**, and then choose the related link.
2. Choose the **Import Bank Transaction** action, and then choose the converted file.  

   [!INCLUDE[d365fin](includes/d365fin_md.md)] will create a new payment reconciliation journal that contains the data in the file. For more information, see [Applying Payments Automatically and Reconciling Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md).

## See Also
[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md)  
[Getting Started](product-get-started.md)
