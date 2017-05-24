---
title: "VAT Reports"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "reporting VAT"
  - "VAT, reports"
  - "VAT-VIES reports, about"
  - "VAT, about"
  - "VAT, statements"
  - "VIES reporting, about"
  - "VAT reporting, about"
  - "VAT statements, about"
ms.assetid: 4f8f3cca-c5ae-4284-811c-d0a719e7bdc7
caps.latest.revision: 25
ms.author: "edupont"
manager: "terryaus"
---
# VAT Reports
VAT is charged on transactions that involve goods and services in Spain or goods imported into Spain. The following information provides more details about VAT functionality.  
  
## Equivalence Charge  
 Equivalence Charge \(EC\) tax applies to activities that do not follow VAT rules. According to EC rules, companies must pay a surcharge to their vendors in addition to VAT. However, they can only charge VAT without the surcharge on sales invoices.  
  
### VAT with EC Percentage  
 Preset general posting groups have an EC percentage in addition to their VAT percentage. Although the EC is tracked separately, both tax values are merged with VAT when it is possible. If the EC percentage is a separate field in the posting group, the EC is merged with the value in the **VAT %** column.  
  
 For printing sales and purchase invoice books, the VAT percent and EC percentages are displayed in the **\($ T\_254 VAT Entry $\)** table during posting.  
  
> [!NOTE]  
>  If the item has no taxable VAT, 0 is automatically displayed in the **VAT %** field in the VAT information windows.  
  
### Telematic VAT  
 With telematic VAT you can design and generate monthly and yearly tax reports as electronic files or printed files. You can submit these reports to the tax authorities using a third\-party program or an XML file from the tax authorities' website.  
  
### VAT Statement  
 The VAT statement displays VAT amounts and base amounts in different columns.  
  
 There are two report template types in the **\($ T\_257 VAT Statement Name $\)** table:  
  
-   **One\-Column Report**  
  
-   **Two\-Columns Report**  
  
### VAT\-VIES Declaration  
 With VAT\-VIES declaration you can run a batch file to generate European Union \(EU\) sales reports. The batch file exports the entries in the required file format for submission to customs and tax authorities.  
  
## See Also  
 [Spain Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/spain-local-functionality.md)   
 [Report 340](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/report-340.md)   
 [Report 347](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/report-347.md)