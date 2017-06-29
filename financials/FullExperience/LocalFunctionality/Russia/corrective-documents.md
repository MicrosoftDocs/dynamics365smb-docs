---
title: "Corrective Documents"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 04cd400f-e6c6-40e0-863a-3c4a5d82c465
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# Corrective Documents
If you sell or purchase items, and you then reach an agreement to change the price or the quantity, you must issue a corrective document that specifies the new price or quantity. You can also register corrective documents that you receive from a vendor, and you can issue and register corrections to corrective documents.  
  
 If you discover a mistake in an invoice, credit memo, or corrective document, you must issue a revision document.  
  
## Corrective Invoices and Credit Memos  
 When you sell or purchase items, you can create corrective invoices and corrective credit memos to reflect changes in quantity and amounts after the items were shipped or received. You can also create corrective documents to reflect changes in item charges.  
  
 For example, you sell 20 items to a customer, but one item is damaged during transport. You can then issue a corrective invoice for the reduced number of items. If you later agree with the customer that they want a substitute item, you must issue a correction to the corrective invoice. The same pattern applies to adjustments in price if you make a discount after shipping the items.  
  
 The following table describes when to use which corrective document.  
  
|Corrective document type|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
|------------------------------|---------------------------------------|  
|Corrective invoice|Use this document type to post an increase in quantity or price after the items were shipped.|  
|Corrective credit memo|Use this document type to post a reduction in quantity or price after the items were shipped.|  
  
 When you create a corrective document, you can specify which document lines from the original document you want to correct. You can change the quantity of document lines where the type is **Item**. If the line is for an item charge, you can change both quantity and price.  
  
> [!WARNING]  
>  If the corrective document must change the price, the line can be for an item charge or a general ledger account, depending on your inventory setup. If you want to post the difference in the price between the original line and the corrective line to a general ledger account, you must change the line type.  
  
 Before you can create corrective documents, you must have set up prerequisites. For more information, see [How to: Set Up Corrective Invoicing](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-set-up-corrective-invoicing.md).  
  
### Revision Documents  
 If you discover a mistake in a posted document, you must issue a revision and send it to the customer or vendor. In contrast to corrective documents, a revision document can be issued without advance notification of the customer or vendor. Corrective documents can only be issued if both parties agree with the changes in quantity or price in advance  
  
 You can create a revision document for sales invoices, sales credit memos, purchase invoices, purchase credit memos, and corrective documents.  
  
 Before you create and post a revision, you must cancel the original invoice. When you cancel the original invoice, you can use the **Copy Document** batch job and select the **\($ B\_292\_F\_1\_1 Include Header $\)** field in the request window. This creates a link between the original invoice and the revision document. For more information, see [How to: Create Corrective Documents](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-create-corrective-documents.md).  
  
### VAT in Corrective Documents  
 The reports for VAT sales books and additional VAT ledgers include changes in VAT amounts from posted corrective documents. If a corrective document is created in the same VAT period as the original invoice, the amounts are included in the VAT sales book. If a corrective document is created in a VAT period that is later than the period for the original invoice, the amounts must be included in the additional VAT ledger for the period.  
  
> [!IMPORTANT]  
>  To include a corrective invoice in an additional VAT ledger, you must select the **Additional VAT Ledger Sheet** field in the sales invoice window. The same applies to corrective sales credit memos, purchase invoices, and purchase credit memos. For more information, see [How to: Create Corrective Documents](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-create-corrective-documents.md).  
  
## See Also  
 [How to: Set Up Corrective Invoicing](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-set-up-corrective-invoicing.md)   
 [How to: Create Corrective Documents](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-create-corrective-documents.md)