---
title: How to Print Swiss VAT Statements (older version)
description: Learn how to print the Swiss VAT statement to use it for quarterly tax reporting.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: Swiss VAT statement, VAT statement, Swiss version
ms.date: 04/29/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Print Swiss VAT Statements (older version)

> [!NOTE]  
> This article is retained for backward compatibility with the **Swiss VAT Statement** report. For information about using the newer Swiss VAT Statement, see Swiss VAT Statement.  

The **Swiss VAT Statement** is the standard calculation report for realizing VAT. You can print this report, and use it for quarterly tax reporting. The **Swiss VAT Statement** includes the following:  

- A VAT entry.  
- VAT adjusting entries.  
- An accounting sheet.  

## Steps to print the Swiss VAT statement  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Swiss VAT Statement**, and then choose the related link.  

    > [!NOTE]  
    > You'll receive a message stating that the **Swiss VAT Statement** will open in the local language.  

1. On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Closed with Journal no.**|Select the general ledger journals that contain the posting source of the VAT adjusting entries. This field evaluates accounting periods that have already been settled.|  
    |**Open until date**|Select the last date for settling open or unsettled VAT entries.|  
    |**Show Postings**|Specifies if all of the VAT entries for each group will be printed.|  
    |**Show Chargeback**|Specifies if VAT entries and general ledger entries with closed summaries or reposted tax will be printed.|  
    |**Normal rate VAT %**|Select the current typical VAT rates used to assign the correct rates to the business and product groups defined in the VAT settings.|  
    |**Reduced rate VAT %**|Select the current reduced tax rates used to assign the correct rates to the business and product groups defined in the VAT settings.|  
    |**Special rate VAT %**|Select the current special tax rates used to assign the correct rates to the business and product groups defined in the VAT settings.|  
    |**Investment/Operating Purchase VAT G/L Account**|Select the VAT general ledger account.|  
    |**Own Consumption Bus. Group**|Select the business and product group for own consumptions.|  
    |**Service Foreign Bus. Group**|Select the foreign service business and product group.|  
    |**Export Bus. Group**|Select the business and product group for exports.|  

1. Choose the **Print** button to print the VAT statement or choose the **Preview** button to view it on the screen.  

## Related information

- [Swiss Value Added Tax](swiss-value-added-tax.md)
- [VAT Rates for Switzerland](vat-rates-for-switzerland.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
