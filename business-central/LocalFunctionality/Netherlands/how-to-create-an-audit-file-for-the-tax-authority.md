---
    title: How to Create an Audit File for the Tax Authority
    description: During an examination of the books for a fiscal year, a tax inspector can ask for data about the basis transactions from the general ledger for that fiscal year. Basis transactions usually are processed via journal entries.
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
# Create an Audit File for the Tax Authority
During an examination of the books for a fiscal year, a tax inspector can ask for data about the basis transactions from the general ledger for that fiscal year. Basis transactions usually are processed via journal entries. That is the reason why the journal entries are the basis for the audit file.  

 The tax authority stimulates companies to use the audit file but it is not prescribed.  

 The audit file can also be used to exchange data between companies. You can select every period you want, but the start and end date of the entered period must be in the same fiscal year.  

## To make an Audit file  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Tax Authority - Audit File**, and then choose the related link.  
2.  On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Start Date**|Specify the start date of the period on which the data must be based.|  
    |**End Date**|Specify the end date of the period on which the data must be based.|  
    |**Exclude Begin Balance**|Specifies if the audit file must contain the begin balance of general ledger accounts.<br /><br /> The field is editable if the start date of the period is equal to the start date of a fiscal year.|  

3.  Choose the **OK** button to create the audit file. If you do not want to create the audit file, choose the **Cancel** button to close the page.  

When you run the report, you must specify the name and location of the exported file. The default file name is **audit.xaf**, but you can change that. The file extension must be .xaf.  

## See Also  
 [Submitting Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md)
