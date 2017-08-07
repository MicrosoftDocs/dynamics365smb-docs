---
    title: How to: Create and Print General Ledger Account Turnover | Microsoft Docs
    description: [!INCLUDE[d365fin](../../includes/d365fin_md.md)] enables you to create general ledger account turnover information in the **G/L Account Turnover** window.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# How to: Create and Print General Ledger Account Turnover
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] enables you to create general ledger account turnover information in the **G/L Account Turnover** window.  
  
 You can then verify this information in the following reports:  
  
-   **G/L Account Turnover**  
  
-   **G/L Account Card**  
  
-   **G/L Account Entries Analysis**  
  
### To create a general ledger account turnover entry  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **G/L Account Turnover**, and then choose the related link.  
  
2.  On the **General** FastTab, enter the following information.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Date Filter**|Enter the date filter for which you want to view account information.|  
    |**Business Unit Filter**|Select the business unit filter for which you want to view account information.|  
    |**Department Filter**|Select the department filter for which you want to view account information.|  
    |**Incexp Filter**|Select the income and expenses filter for which you want to view account information.|  
    |**Switch Debit/Credit**|Specify if you want to show the debit and credit balance for the account.|  
  
     On the **Source** FastTab, enter the following information.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Source Type Filter**|Specify the source type filter for which you want to view account information.|  
    |**Source No. Filter**|Select the source number filter for which you want to view account information.|  
  
### To print the general ledger account turnover report  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **G/L Account Turnover**, and then choose the related link.  
  
2.  On the **Options** FastTab, enter the following information.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Rounding Precision**|Specify the interval that you want to use as the rounding difference for the relevant currency.|  
    |**Replace zero values by blanks**|Select if you want to replace zero values with a blank entry.|  
    |**Skip accounts without net changes**|Select to exclude the accounts that do not have net changes.|  
    |**Skip accounts without zero ending balance**|Select to exclude the accounts that do have zero ending balances.|  
    |**Skip zero lines**|Select to exclude lines with zero values.|  
  
### To print the general ledger account card report  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **G/L Account Card**, and then choose the related link.  
  
2.  On the **Options** FastTab, enter the following information.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Show Correspondence**|Select if you want to show general ledger correspondence information on the report.|  
    |**New Page for GL Acc**|Select if you want to print a new page for each general ledger account.|  
    |**Including Closing Period Entries**|Select if you want to include the closing period entries on the report.|  
  
### To print the general ledger account entries analysis report  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **G/L Account Entries Analysis**, and then choose the related link.  
  
2.  On the **Options** FastTab, enter the following information.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Without Zero Net Changes**|Select to include the entries that do not have zero net changes.|  
    |**Without Zero Lines**|Select to include the entries that do not have zero lines.|  
    |**Debit Credit Separately**|Select if you want to separate the debit and credit entries on the report.|  
    |**New Page for GL Acc**|Select if you want to print a new page for each general ledger account.|  
  
## See Also  
 G/L Account   
 G-L Account Turnover   
 G-L Account Card   
 G-L Account Entries Analysis