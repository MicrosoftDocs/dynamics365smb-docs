---
title: "Invoice Discounts on Service Documents"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "discounts, service invoices"
  - "service invoices, discounts"
  - "service lines, invoice discounts"
ms.assetid: 8e187da9-c783-4459-bf5a-5e42668211fd
caps.latest.revision: 5
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# Invoice Discounts on Service Documents
After all the information has been entered on the service lines, you can calculate the invoice discount for the whole service document by using the **Calculate Invoice Discount** function. If the **\($ T\_311\_24 Calc. Inv. Discount $\)** check box is selected in the **Sales & Receivables Setup** window, the amount will be calculated automatically.  
  
 The discount will be allocated over all the lines in the service document for items, resources, general ledger accounts, and costs where the **\($ T\_5902\_32 Allow Invoice Disc. $\)** field on the service line is set to **Yes**. This is the default setting for items and resources.  
  
 To calculate the invoice discount, the invoice discount terms defined in the **\($ T\_19 Cust. Invoice Disc. $\)** table are used. To see the invoice discounts that have been set up, in the **Customer** card window, on the **Navigate** tab, in the **Sales** group, choose **Invoice Discounts**.  
  
 The currency code on the service document is used to find the invoice discount terms in the corresponding currency. If invoice discounts have not been defined for foreign currencies, the invoice discount terms in LCY set up in the **Cust. Invoice Disc.** table and the exchange rate as of the posting date on the service document are used.  
  
## See Also  
 [How to: Invoice with Sales Invoice Discounts in LCY](../Finance/how-to-invoice-with-sales-invoice-discounts-in-lcy.md)