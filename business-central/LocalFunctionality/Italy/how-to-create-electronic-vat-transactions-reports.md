---
title: Create Electronic VAT Transactions Report [IT]
description: Create a report of VAT-inclusive transactions exceeding the current threshold by the specified date.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: VAT-inclusive transactions, create VAT transaction reports, VAT report, Italian version
ms.date: 05/20/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Create electronic VAT Transactions reports in the Italian version

You must create a list of transactions that include VAT with amounts over the current threshold on or before the specified occurrence date. You submit this report to the tax authorities.  

## Create a VAT Transactions report  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Report**, and then choose the related link.  
1. Fill in the fields as described in the following table.  

    |Field|Description|  
    |-------------------------------------|---------------------------------------|  
    |**Without Contract**|The VAT entries that resulted in this line aren't associated with a contract.|  
    |**Contract**|The VAT entries that resulted in this line are associated with a contract.|  
    |**Other**|The VAT entries that resulted in this line aren't associated with a special contract, such as ongoing maintenance or other exceptions.|  

    > [!TIP]  
    > In [!INCLUDE[prod_short](../../includes/prod_short.md)], the contract that the tax authorities are looking for can be blanket orders or service contracts. To identify if the VAT report line belongs to a blanket order or service contract, you can drill down to see the underlying VAT entries from the **Amount** field.  

Credit memos are included in the VAT transaction report if the customer or vendor is from a country/region that is outside the EU and not excluded. Learn more in [Italian VAT](italian-vat.md).  

Now that you have created the VAT report, you must submit it to the tax authorities. Learn more in [Export VAT Transactions Reports](how-to-export-vat-transactions-reports.md).  

## Related information

[Italian VAT](italian-vat.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
