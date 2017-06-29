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
# How to: Create Sales Return Orders
You may agree to compensate a customer for an item that you sold them by allowing them to return the item.  
  
 At this point, you have shipped the item to the customer.  
  
### To create a sales return order  
  
1.  In the **Search** box, enter **Sales Return Orders**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**.  
  
3.  Fill in the **No.** field. You can do this in several ways, depending on how you have set up your numbering system.  
  
4.  In the **Sell-to Customer No.** field, enter the customer number.  
  
5.  In the **External Document No.** field, enter the customer's reference number.  
  
6.  You can either fill the lines manually, or, if you want to copy information from other documents, you have two options for filling the lines automatically:  
  
    -   You can use the **Copy Document** batch job to copy an existing document to the return order. Use this function to copy the entire document. It can be either a posted document or a document that is not yet posted. This function only enables exact cost reversing when exact cost reversing is set up as mandatory in the sales and receivables setup.  
  
    -   You can use the **Get Posted Document Lines to Reverse** function to copy one or more posted document lines from one or more posted documents. This function always exactly reverses the costs from the posted document line, regardless of whether exact cost reversing is set up as mandatory in the sales and receivables setup.   
        When you use either of these functions, a link is created to the original item ledger entries in the **Appl.-from Item Entry** field to ensure that the costs are copied from the original posted document. If the line has item tracking, the **Appl.-from Item Entry** field is filled in on the item tracking line or lines instead of on the document line. For more information, see [How to: Assign Exact Cost Reversing in Sales](../Finance/how-to-assign-exact-cost-reversing-in-sales.md).  
  
7.  In the **Return Reason Code** field, select the reason for the return.  
  
 If the location on the sales return order line is set up to require bins, but not to require put-away processing, you can assign a bin code on the line to indicate where the item should be placed when it arrives at the location.  
  
## See Also  
 [How to: Create a Restock Charge](../Sales/how-to-create-a-restock-charge.md)   
 [How to: Reverse Posted Document Lines](../Finance/how-to-reverse-posted-document-lines.md)   
 [How to: Create and Post Sales Allowances](../Sales/how-to-create-and-post-sales-allowances.md)   
 [How to: Post Sales Returns](../Sales/how-to-post-sales-returns.md)   
 [How to: Create Replacement Sales Orders](../Sales/how-to-create-replacement-sales-orders.md)   
 [How to: Close Open Item Ledger Entries Resulting from Fixed Application in the Item Journal](../Finance/how-to-close-open-item-ledger-entries-resulting-from-fixed-application-in-the-item-journal.md)   
 [Manage Sales Returns](../Sales/manage-sales-returns.md)