---
    title: How to Set Up Business Activity Statements
    description: You must set up a Business Activity Statement (BAS) to generate a BAS report.

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
# How to: Set Up Business Activity Statements
You must set up a Business Activity Statement (BAS) to generate a BAS report. BAS setup includes the following:  

-   Goods and Services Tax (GST) posting setup.  
-   BAS – XML field IDs.  
-   BAS setup names.  

## To set up GST posting  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Posting Setup**, and then choose the related link.  
2.  To set up GST posting rules, create a new line and enter information into the relevant fields.  
3.  Choose the **OK** button.  

## To set up BAS – XML field IDs  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **BAS – XML Field IDs**, and then choose the related link.  
2.  Choose the **New** action to create a new line.  
3.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**XML Field ID**|The name for the BAS field, as it appears in the XML file.|  
    |**Field No.**|The internal [!INCLUDE[navnow](../../includes/navnow_md.md)] number that corresponds to the field label number in the XML file.|  
    |**Field Label No.**|This value is replicated from the XML file received from the Australian Tax Office (ATO). It refers to the relevant section of the BAS, as described in the BAS instructions from the ATO. **Note:**  The value in this field is updated when you select a value in the **Field No.** field.|  
    |**Field Description**|This is the description for the value in the **Field Label No.** field. **Note:**  The value in this field is updated when you select a value in the **Field No.** field.|  

4.  Choose the **OK** button.  

## To set up BAS  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **BAS Setup Names**, and then choose the related link.  
2.  Choose the **New** action.  
3.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Name**|The BAS setup name.|  
    |**Description**|The description for the BAS setup name.|  

4.  Choose the **OK** button.  
5.  In the **BAS Setup Name** window, choose the **BAS Setup** action.  
6.  In the **BAS Setup** window, enter the BAS setup information.  
7.  Choose the **OK** button.  

## See Also  
 [Business Activity Statements](business-activity-statements.md)   
 [How to: Export Business Activity Statements](how-to-export-business-activity-statements.md)   
 [How to: Calculate Goods and Services Tax on Prepayments](how-to-calculate-goods-and-services-tax-on-prepayments.md)   
 [How to: Print Goods and Services Tax Sales and Purchase Reports](how-to-print-goods-and-services-tax-sales-and-purchase-reports.md)
