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
# How to: Create Sales Credit Memos
A sales credit memo is typically used when a customer returns an item, but it can also be used to give a customer compensation such as a sales allowance and to correct an erroneous invoice.  
  
 If you use the invoicing features, it is a good idea to use credit memos too. They make it easier to manage your receivables.  
  
### To create a sales credit memo  
  
1.  In the **Search** box, enter **Sales Credit Memos**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**. Create a new sales credit memo.  
  
3.  Fill in the **No.** field.  
  
4.  In the **Sell-to Customer No.** field, enter the number of the customer that returned the items.  
  
5.  You can fill in the lines manually, or you have two options for filling the credit memo lines automatically:  
  
    -   You can use the  **Copy Document** batch job to copy an existing document to the credit memo. Use this function to copy the entire document. It can be either a posted document or a document that is not yet posted.  
  
    -   You can use the **Get Posted Document Lines to Reverse** function to copy one or more posted document lines from one or more posted documents. This function’s purpose is to allow you to exactly reverse the costs from the posted document line.  
  
6.  On the **Invoicing** FastTab, you can see the other information that was copied from the customer card. If you want to post the credit memo to a different customer than the one specified on the **General** FastTab, enter the number of that customer in the **Bill-to Customer No.** field.  
  
7.  You can compare the credit memo to the original posted document, for example, in the **Posted Sales Invoices** window.  
  
8.  In the **Posting Date** and **Document Date** fields, enter a date.  
  
9. On the credit memo lines, enter information about the items that have been returned or the sales allowance that will be sent.  
  
     You can apply the credit memo line to a specific item ledger entry, job entry, or service entry, and you can assign item charges cost to it.  
  
 If the **Return Receipt on Credit Memo** field is selected in the Sales & Receivables setup, a posted return receipt will be created when the credit memo is posted.  
  
## See Also  
 [How to: View Additional Information About Sales Credit Memos](../how-to-view-additional-information-about-sales-credit-memos.md)   
 [How to: Correct Sales Invoices with Credit Memos](../how-to-correct-sales-invoices-with-credit-memos.md)   
 [How to: Create and Post Sales Allowances](../how-to-create-and-post-sales-allowances.md)   
 [How to: Combine Return Receipts](../how-to-combine-return-receipts.md)