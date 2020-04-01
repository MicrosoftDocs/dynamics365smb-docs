---
    title: How to Enter CCC Codes
    description: Código Cuenta Cliente (CCC) is a unique bank account identification code. The following component fields make up the 20-digit (Spain) or 21-digit (Portugal) bank CCC code structure.

    services: project-madeira 
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Enter CCC Codes
Código Cuenta Cliente (CCC) is a unique bank account identification code. The following component fields make up the 20-digit (Spain) or 21-digit (Portugal) bank CCC code structure.  

If you change the CCC code structure, the **CCC No.** field updates automatically. Similarly, if you change the **CCC No.** field, the CCC code structure updates automatically.  

## To enter CCC codes  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Company Information**, and then choose the related link.  
2.  On the **Payments** FastTab, fill in the fields as described in the following table  

    |Field|Description|  
    |---------------------------------|--------------|---------------------------------------|  
    |**CCC Bank No.**|1-4|Identifies the bank where the account has been opened.|  
    |**CCC Bank Branch No.**|5-8|Identifies the branch code. If the bank does not use this reference, these can be zeros.|  
    |**CCC Control Digits**|9-10|Identifies the control digits.|  
    |**CCC Bank Account No.**|11-20 (Spain)<br /><br /> 11-21 (Portugal)|Identifies the account number, which may be adjusted with preceding zeros.|  

## See Also  
[Spain Local Functionality](spain-local-functionality.md)
