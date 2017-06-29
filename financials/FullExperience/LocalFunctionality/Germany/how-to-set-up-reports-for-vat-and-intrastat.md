---
title: "How to: Set Up Reports for VAT and Intrastat"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "VAT, reports"
  - "Intrastat, setting up reports"
  - "VAT, Intrastat"
ms.assetid: e49fd417-9994-4519-a080-caf51ee8b684
caps.latest.revision: 6
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "de-de"
---
# How to: Set Up Reports for VAT and Intrastat
In [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)], you can specify which reports to use to create the documents that you must submit to the authorities, such as the VAT statement and the Intrastat form.  
  
### To set up reports for VAT  
  
1.  In the **Search** box, enter **Report Selections VAT**, and then choose the related link.  
  
2.  In the **\($ N\_26101 Report Selection – VAT $\)** window, in the **Usage** field, select the type of document that you want to specify reports for. This includes the VAT statement and the VAT statement schedule.  
  
3.  Specify the report or batch job that must run when a user starts the activity for the document type that you specified in the **Usage** field. Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Sequence**|Specifies where a report is in the printing order.|  
    |**Report ID**|Specifies the ID of the report that prints for this document type.|  
    |**Report Name**|Specifies the name of the report that prints for this document type. The **Report Name** field updates based on the selection in the **Report ID** field.|  
  
4.  Choose the **OK** button.  
  
### To set up reports for Intrastat  
  
1.  In the **Search** box, enter **Report Selection**, and then choose the related link.  
  
2.  In the **\($ N\_26100 Report Selection – Intrastat $\)** window, in the **Usage** field, select the type of document that you want to specify reports for. This includes the Intrastat checklist and Intrastat form.  
  
3.  Specify the report or batch job that must run when a user starts the activity for the document type that you specified in the **Usage** field. Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Sequence**|Specifies where a report is in the printing order.|  
    |**Report ID**|Specifies the ID of the report that prints for this document type.|  
    |**Report Name**|Specifies the name of the report that prints for this document type. The **Report Name** field updates based on the selection in the **Report ID** field.|  
  
4.  Choose the **OK** button.  
  
## See Also  
 [How to: Print VAT Reports\-duplicate](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-print-vat-reports-duplicate.md)   
 [How to: Export and Print Intrastat Reports](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-export-and-print-intrastat-reports.md)   
 Report Selection \- VAT   
 Report Selection \- Intrastat   
 DACH Report Selections   
 Report Selections