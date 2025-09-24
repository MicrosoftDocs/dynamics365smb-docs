---
title: How to print VAT reconciliation reports [DK]
description: In Business Central, the VAT Reconciliation report displays a list of general ledger accounts with their corresponding base amounts and VAT amounts.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: VAT, VAT reconciliation report, Denmark, reconciliation
ms.date: 03/03/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Print VAT Reconciliation reports

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can use the **VAT Reconciliation** report to view a list of general ledger accounts with their base amounts and VAT amounts. VAT type groups these amounts to help with VAT settlement reconciliation.  

### Print a VAT Reconciliation report

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Reconciliation**, and then choose the related link.  
1. On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Show Details**|Select to print all transaction amounts in the report.<br><br/> If you don't select this field, a single cumulative line is printed for each general ledger account.|  
    |**Show Transactions without VAT**|Select to print a line for each general ledger account that transactions are posted to. You can use this option for both single accounts and multiple accounts.<br><br/> The default is **No**. The report includes only those transactions that include VAT entries. If you select this field, the report includes all transactions.|  

1. On the **G/L Entry** FastTab, select the appropriate filters.  
1. Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  

## Related information

[Denmark Local Functionality](denmark-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
