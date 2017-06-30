---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# Correction of Incorrect Posted Documents
If you have posted a document, for example a purchase order, and you discover that some of the information on the lines was incorrect, you can correct this posted document.  
  
 In the following, an incorrect posted purchase order is used as an example.  
  
 There are three ways of correcting a posted purchase order:  
  
-   Creating an identical credit memo and a new purchase order to reverse the posting.  
  
-   Revaluing the posted items.  
  
-   Creating a credit memo and posting it with an item charge.  
  
 In the following, the three methods are briefly described. None of the methods will result in an incorrectly calculated average cost.  
  
## Creating an Identical Credit Memo and a New Purchase Order  
 Creating a credit memo with the same information as in the incorrectly filled-in purchase order effectively reverses the posted order. You can either fill in the credit memo manually or you can use one of two methods to fill the lines automatically:  
  
-   You can use the [Copy Document](../-$-b_492-copy-purchase-document-$-duplicate.md) batch job to copy an existing document to the credit memo. Use this function to copy the entire document. It can be either a posted document or a document that is not yet posted. This function only reverses costs exactly when exact cost reversing is set up as mandatory in Purchases and Payables Setup.  
  
-   You can use the [Get Posted Document Lines to Reverse](../how-to-reverse-posted-document-lines.md) function to copy one or more posted document lines from one or more posted documents to the new credit memo document. This function always exactly reverses the costs from the posted document line, regardless of whether exact cost reversing is set up as mandatory in Purchases and Payables Setup.  
  
 When you use either of these methods \(and, in the case of the Copy Document batch job, when you have also set up exact cost reversing as mandatory in Purchases and Payables Setup\), the program creates a link to the original item ledger entries in the Appl.-to Item Entry field to ensure that the costs are copied from the original posted document. If the line has item tracking, the program cannot provide exact cost reversing because reservation is not available from the purchase credit memo. You can create a purchase return order instead to achieve exact cost reversing of an item-tracked line.  
  
 You must fill in the [Appl.- to Item Entry](../\($%20T_39_38%20Appl.-to%20Item%20Entry%20$\).md) field. This is only possible if the incorrect item ledger entry is still open. When you post the credit memo, the incorrect document has been reversed and you can re-enter it into the system by creating a new purchase order and filling it in correctly.  
  
 Reversing the incorrect document means that the program "deletes" the quantities and the inventory value of the incorrect purchase order.  
  
 If you also want to correct the vendor accounts, you can fill in the [Apply to Doc.-Type](../\($%20T_38_53%20Applies-to%20Doc.%20No.%20$\).md) fields in the purchase credit memo header. If the header has a Correction field, you must place a check mark in that field.  
  
## Revaluing the Posted Items  
 Using the revaluation journal to correct the posted order lets you correct the inventory value of the posted items, but you cannot update the vendor accounts or the quantity on hand.  
  
 In the revaluation journal, fill in the [Item No.](../\($%20T_83_5803%20Inventory%20Value%20\(Revalued\)%20$\).md) field.  
  
 This method corrects the inventory value only.  
  
## Creating A Credit Memo And Posting It With an Item Charge  
 You can correct the incorrect posted purchase order by creating a credit memo with the same header as the original document but without the incorrect lines. Instead, you can create an item charge line \(that is, a line where the type is Charge \(Item\)\).  
  
 First, you must have set up an item charge number to identify these kinds of corrections.  
  
 You can then use the Item Charge Assignment \(Purch\)%20$\).md) window to create a link to the incorrect posted purchase receipt. When you post the credit memo, the program updates the inventory value and the vendor ledger entries.  
  
## See Also  
 [How to: Correct Purchase Invoices with Purchase Credit Memos](../how-to-correct-purchase-invoices-with-purchase-credit-memos.md)   
 [How to: Create Purchase Credit Memos](../how-to-create-purchase-credit-memos.md)   
 [Inventory Revaluation](../inventory-revaluation.md)   
 [How to: Set Up Item Charge Numbers](../how-to-set-up-item-charge-numbers.md)   
 [Processing Purchase Orders](../processing-purchase-orders.md)