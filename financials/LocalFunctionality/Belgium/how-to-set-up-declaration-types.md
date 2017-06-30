---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# How to: Set Up Declaration Types
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], there are two types of declaration:  
  
-   Simplified declaration  
  
-   Extended declaration  
  
 The type of declaration depends on the amount of shipped or received goods. To determine the type of declaration that you should use, see the [National Bank of Belgium](http://go.microsoft.com/fwlink/?LinkId=163064) web site.  
  
 When using the extended declaration, you will also need to set up an Incoterm in Intrastat Declaration for each shipping method. For more information, see [Incoterm in Intrastat Decl. Field](ms-its:be_lf_a.chm::/T_10_11300.htm).  
  
### To set up declaration types  
  
1.  In the **Search** box, enter **General Ledger Setup**, and then choose the related link.  
  
2.  On the **General** FastTab, select the **Simplified Intrastat Decl.** check box to set up a simplified declaration type. Clear this field to use extended declaration.  
  
3.  Choose the **OK** button.  
  
## See Also  
 [Belgian Intrastat Reporting](../belgian-intrastat-reporting.md)   
 [How to: Set Up Belgian Tariff Numbers](../how-to-set-up-belgian-tariff-numbers.md)   
 [How to: Set Up Intrastat Establishment Numbers](../how-to-set-up-intrastat-establishment-numbers.md)   
 [How to: Export Intrastat Third-Party Declararations](../how-to-export-intrastat-third-party-declararations.md)   
 [How to: Print the Intrastat Form Report](../how-to-print-the-intrastat-form-report.md)