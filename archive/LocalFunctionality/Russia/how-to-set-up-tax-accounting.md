---
    title: How to Set Up Tax Accounting
    description: Tax accounting lets you apply rules for recognizing income and expenses that follow your local tax laws. You can activate tax accounting features in [!INCLUDE[navnow](../../includes/navnow_md.md)] by setting up tax registers.

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
# Set Up Tax Accounting
Tax accounting lets you apply rules for recognizing income and expenses that follow your local tax laws. You can activate tax accounting features in [!INCLUDE[navnow](../../includes/navnow_md.md)] by setting up tax registers.  

## To activate tax accounting  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Tax Register Setup**, and then choose the related link.  
2.  On the **General** FastTab, select codes for the following dimensions.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Condition Dimension Code**|Select a dimension code that describes the condition of the tax register.|  
    |**Kind Dimension Code**|Select a dimension code that describes the type of tax register.|  

3.  Select the following fields to activate entries in the tax register.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Create Acquis. FA Tax Ledger**|Select to create fixed asset acquisition entries.|  
    |**Create Reclass. FA Tax Ledger**|Select to create fixed asset reclassification entries.|  
    |**Create Acquis. FE Tax Ledger**|Select to create future expense acquisition entries.|  

4.  Select the appropriate depreciation books in the **Tax Depreciation Book** and **Future Exp. Depreciation Book** fields. The depreciation books that you select should not be integrated with the [!INCLUDE[navnow](../../includes/navnow_md.md)] finance module.  

5.  Select the **Create Data for Printing Forms** check box to enable detailed tax register entry information to be printed on reports and forms.  
6.  Choose the **Close** button to close the window and save your entries.  

For more information about how to set up and customize tax registers, see [Create Tax Registers](how-to-create-tax-registers.md).  

## See Also  
 [Tax Accounting](tax-accounting.md)   
 [Tax Reports](assetId:///e42ca8e7-1cee-4fb8-9f71-e596f29cabc3)   
 [Tax Registers](tax-registers.md)   
 [Create Tax Registers](how-to-create-tax-registers.md)   
 [Tax Differences](tax-differences.md)
