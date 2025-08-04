---
title: Manage the Intercompany Inbox and Outbox
description: Intercompany transactions you receive from your partners are listed in the intercompany inbox, where you process them manually or automatically.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 07/21/2025
ms.custom: bap-template
ms.search.keywords: incoming document
ms.search.form: 600, 605, 611_Primary, 613_Primary, 615_Primary, 617_Primary, 618, 650, 651, 648, 649, 614, 642, 643, 640, 641, 616, 646, 647, 644, 645, 619, 612, 638, 639, 636, 637, Report_512
ms.service: dynamics-365-business-central
---
# Manage the Intercompany Inbox and Outbox

The intercompany transactions that you receive from your partners are listed on the **Intercompany Inbox** page. To learn how to process incoming intercompany transactions, go to [Process incoming intercompany transactions](#process-incoming-intercompany-transactions-using-the-inbox). The intercompany transactions that you send to partners are listed on the **Intercompany Outbox** page. To learn how to process outgoing intercompany transactions, go to [To process outgoing intercompany transactions](#to-process-outgoing-intercompany-transactions-using-the-outbox).

However, depending on your intercompany setup, some transactions are automatically handled. You can set up the source company and partner companies to automatically create documents and journals that correspond to transactions that partners post through the intercompany general journal. To learn about using intercompany journals, go to [Fill in and post an intercompany journal](intercompany-how-work-documents-journals.md#fill-in-and-post-an-intercompany-journal).  

## Organizing the Inbox  

You can use the filter fields at the top of the Inbox page to determine which transactions are shown on the page. For example, if you only want to explore transactions that a particular partner created, use the **Transaction Source** and **Intercompany Partner Code** filters.  

### Transaction source  

What you can do with a transaction depends whether it was:  

* Created by your intercompany partner  
* Rejected by your intercompany partner and returned to you  

Use the **Show Transaction Source** field to filter the **Intercompany Inbox Transactions** page so that it displays only one of these types of transactions. You can also filter by intercompany partner, or by the contents of the **Line Action** field.  

#### Created by intercompany partner  

 When you receive a new transaction that was created by your partner, you can choose to either:

* Accept the transaction  
* Reject the transaction (return to partner)  
* Cancel the transaction (delete the transaction and don't return it to your partner)  

#### Returned from intercompany partner  

If your intercompany partner rejects a transaction, you must cancel the transaction in the inbox and then create correction lines or reverse the journal or document.  

## Recreating inbox entries  

If you accepted a transaction in your inbox but then deleted the document or journal instead of posting it, you can re-create the inbox entry and accept it again.  

## Get an overview of intercompany transactions for a period  

You can get an overview of all of the intercompany transactions that you have sent and received in a period. The **Intercompany Transactions** report lists all intercompany G/L entries, customer ledger entries, and vendor ledger entries.

> [!NOTE]  
> If the intercompany partners are in the same database, the partners can automatically accept transactions. The go directly to the **Handled Intercompany Inbox Transactions** and **Handled Intercompany Outbox Transactions** pages. To learn more about auto-accepting transactions, go to [Auto-accept transactions from intercompany partners](intercompany-how-setup.md#autoaccept-transactions-from-intercompany-partners).  
>
> * For the synchronization partner, on the **Intercompany Setup** page, turn on the **Auto. Send Transactions** toggle.
> * For partner companies, on the **Intercompany Partner** page, turn on the **Auto. Accept Transactions** toggle.  

## Import intercompany transactions from a file

[!INCLUDE [onprem_only_md](includes/onprem_only_md.md)]

If you have an intercompany partner that is not in the same database as your company, you can receive intercompany transactions from that partner in an .xml file. Then you must import the transactions into your inbox.  

1. Save the file to the location that you specified in the **Intercompany Inbox Details** field when you set up intercompany.  
2. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intercompany Inbox Transactions**, and then choose the related link.
3. On the **Intercompany Inbox Transactions** page, choose the **Import Transaction File** action.  
4. on the page that appears, select the .xml file that contains the transactions, and then choose the **Open** button.  

The transactions are imported into the inbox and you can now process them.

## Process incoming intercompany transactions (using the inbox) 

When your intercompany partners send you intercompany transactions, the transactions end up in your intercompany inbox. You must evaluate each transaction in your inbox and act on it.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intercompany Inbox Transactions**, and then choose the related link.  
2. On the **Intercompany Inbox Transactions** page, select a line, and then choose an action, such as **Accept**, to process the line.
3. On the **Complete IC Inbox Action** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Choose the **OK** button.  

For lines that you accept, document or journal lines are created in your company. Open each document or journal, make any necessary changes, and then post them.  

Lines that you reject and return to your partner go to your intercompany outbox, where you can send them to your partner.

For lines that a partner rejected and returned to you, you must post a correction to the original transaction that you posted in your company.

## To process outgoing intercompany transactions (using the outbox) 

When you post an intercompany journal or document, or send an intercompany order confirmation, the transactions go to your intercompany outbox. To send them to your intercompany partners, open the outbox and process them.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intercompany Outbox Transactions**, and then choose the related link.  
2. On the **Intercompany Outbox Transactions** page, select a line, and then choose an action, such as **Return to Inbox**, to process the line.

Use the **Send to Intercompany Partner** action to send lines to the relevant partner's inbox.

Use the **Return to Inbox** action to move lines to your inbox, where you can then accept them to create documents or journal lines in your company.  

If you use the **Cancel** action, you must post a correction to the transaction that you originally posted in your company.  

## Recreate intercompany inbox or outbox transactions  

You might want to re-create a transaction in the inbox or outbox. For example, if you accepted a transaction in your inbox but then deleted the document or journal instead of posting it, you can re-create the inbox entry and accept it again.  

The following procedure describes to re-create inbox transactions, but the same steps also apply to the outbox.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Handled IC Inbox Transactions**, and then choose the related link.  
2. On the **Handled IC Inbox Transactions** page, select the line with the transaction that you want to re-create in the inbox, and then choose the **Re-create Inbox Transaction** action.  

## Related information

[Managing Intercompany Transactions](intercompany-manage.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Work with General Journals](ui-work-general-journals.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
