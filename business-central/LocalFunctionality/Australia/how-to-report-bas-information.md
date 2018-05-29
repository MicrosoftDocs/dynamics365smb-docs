---
    title: How to Report BAS Information
    description: You need to report the Business Activity Statement (BAS) calculation information for goods and services tax (GST). The **C** and **D** fields on the **Totals** FastTab in the **BAS Calculation Sheet** window are used for fuel tax credits.

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
# Report BAS Information
You need to report the Business Activity Statement (BAS) calculation information for goods and services tax (GST). The **C** and **D** fields on the **Totals** FastTab in the **BAS Calculation Sheet** window are used for fuel tax credits.  

## To report BAS information and calculate the GST settlement  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **BAS Calculation Sheets**, and then choose the related link.  
2.  Choose the **New** action.  
3.  In the **BAS Calculation Sheet** window, choose the **Import** action.  
4.  In the **BAS – Import/Export** window, enter the BAS file name to import a sample XML file. The totals information will be updated. Choose the **OK** button.  
5.  In the **BAS Calculation Sheet** window, choose the **Update** action.  
6.  In the **BAS-Update** window, choose the **Preview** button to view the update information. Choose the **OK** button to close the preview window.  
7.  In the **BAS Calculation Sheet** window, choose the **Export** action.  
8.  In the **BAS – Import/Export** window, select an XML file to export the data to, and then choose the **OK** button. The XML file is updated with the new information. If you use Electronic Commerce Interface (ECI) to update your taxes, the information in the XML file will be complete.  
9. In the **BAS Calculation Sheet** window, choose the **Calculate GST Settlement** action.  
10. In the **Calculate GST Settlement** window, make sure that the **Post** field is selected. When you run the report, the resulting GST settlement postings include the fuel tax values.  

## See Also  
 [BAS Fuel Tax Credits](bas-fuel-tax-credits.md)   
 [Set Up BAS XML Fields](how-to-set-up-bas-xml-fields.md)   
 [Business Activity Statements](business-activity-statements.md)
