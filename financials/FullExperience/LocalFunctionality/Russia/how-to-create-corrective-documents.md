---
title: "How to: Create Corrective Documents"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "corrective documents, creating"
ms.assetid: 13a11268-326d-4276-96b7-f430482489d1
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# How to: Create Corrective Documents
In ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]-->, you can create corrective invoices and credit memos to reflect a change in the invoiced amount or quantity.  
  
 You can also create revision documents if you discover a mistake in an issued invoice or credit memo.  
  
 The following procedure shows how to create a corrective sales invoice, but the same steps apply to sales credit memos, purchase invoices, and purchase credit memos.  
  
> [!NOTE]  
>  You cannot create corrective documents for service documents.  
  
### To create a corrective invoice  
  
1.  In the Navigation Pane, in the **Financial Management** area, choose **Receivables**, and then choose **Corrective Invoice**.  
  
2.  In the **Sales Corrective Invoice** window, press F3 to create a new document. On the **General** tab and the **Invoicing** tab, fill in the fields.  
  
     Some fields are filled in automatically when you select a customer. Other fields you must fill in manually. You must make sure that the values of fields such as **Prices Including VAT** and **Currency Code**, relevant dimensions, and so on are the same in the corrective document as in the original invoice.  
  
    > [!NOTE]  
    >  On the **Invoicing** tab, fill in the **Agreement No.** field if you have set up an agreement. For more information, see [How to: Set Up Customer and Vendor Agreements](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-set-up-customer-and-vendor-agreements.md).  
  
3.  On the **VAT** tab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Additional VAT Ledger Sheet**|Optionally, select to include this document in the additional VAT ledger. For more information, see [VAT Ledgers](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/vat-ledgers.md).|  
    |**Corrected Document Date**|If you selected the **Additional VAT Ledger Sheet** field, specify the posting date of the document that you are correcting.<br /><br /> This ensures that the original invoice is listed as canceled in the additional sheet for the sales VAT book in the relevant report period.|  
    |**Corrective Document**|Select to make this document a corrective document.|  
    |**Corrective Doc. Type**|Choose **Correction** to make this a correction to an invoice.|  
    |**Corrected Doc. Type**|Specify if the original document was an invoice or a credit memo.|  
    |**Corrected Doc. No.**|Specify the original document.<br /><br /> Depending on the value of the **Corrected Doc. Type** field, you can select a posted invoice or a posted credit memo.|  
    |**Revision No.**|Optionally, specify a revision number if this document is a revision of a corrective document.|  
  
     Choose **Functions**, and then choose **Get Corr. Doc. Lines**.  
  
4.  In the **Sales Invoice Lines** window, select the lines that you want to add to the corrective documents, and then choose the **OK** button.  
  
5.  In the dialog box that appears, specify if the correction if for quantity or price.  
  
6.  Make the appropriate changes to the document lines. For example, to change the invoiced amount, change the value of the **Amount \(After\)** field.  
  
    > [!NOTE]  
    >  If the document line is for an item, you can only change the value of the **Amount \(After\)** field. If the document line is for an item charge, you can change the value of the **Quantity \(After\)** field and the **Amount \(After\)** field.  
  
7.  Post the document.  
  
     The posted document is included in the list of posted invoices. This means that you can select it in the **Corrected Doc. No.** field if you must create a correction for this corrected document.  
  
 The following procedure describes how to create a revision for a posted sales invoice but the same steps apply to sales credit memos, purchase invoices, purchase credit memos, and corrective documents.  
  
### To create a revision document for a sales invoice  
  
1.  In the Navigation Pane, in the **Financial Management** area, choose **Receivables**, and then choose **Invoices**.  
  
2.  In the **Sales Invoice** window, press F3 to create a new document.  
  
3.  Choose the **Functions** button, and then choose **Copy Document**.  
  
4.  In the **Copy Sales Document** window, fill in the fields to import information from the original sales invoice.  
  
    > [!NOTE]  
    >  Select the **\($ B\_292\_F\_1\_1 Include Header $\)** field.  
  
5.  On the **VAT** tab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Additional VAT Ledger Sheet**|Optionally, select to include this document in the additional VAT ledger. For more information, see [VAT Ledgers](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/vat-ledgers.md).|  
    |**Corrected Document Date**|If you selected the **Additional VAT Ledger Sheet** field, specify the posting date of the document that you are revising.<br /><br /> This ensures that the original invoice is listed as canceled in the additional sheet for the sales VAT book in the relevant report period.|  
    |**Corrective Document**|Select to make this document a corrective document.|  
    |**Corrective Doc. Type**|Choose **Revision** to make this a revision document.|  
    |**Corrected Doc. Type**|Specify if the original document was an invoice or a credit memo.|  
    |**Corrected Doc. No.**|Specify the original document.<br /><br /> Depending on the value of the **Corrected Doc. Type** field, you can select a posted invoice or a posted credit memo.|  
    |**Revision No.**|Specify a revision number.<br /><br /> The revision number is not used by ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]-->, but it is included in the printed document.|  
  
6.  Make the relevant changes to the document lines.  
  
7.  Post the document.  
  
 The posted document is included in the list of posted invoices. This means that you can select it in the **Corrected Doc. No.** field if you must create a correction for this corrected document.  
  
## See Also  
 [Corrective Documents](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/corrective-documents.md)