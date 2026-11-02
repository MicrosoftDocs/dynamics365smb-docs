---
title: Banking Setup in Business Central
description: Set up bank accounts in Business Central, choose statement import and payment export formats, and find banking apps that support your bank.
author: brentholtorf
ms.topic: overview
ms.devlang: al
ms.search.keywords: Yodlee, feed, stream, data exchange, AMC, link
ms.search.form: 370, 371, 1200, 20353
ms.date: 10/14/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Set up banking and bank connections

Set up bank accounts in [!INCLUDE[prod_short](includes/prod_short.md)] to track banking transactions, reconcile bank statements, and prepare payments. You can import and export bank files in supported formats, or use a banking app to connect to your bank. An external service isn't required for every import or export.

## Set up bank accounts

Create a bank account card for each bank account that your company uses. On the **Bank Account Card** page:

* Set **Currency Code** for a foreign-currency account, or leave it blank for your company's local currency.
* Set **Bank Acc. Posting Group** to link bank transactions to the appropriate general ledger account.
* Enter the account details that your bank and chosen payment format require, such as **Bank Account No.**, **IBAN**, and **SWIFT Code**.

After you create the account, you can use it for payment transactions, reconciliation, and check printing. Learn more about account setup in [Set up bank accounts](bank-how-setup-bank-accounts.md).

## Choose a connection or file format

Check which formats and connection methods your bank supports before you choose an app or configure a file format. Availability depends on your country or region, deployment, and installed apps.

| To | See |
| --- | --- |
| Import bank statement files for reconciliation, including files in comma-separated values (CSV) format. | [Reconcile bank accounts](bank-how-reconcile-bank-accounts-separately.md). |
| Configure the mapping between a bank file and fields in [!INCLUDE[prod_short](includes/prod_short.md)]. | [Set up data exchange definitions](across-how-to-set-up-data-exchange-definitions.md). |
| Find an app that supports your bank's formats or connection requirements. | [Customize Business Central using extensions](ui-extensions.md). |
| Link a supported online bank account to import statements through Envestnet Yodlee Bank Feeds. | [Set up the Envestnet Yodlee bank feeds service](bank-how-setup-bank-statement-service.md). |
| Set up payment-file exports, such as Single Euro Payments Area (SEPA) credit transfers. | [Set up SEPA credit transfer](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#setting-up-sepa-credit-transfer). |
| Configure bank-file conversion with the Microsoft-published AMC Banking 365 Fundamentals extension in versions where it's available. | [Use the AMC Banking 365 Fundamentals extension](ui-extensions-amc-banking.md). |
| Set up and print checks. | [Work with checks](payables-how-work-checks.md). |

### Bank statement files

On the **Bank Account Card** page, use **Bank Statement Import Format** on the **Transfer** FastTab to choose the import setup for the account. For a CSV file, use the **Set up a bank statement file import format** assisted setup guide to define the file layout and assign it to a bank account.

Use **Bank Export/Import Setup** and data exchange definitions when you need to configure another supported bank-file format. Learn more about file-format setup in [Set up data exchange](across-set-up-data-exchange.md).

### Banking apps and bank feeds

In [!INCLUDE[prod_short](includes/prod_short.md)] online, use the **Banking Apps** page to find apps for your country or region. Where available, the **Connect to Banks** action on the **Bank Account Card** page opens that list. Review the app's supported banks, capabilities, pricing, and setup requirements before installing it.

The Microsoft-provided Envestnet Yodlee Bank Feeds integration is supported in [!INCLUDE[prod_short](includes/prod_short.md)] online for banks in the United States and Canada. Don't assume that every bank shown in a provider's bank-selection window is supported.

> [!IMPORTANT]
> The Microsoft-published AMC Banking 365 Fundamentals app is scheduled to be replaced by an AMC-owned app in 2027 release wave 1, version 30. If you use the Microsoft-published app and want to move to the replacement, coordinate migration with AMC. Learn more about this change in [AMC Fundamentals app removal](/dynamics365/business-central/dev-itpro/upgrade/deprecated-features-w1#amc-fundamentals-app-removal).

### Payment exports

On the **Bank Account Card** page, select **Payment Export Format** on the **Transfer** FastTab. Depending on the format, you also need to set up recipient bank accounts, payment methods, and the payment journal batch. For payment-file exports, the batch must have **Allow Payment Export** turned on.

Exporting a payment file doesn't send it to your bank for processing. Upload and authorize the file as required by your bank, unless your banking app provides a direct submission process.

[!INCLUDE [local-functionality](includes/local-functionality.md)]

## Related information

[Manage bank accounts](bank-manage-bank-accounts.md)  
[Manage receivables](receivables-manage-receivables.md)  
[Manage payables](payables-manage-payables.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
