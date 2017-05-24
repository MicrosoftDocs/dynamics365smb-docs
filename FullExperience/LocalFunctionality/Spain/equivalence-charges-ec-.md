---
title: "Equivalence Charges (EC)"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "EC (equivalence charges)"
  - "equivalence charges (EC)"
ms.assetid: 033e5356-55cc-4ceb-87ac-eccfdbf0140e
caps.latest.revision: 11
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "es-es"
---
# Equivalence Charges (EC)
An Equivalence Charge \(EC\) is a tax that is used in retail sales and in activities that do not follow VAT rules. Under EC rules, companies must pay a surcharge to their vendors when purchasing goods, in addition to the usual VAT. However, when selling goods, only VAT can be charged. Some general posting groups must have an EC percentage in addition to the VAT percentage. This information is tracked separately, but in order to minimize changes, both taxes are usually combined.  
  
 The **EC %** field is a separate field in the **\($ T\_39 Purchase Line $\)**, **\($ T\_37 Sales Line $\)**, **\($ T\_5108 Sales Line Archive $\)** and **\($ T\_5110 Purchase Line Archive $\)** tables. However, in sales and purchase lines, both taxes are combined and the value is displayed in the **VAT %** field. The **\($ T\_325\_4 VAT \+ EC % $\)** field is used when these values are combined. At the time of posting, the VAT percentage and the EC percentage are inserted in the **\($ T\_254 VAT Entry $\)** table. This makes it possible to print the **\($ R\_10704 Sales Invoice Book $\)** report and the **\($ R\_10705 Purchases Invoice Book $\)** report.  
  
## See Also  
 [\($ T\_288\_10705 Use For Electronic Payments $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/-$-t_288_10705-use-for-electronic-payments-$-.md)   
 [\($ T\_254\_10700 VAT Percentage $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/-$-t_254_10700-vat-percentage-$-.md)   
 [\($ T\_325\_10701 VAT Percentage $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/-$-t_325_10701-vat-percentage-$-.md)