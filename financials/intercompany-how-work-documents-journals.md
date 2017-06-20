---
title: Post Intercompany Documents and Journals| Microsoft Docs
description: Use intercompany documents to post transactions with your intercompany partners.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: IC, group, consolidation, affiliate, subsidiary
ms.date: 06/20/2017
ms.author: sgroespe

---
# How to: Work with Intercompany Documents and Journals

## To fill in and send an intercompany sales order  
You use intercompany documents to post transactions with your intercompany partners. When you post an intercompany document in your company, creates a corresponding document in your intercompany outbox that you can transfer to your partner. Your partner can then post the document in their company, without having to reenter the data.  

The following procedure describes how to fill in and send an intercompany sales order, but the same steps also apply to intercompany purchase orders, intercompany invoices, return orders, and credit memos  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales Orders**, and then choose the related link.  
2. Choose **New** to create a new sales order. For more information, see [How to: Sell Products](sales-how-sell-products.md).  
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. To send the sales order before you post it, choose the **Send IC Sales Order Cnfmn.** action. Otherwise, the document will automatically be sent to your outbox when you post the document.  

> [!NOTE]  
>  You can send sales and purchase orders and return orders before posting. Invoices and credit memos cannot be sent until they are posted.  

## To fill in and post an intercompany journal  
Use intercompany (IC) journals to post transactions with your intercompany partners. When you post an intercompany journal, a corresponding journal is created in your intercompany outbox that you can transfer to your partner. Your partner can then post the journal in their company, without having to re-enter the data.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **General Journals**, and then choose the related link.  
2. Open the relevant journal batch. For more information, see [Working with General Journals](ui-work-general-journals.md).
3. Fill in the fields as necessary.

    > [!NOTE]  
    >  If you enter a customer or vendor number, it must have an intercompany partner code assigned to it.  
4. In the **IC Partner G/L Acc. No.** field, enter the intercompany general ledger account that the amount will be posted to in your partner's company. This field must be filled in on a line with a bank account or general ledger account in either the **Account No.** field or the **Bal. Account No.** field.  
5. Choose the **Post** action.

Now entries have been posted in your company and corresponding entries have been created in your intercompany outbox for you to send to your partner company.  

## See Also
[Managing Intercompany Transactions](intercompany-manage.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Working with General Journals](ui-work-general-journals.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
