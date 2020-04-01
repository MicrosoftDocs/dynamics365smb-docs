---
title: How to Print VAT Reconciliation Reports | Microsoft Docs
description: In Business Central, you can use the VAT Reconciliation report to view a list of general ledger accounts with their base amounts and VAT amounts. These amounts are grouped by VAT type to help with VAT settlement reconciliation.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 04/01/2020
ms.author: sgroespe

---
# Print VAT Reconciliation Reports
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can use the **VAT Reconciliation** report to view a list of general ledger accounts with their base amounts and VAT amounts. These amounts are grouped by VAT type to help with VAT settlement reconciliation.  

### To print a VAT reconciliation report  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Reconciliation**, and then choose the related link.  
2.  On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Show Details**|Select to print all transaction amounts in the report.<br /><br /> If you do not select this field, a single cumulative line is printed for each general ledger account.|  
    |**Show Transactions without VAT**|Select to print a line for each general ledger account that transactions are posted to. You can use this option for both single accounts and multiple accounts.<br /><br /> The default is **No**. The report includes only those transactions that include VAT entries. If you select this field, the report includes all transactions.|  

3.  On the **G/L Entry** FastTab, select the appropriate filters.  
4.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  

## See Also  
 [Denmark Local Functionality](denmark-local-functionality.md)  
