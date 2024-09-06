---
title: Banking formats
description: Frequently Asked Questions about Supported Banking and Payment Formats.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: bank, format, payment, feed, stream, data exchange, AMC, link
ms.search.form: 370, 1200, 20353
ms.date: 09/06/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: 
---

# Frequently Asked Questions about Supported Banking and Payment Formats 

## Introduction  

Banking and payment formats are often subject to changes, different from country to country, and different from bank to bank. For Business Central to handle the more than thousands bank formats globally, Microsoft ensures partners can easily deliver the needed integrations and updates.  

In some countries Microsoft delivered built-in imports and exports. These imports and exports will not be adapted to newer versions of the formats they represent, should any such be published or required by banks. Nor will any new banking and payment related formats be developed. This will impact the country localizations of Business Central released by Microsoft. See the [list of localizations here](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations.md). 

## Questions  

### Will these import and export options and formats disappear from Business Central?  

There are no plans to deprecate and remove the current formats and import/export options. You can still use them and partners and customers can still build integrations for them.  

### What banking and payment apps are available in my country?   

You can find ISV banking solutions that support banking and/or payment related functionality in some form in product in the **Banking Apps** page or using the [AppSource](https://appsource.microsoft.com/)

Make sure to investigate which features the individual app supports to evaluate if they meet the requirements of your business and your bank. 

> [!NOTE]
> There is one current exception. The Envestnet Yodlee Bank Feeds and AMC Banking 365 Fundamentals apps are not impacted and still supported. 

### Does this mean there is no plan to support banking connectivity in Business Central in the future?  

Micorsoft ensures businesses can connected to their banks and perform fundamental tasks in a modern and secure fashion, and support partners to build apps for this purpose. 


## See Also

[Reconciling Bank Accounts](bank-manage-bank-accounts.md)  
[Make payments with the AMC banking 365 fundamentals extension or SEPA credit transfer](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md)
[Collect payments with SEPA Direct Debit](finance-collect-payments-with-sepa-direct-debit.md)
[Field Mapping When Importing SEPA CAMT Files](across-field-mapping-when-importing-sepa-camt-files.md)
[Country/regional availability and supported languages](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
