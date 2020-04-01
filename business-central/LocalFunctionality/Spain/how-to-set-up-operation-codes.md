---
    title: How to Set Up Operation Codes
    description: You can add as many operation codes as you want to the table. However, the operation codes C, D, and I already exist in Business Central.

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
# Set Up Operation Codes
You can add as many operation codes as you want to the table. However, the operation codes C, D, and I already exist in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. For example, Credit Memos always have the operation code D. You cannot set up these values in the table because they are system-created codes. If you try to add them, [!INCLUDE[d365fin](../../includes/d365fin_md.md)] will return an error.  

## To set up operation codes  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Operation Codes**, and then choose the related link.  
2.  On the **Operation Codes** page, fill in the fields as described in the following table  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|Enter an operation code. You can only enter one letter or number.<br /><br /> Valid codes are numbers 1 – 8, and letters A – Z.<br /><br /> To submit a report under the CAC regimen, you must make certain that the code Z, which is required for these types of transactions, is in the list of operation codes.|  
    |**Description**|Enter a description for the operation code. You can enter a maximum of 30 letters and numbers.|  

## To link operation codes to general product posting groups  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Posting Groups**, and then choose the related link.  
2.  Choose the **General Product Posting Groups** action.  
3.  On the **General Product Posting Groups** page, link each operation code to a general product posting group.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |Code|Enter a code to create a new general product posting group.|  
    |Description|Enter a description for the general product posting group|  
    |Def. VAT Prod. Posting Group|Select a VAT percentage to link it to the general product posting group.|  
    |Operation Code|Select an appropriate operation code to link it to the general product posting group. You can assigne the same operation code to different posting groups. **Note:**  It is important to link the operation code to the correct VAT product posting group. The Make 340 Declaration report uses the setup to create trade declarations.|  

When you add an operation code to the general product posting group, that association is in turn applied to the items that have that general product posting group.  

## See Also  
 [Create Report 340](how-to-create-report-340.md)
