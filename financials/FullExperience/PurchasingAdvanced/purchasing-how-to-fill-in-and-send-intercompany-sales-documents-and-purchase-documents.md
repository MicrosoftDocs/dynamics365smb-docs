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
# How to: Fill In and Send Intercompany Sales Documents and Purchase Documents
You use intercompany documents to post transactions with your intercompany partners. When you post an intercompany document in your company, ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> creates a corresponding document in your IC outbox that you can transfer to your partner. Your partner can then post the document in their company, without having to reenter the data.  
  
 The following procedure describes how to fill in and send an intercompany sales order, but the same steps also apply to intercompany purchase orders, intercompany invoices, return orders, and credit memos  
  
### To fill in and send an intercompany sales order  
  
1.  In the **Search** box, enter **Sales Order**, and then choose the related link.  
  
2.  On the **Home** tab, choose **New** to create a new sales order.  
  
3.  In the **Sell-to Customer No.** field, enter the number of a customer who has been assigned an intercompany partner code.  
  
4.  Fill in the rest of the fields on the document header.  
  
5.  Fill in the sales lines. Fill in the **IC Partner Ref. Type** and **IC Partner Reference** fields to indicate the item or account in your partner's company that corresponds to the item or account on the line.  
  
6.  To send the sales order before you post it, on the **Actions** tab, in the **Functions** group, choose **Send IC Sales Order Cnfmn.** Otherwise, the document will automatically be sent to your outbox when you post the document.  
  
> [!NOTE]  
>  You can send sales and purchase orders and return orders before posting. Invoices and credit memos cannot be sent until they are posted.  
  
## See Also  
 [How to: Handle Outgoing Intercompany Transactions](../how-to-handle-outgoing-intercompany-transactions.md)   
 [How to: Handle Incoming Intercompany Transactions](../how-to-handle-incoming-intercompany-transactions.md)   
 [How to: Fill In and Post Intercompany Journals](../how-to-fill-in-and-post-intercompany-journals.md)