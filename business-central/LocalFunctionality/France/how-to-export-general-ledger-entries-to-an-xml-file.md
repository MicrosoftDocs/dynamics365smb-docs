---
    title: How to Export General Ledger Entries to an XML File
    description: You can export financial transactions for a particular period to an XML file for external archiving.

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
# Export General Ledger Entries to an XML File
You can export financial transactions for a particular period to an XML file for external archiving. After the closing of the fiscal year, you can export the general ledger transactions for the closed year by applying the correct date filter and then exporting the financial transactions within the specified period to the XML file. The XML file includes all the general ledger transaction information, such as document posting date, document type, document number, account type, account number, credit amount, and debit amount retrieved from the **General Journal** page.  

## To export general ledger entries to an XML file  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Export G/L Entries to XML**, and then choose the relevant link.  
2.  On the **Export G/L Entries to XML** page, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Starting Date**|Sets the starting date to export the financial transactions.|  
    |**Ending Date**|Sets the ending date to export the financial transactions.|  

3.  To export the file, choose the **OK** button.  

You can save the generated file to a specified location, or you can open the file.  

> [!WARNING]  
>  If you have set the start date and end date to include the entire fiscal year, the process can take several minutes.  

## See Also  
[Print General Ledger Reports](how-to-print-general-ledger-reports.md)
