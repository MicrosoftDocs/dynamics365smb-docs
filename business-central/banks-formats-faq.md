---
title: Banking formats
description: Frequently Asked Questions about Supported Banking and Payment Formats.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: bank, format, payment, feed, stream, data exchange, AMC, link
ms.search.form: 370, 1200, 20353
ms.date: 09/09/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: 
---

# Frequently Asked Questions about Supported Banking and Payment Formats 

## Introduction  

Banking and payment formats are often subject to changes, vary from country to country, and differ from bank to bank. For [!INCLUDE[prod_short](includes/prod_short.md)] to handle more than thousands of bank formats globally, Microsoft ensures that partners can easily deliver the needed integrations and updates.  

In some countries, Microsoft delivers built-in imports and exports. These imports and exports won't be adapted to newer versions of the formats, unless they're published or required by banks, and there will be no development of new banking and payment-related formats. This will impact the country localizations of [!INCLUDE[prod_short](includes/prod_short.md)] released by Microsoft. See the [list of localizations here](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations). 

## Questions  

### Will [!INCLUDE[prod_short](includes/prod_short.md)] discontinue these import/export options and the current formats?  

There are no plans to deprecate and remove the current formats and import/export options. You can still use them, partners, and customers can still build integrations for them.  

### What banking and payment apps are available in my country?   

You can find ISV banking solutions that support banking and/or payment-related functionality in some form in product on the **Banking Apps** page or using the [AppSource](https://appsource.microsoft.com/)

Make sure to investigate the features that individual app supports to evaluate if they meet the requirements of your business and your bank. 

> [!NOTE]
> There is one current exception. The Envestnet Yodlee Bank Feeds and AMC Banking 365 Fundamentals apps are not impacted and still supported. 

### Is there no plan to support banking connectivity in [!INCLUDE[prod_short](includes/prod_short.md)] in the future?  

Microsoft ensures that businesses can connect to their banks and perform fundamental tasks in a modern and secure manner, and supports partners in building apps for this purpose. 


## See also

[Reconciling Bank Accounts](bank-manage-bank-accounts.md)    
[Make payments with the AMC banking 365 fundamentals extension or SEPA credit transfer](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md)  
[Collect payments with SEPA Direct Debit](finance-collect-payments-with-sepa-direct-debit.md)  
[Field Mapping When Importing SEPA CAMT Files](across-field-mapping-when-importing-sepa-camt-files.md)  
[Country/regional availability and supported languages](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
