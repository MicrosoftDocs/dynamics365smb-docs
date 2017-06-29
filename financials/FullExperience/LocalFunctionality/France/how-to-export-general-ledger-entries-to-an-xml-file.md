---
title: "How to: Export General Ledger Entries to an XML File"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "general ledger, exporting entries to XML"
  - "exporting, general ledger entries to XML"
ms.assetid: a86fd159-8ea3-4ea4-80ee-22115c5d57cc
caps.latest.revision: 32
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "fr-fr"
---
# How to: Export General Ledger Entries to an XML File
You can export financial transactions for a particular period to an XML file for external archiving. After the closing of the fiscal year, you can export the general ledger transactions for the closed year by applying the correct date filter and then exporting the financial transactions within the specified period to the XML file. The XML file includes all the general ledger transaction information, such as document posting date, document type, document number, account type, account number, credit amount, and debit amount retrieved from the **General Journal** window.  
  
### To export general ledger entries to an XML file  
  
1.  In the **Search** box, enter **Export G\/L Entries to XML**, and then choose the relevant link.  
  
2.  In the **Export G\/L Entries to XML** window, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Starting Date**|Sets the starting date to export the financial transactions.|  
    |**Ending Date**|Sets the ending date to export the financial transactions.|  
  
3.  To export the file, choose the **OK** button.  
  
     You can save the generated file to a specified location, or you can open the file.  
  
    > [!WARNING]  
    >  If you have set the start date and end date to include the entire fiscal year, the process can take several minutes.  
  
## See Also  
 [How to: Print General Ledger Reports](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-print-general-ledger-reports.md)