---
    title: How to Set Up Declaration Types
    description: In Business Central, there are two types of declaration.

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
# Set Up Declaration Types
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], there are two types of declaration:  

- Simplified declaration  
- Extended declaration  

The type of declaration depends on the amount of shipped or received goods. To determine the type of declaration that you should use, visit the [National Bank of Belgium](https://aka.ms/BelgianNationalBank) website.  

When using the extended declaration, you will also need to set up an Incoterm in Intrastat Declaration for each shipping method. If you do not see the **Incoterm in Intrastat Decl.** field on the **Shipment Method** page, you might need to customize the page and add the field.

## To set up declaration types  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **General Ledger Setup**, and then choose the related link.  
2.  Select the **Simplified Intrastat Decl.** check box to set up a simplified declaration type. Clear this field to use extended declaration.  
3.  Choose the **OK** button.  

## See Also  
 [Belgian Intrastat Reporting](belgian-intrastat-reporting.md)   
 [Set Up Belgian Tariff Numbers](how-to-set-up-belgian-tariff-numbers.md)   
 [Set Up Intrastat Establishment Numbers](how-to-set-up-intrastat-establishment-numbers.md)   
 [Export Intrastat Third-Party Declararations](how-to-export-intrastat-third-party-declararations.md)   
 [Print the Intrastat Form Report](how-to-print-the-intrastat-form-report.md)
