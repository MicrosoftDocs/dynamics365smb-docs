---
title: Set Up Bank Data Conversion| Microsoft Docs
description: You can set up bank accounts to keep track of transactions and import or export bank feeds, such as Yodlee.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: Yodlee, feed, stream, data exchange, AMC, bank file import, bank file export, re-export, bank transfer, AMC, AMC Banking 365 Fundamentals extension, funds transfer
ms.date: 04/01/2020
ms.author: sgroespe

---
# Set Up the AMC Banking 365 Fundamentals extension
A global provider of services to convert payment information to any data format that your bank requires is connected and ready to be enabled in [!INCLUDE[d365fin](includes/d365fin_md.md)]. This is referred to in [!INCLUDE[d365fin](includes/d365fin_md.md)] as the AMC Banking 365 Fundamentals extension.

You can export payment lines from the **Payment Journal** page to a file or a data stream that you then upload to your bank for automatic processing so that you do not have to make electronic payments individually. For more information, see [Export Payments to a Bank File](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#exporting-payments-to-a-bank-file).

You can import bank statement files into the **Payment Reconciliation Journal** page by using the AMC Banking 365 Fundamentals extension to convert a file that you receive from your bank to a data stream that [!INCLUDE[d365fin](includes/d365fin_md.md)] can import. For more information, see [Applying Payments Automatically and Reconciling Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md).

As an alternative to importing bank statements with the AMC Banking 365 Fundamentals extension, you can use the Envestnet Yodlee Bank Feeds service. For more information, see [Set Up the Envestnet Yodlee Bank Feeds Service](bank-how-setup-bank-statement-service.md).

To import or export bank files, you must set up your own bank account and your vendors' bank accounts. For more information, see [Set Up Bank Accounts](bank-how-setup-bank-accounts.md).

> [!NOTE]  
> The AMC Banking 365 Fundamentals extension may impose a limit on the number of lines that can be exported in one file. You will receive an error message if the limit is exceeded. It is recommended that bank statement files do not exceed 1000 lines as the processing time in the AMC Banking 365 Fundamentals extension may otherwise increase significantly.

## To sign your company up for the AMC Banking 365 Fundamentals extension
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Data Conv. Service Setup**, and then choose the related link.  
2. The **Bank Data Conv. Service Setup** page opens with three fields prefilled with relevant URLs of the provider of AMC Banking 365 Fundamentals extension.

    > [!NOTE]  
    >   In the CRONUS International Ltd. demonstration database, the User Name and Password fields are prefilled with demonstration logon information, which you will replace with your company’s actual information as you sign up for the AMC Banking 365 Fundamentals extension.
3. In the **Sign-up URL** field, choose the browser button to open the service provider’s sign-up page.  
4. On the sign-up page of the bank data service provider, enter the user name and password for your company’s subscription to the service, and then complete the sign-up process as instructed by the service provider.

    Your company is now signed up for the AMC Banking 365 Fundamentals extension. Proceed to enter the user name and password that you specified for the service in the related setup fields in [!INCLUDE[d365fin](includes/d365fin_md.md)].

5. On the **Bank Data Conv. Service Setup** page, in the User **Name** field, enter the same value that you entered as logon name on the service provider’s page in step 4.
6. In the **Password** field, enter the same value that you entered in the **Password** field on the service provider’s page in step 4.

> [!NOTE]  
> You login data is automatically encrypted.

## To view or update the list of currently supported bank data formats
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Data Conv. Service Setup** , and then choose the related link.
2. On the **Bank Data Conv. Service Setup** page, choose the **Bank Name - Data Conversion List** action to open the list of bank names representing bank data formats that are supported by the conversion service.
3. On the **Bank Name - Data Conversion List** page, choose the **Update Bank Name List** action.

The list of bank data formats that are supported by the AMC Banking 365 Fundamentals extension is now updated. This is the list of bank names, filtered by the country/region, that you can select from in the **Bank Name - Data Conversion** field on the **Bank Account Card** page.

> [!NOTE]  
>   The update of supported bank data formats also occurs when you select or enter a value in the **Bank Name - Data Conversion** field on the bank account.

You have now signed up for the AMC Banking 365 Fundamentals extension. Proceed to reflect the sign-up information on every bank account that will use the service.

## See Also
[Setting Up Banking](bank-setup-banking.md)  
[Reconciling Bank Accounts](bank-manage-bank-accounts.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
