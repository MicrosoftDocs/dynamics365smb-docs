---
    title: How to Create Electronic VAT and ICP Declarations
    description: To create electronic VAT and ICP declarations, you must first set up the declaration using the **Elec. Tax Declaration Setup** window. Then you can submit them to the tax authorities.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Create Electronic VAT and ICP Declarations
To create electronic VAT and ICP declarations, you must first set up the declaration using the **Elec. Tax Declaration Setup** window. Then you can submit them to the tax authorities.  

> [!NOTE]  
>  If you have selected the **Part of Fiscal Entity** field in the **Elec. Tax Declaration Setup** window, then you can create an electronic declaration for only one company. If you want to combine the tax information for all subsidiaries of a holding company, you must create a VAT statement on paper for each subsidiary company and manually calculate the total amounts for the holding company. These total amounts of the holding company must be entered on the website of the tax authorities. You cannot combine tax information for ICP declarations. ICP declarations must always be submitted individually.  

If there are no intra-community deliveries in the declaration period, then an electronic ICP declaration is created without XML elements for the deliveries. If you submit such a declaration, an error message will be displayed.  

## To create an electronic VAT or ICP declaration  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Elec. Tax Declarations**, and then choose the related link.  
2.  In the **Elec. Tax Declaration List** window, choose the **New** action.  
3.  In the **Elec. Tax Declaration Card** window, on the **General** FastTab, fill in the required fields as described in the following table.  

    |Field|Description|  
    |-----------------------------------|---------------------------------------|  
    |**Template Name**|The name of the template that will be used to create the electronic declaration.|  
    |**Statement Name**|The name of the statement that will be used to create the electronic declaration.|  

6.  Choose the **OK** button.  

The XML elements and the accompanying data of the electronic declaration are displayed on the **Lines** FastTab in the **Elec. Tax Declaration Card** window.  

## See Also  
 [Electronic Tax Declarations](electronic-tax-declarations.md)   
 [Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md)   
 [Set Up VAT Categories](how-to-set-up-vat-categories.md)
