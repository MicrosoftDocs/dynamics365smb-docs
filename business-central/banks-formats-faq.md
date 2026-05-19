---
title: How to use banking and payment formats in Business Central
description: Learn how to find and use banking and payment formats that suit your needs and comply with your country and bank requirements in Business Central.
author: altotovi
ms.topic: how-to
ms.devlang: al
ms.search.keywords: bank, format, payment, feed, stream, data exchange, AMC, link
ms.search.form: 370, 1200, 20353
ms.date: 09/09/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: solsen
---

# How to use banking and payment formats in Business Central

Banking and payment formats can change over time and vary by country/region and bank. To help you connect to your bank and handle transactions in [!INCLUDE[prod_short](includes/prod_short.md)], Microsoft works with partners who provide apps that support different formats and integrations. 

In some countries/regions, Microsoft also provides built-in imports and export options. However, these options aren't adapted to newer versions of the formats, unless the bank requires it. Also, there will be no development of new banking and payment-related formats. This affects the country/region localizations of [!INCLUDE[prod_short](includes/prod_short.md)] that Microsoft releases. For a list of local versions, see [list of localizations here](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations). 

## Frequently Asked Questions about supported banking and payment formats

### Will [!INCLUDE[prod_short](includes/prod_short.md)] discontinue these import/export options and the current formats?  

No, there are no plans to remove the current formats and import/export options. You can still use them, and partners, and customers can still build integrations for them.  

### How can I find banking and payment apps for my country/region?

You can find ISV banking solutions that support banking and/or payment-related functionality on the **Banking Apps** page or on [Marketplace](https://marketplace.microsoft.com/)

Make sure to check the features of each app to see if they match your business needs and your bank requirements. 

> [!NOTE]
> There's one exception. The Envestnet Yodlee Bank Feeds and AMC Banking 365 Fundamentals apps aren't impacted and still supported. 

### Is there no plan to support banking connectivity in [!INCLUDE[prod_short](includes/prod_short.md)] in the future?  

Yes, Microsoft wants to enable you to connect to your bank and perform fundamental tasks in a modern and secure manner. This is why Microsoft supports partners who create apps for this purpose. 

## Related information

- [Reconciling Bank Accounts](bank-manage-bank-accounts.md)    
- [Make payments with the AMC banking 365 fundamentals extension or SEPA credit transfer](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md)  
- [Collect payments with SEPA Direct Debit](finance-collect-payments-with-sepa-direct-debit.md)  
- [Field Mapping When Importing SEPA CAMT Files](across-field-mapping-when-importing-sepa-camt-files.md)  
- [Country/regional availability and supported languages](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
