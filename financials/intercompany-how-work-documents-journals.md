---
title: wefwsfwvf| Microsoft Docs
description: wefwsswv
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: IC, group, consolidation, affiliate, subsidiary
ms.date: 06/16/2017
ms.author: sgroespe

---
# How to: Work with Intercompany Documents and Journals

## To fill in and send an intercompany sales order  
You use intercompany documents to post transactions with your intercompany partners. When you post an intercompany document in your company, creates a corresponding document in your IC outbox that you can transfer to your partner. Your partner can then post the document in their company, without having to reenter the data.  

The following procedure describes how to fill in and send an intercompany sales order, but the same steps also apply to intercompany purchase orders, intercompany invoices, return orders, and credit memos  

1. In the **Search** box, enter **Sales Order**, and then choose the related link.  
2. On the **Home** tab, choose **New** to create a new sales order.  
3. In the **\($ T\_36\_2 Sell\-to Customer No. $\)** field, enter the number of a customer who has been assigned an intercompany partner code.  
4. Fill in the rest of the fields on the document header.  
5. Fill in the sales lines. Fill in the **\($ T\_37\_107 IC Partner Ref. Type $\)** and **\($ T\_37\_108 IC Partner Reference $\)** fields to indicate the item or account in your partner's company that corresponds to the item or account on the line.  
6. To send the sales order before you post it, on the **Actions** tab, in the **Functions** group, choose **Send IC Sales Order Cnfmn.** Otherwise, the document will automatically be sent to your outbox when you post the document.  

> [!NOTE]  
>  You can send sales and purchase orders and return orders before posting. Invoices and credit memos cannot be sent until they are posted.  


## To fill in and post an intercompany journal  
Use intercompany \(IC\) journals to post transactions with your intercompany partners. When you post an intercompany journal, a corresponding journal is created in your IC outbox that you can transfer to your partner. Your partner can then post the journal in their company, without having to re\-enter the data.

1. In the **Search** box, enter **\($ N\_610 IC General Journal $\)**, and then choose the related link.  
2. In the **\($ T\_81\_3 Account Type $\)** field, enter either **IC Partner**, **Customer**, or **Vendor**.  In the **\($ T\_81\_4 Account No. $\)** field, select the IC partner code or the customer or vendor number of the partner that you will send the transaction to.  

    > [!NOTE]  
    >  If you enter a customer or vendor number, it must have an IC partner code assigned to it.  

3. Fill in the fields as you would fill in a regular general journal.  
4. In the **\($ T\_81\_116 IC Partner G\/L Acc. No. $\)** field, enter the IC general ledger account that the amount will be posted to in your partner's company. This field must be filled in on a line with a bank account or general ledger account in either the **\($ T\_81\_4 Account No. $\)** field or the **\($ T\_81\_11 Bal. Account No. $\)** field.  
5. After filling in the fields, post the journal.  

Now entries have been posted in your company and corresponding entries have been created in your IC outbox for you to send to your partner company.  


## See Also
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Working with General Journals](ui-work-general-journals.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
