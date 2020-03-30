---
    title: How to Print Checks for APACS | Microsoft Docs
    description: The Association for Payment Clearing Services (APACS) specification defines a standard layout for fields on checks. The Check report uses this specification.
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
# Print Checks for APACS
The Association for Payment Clearing Services (APACS) specification defines a standard layout for fields on checks. The **Check** report uses this specification.  

## To print checks for APACS  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Journals**, and then choose the related link.  
2.  To preview the check, choose the **Preview Check** action.  
3.  To print the check, choose the **Print Check** action.  

4.  On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Bank Account**|Specifies bank account code.|  
    |**Last Check No.**|Specifies the last check number that was specified on the **Bank Account Card** page.|  
    |**One Check per Vendor per Document No.**|Select to print only one check per vendor for each document number.|  
    |**Reprint Checks**|Select to reprint canceled checks.|  
    |**Test Print**|Select to print checks on blank paper before printing them on check forms.|  
    |**Preprinted Stub**|Select to use check forms with preprinted stubs.|  

5.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  

## See Also  
[United Kingdom Local Functionality](united-kingdom-local-functionality.md)
