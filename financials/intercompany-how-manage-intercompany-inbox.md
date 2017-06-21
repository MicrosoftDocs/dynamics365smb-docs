---
title: Process Incoming and Outgoing IC Transactions| Microsoft Docs
description: Intercompany transactions that you receive from your intercompany partners are listed in the intercompany inbox where you process them manually or automatically.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: incoming document
ms.date: 06/21/2017
ms.author: sgroespe

---
# How to: Manage the Intercompany Inbox and Outbox
All of the intercompany transactions that you receive electronically from your intercompany partners are listed in the intercompany Inbox.  

## Organizing the Inbox  
 You can use the filter fields at the top of the inbox window to determine which transactions are shown in the window. For example, if you only want to look at transactions a particular partner created, you can enter filters in the **Transaction Source** and **Intercompany Partner Code** filters.  

### Transaction Source  
 What you can do with a transaction depends whether it was:  

-   Created by your intercompany partner  

-   Rejected by your intercompany partner and returned to you  

 You can use the **Show Transaction Source** field to filter the **Intercompany Inbox Transactions** window so that it displays only one of these types of transactions. (You can also filter by intercompany partner, or by the contents of the **Line Action** field.)  

#### Created by Intercompany Partner  
 When you receive a new transaction that was created by your partner, you can choose to:  

 Accept the transaction  

 Reject the transaction (Return to partner)  

 Cancel the transaction (Delete the transaction but do not return it to your partner)  

#### Returned from Intercompany Partner  
 If the transaction was rejected by your intercompany partner, your only choice is to cancel the transaction in the inbox. Then you must create correction lines or reverse the journal or document in your company.  

## Re-creating Inbox Entries  
 If you accepted a transaction in your inbox but then deleted the document or journal instead of posting it, you can re-create the inbox entry and accept it again.  

## Getting an Overview of Intercompany Transactions for a Period  
 You can get an overview of all of the intercompany transactions that you have sent and received in a period. The **Intercompany Transactions** report lists all intercompany G/L entries, customer ledger entries, and vendor ledger entries.  

## To import intercompany transactions from a file:  
If you have an intercompany partner that is not in the same database as your company, you can receive intercompany transactions from that partner in an .xml file. Then you must import the transactions into your inbox.  


 1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Company Information** , and then choose the related link.  

 2.  Save the file to the location that you specified in the **Intercompany Inbox Details** field in the **Company Information** window.  

 3.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Intercompany Inbox Transactions**, and then choose the related link.  

 4.  In the **Intercompany Inbox Transactions** window, on the **Actions** tab, in the **Functions** group, choose **Import Transaction File**.  

 5.  In the window that appears, select the .xml file that contains the transactions and then choose the **Open** button.  

  The transactions are imported into the inbox and you can now process them.

## To handle incoming intercompany transactions  
When your intercompany partners send you intercompany transactions, the transactions end up in your intercompany inbox. You must evaluate each transaction in your inbox and act upon it.  

  1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Intercompany Inbox Transactions**, and then choose the related link.  

  2.  In the **Intercompany Inbox Transactions** window, to see details of a transaction, select the transaction.  

  3.  On the **Navigate** tab, in the **Inbox Transactions** group, choose **Details**  

  4.  In the **Intercompany Inbox Transactions** window, enter an option in the **Line Action** field for each transaction. You can either fill in the field on one line at a time, or you can select several lines and then on the **Actions** tab, in the **Functions** group, choose **Set Line Action**. Choose the relevant option.  

  5.  On the **Actions** tab, in the **Functions** group, choose **Complete Line Actions**.  

  6.  Fill in the **Complete IC Inbox Action** batch job request page. On the **Intercompany Inbox Transaction** FastTab, you can set filters to determine which transactions will be completed. On the **Options** FastTab, you specify the journal template and batch that you want to use, and other posting details. Choose the **OK** button.  

  7.  If any of the lines in the inbox contains **Accept** in the **Line Action** field, document or journal lines are created in your company. Open each document or journal, make any necessary changes, and post.  

  8.  If any of the lines contains **Return to Partner** in the **Line Action** field, they have been moved to the outbox. Send them to your partner from there.  

  9. If any of the lines contains **Returned by Partner** in the **Transaction Source** field, post a correction to the original transaction that you posted in your company

## To handle outgoing intercompany transactions  
When you post an intercompany journal or document, or send an intercompany order confirmation, the transactions are sent to your intercompany outbox. In order for them to be sent on to your intercompany partners, you must open the outbox and process them.  

  1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Intercompany Outbox Transactions**, and then choose the related link.  

  2.  In the **Intercompany Outbox Transactions** window, select the transaction. On the **Navigate** tab, in the **Outbox Transactions** group, choose **Details** to see the details of a transaction.  

  3.  In the **Intercompany Outbox Transactions** window, enter an option in the **Line Action** field for each transaction.  

  4.  You can either fill in the field on one line at a time, or you can select several lines. On the **Actions** tab, in the **Functions** group, choose **Set Line Action**, and then choose the relevant option.  

  5.  On the **Actions** tab, in the **Functions** group, choose **Complete Line Actions**, and then choose the **Yes** button in the window that appears.  

  6.  If any of the lines in the outbox contains **Send to Intercompany Partner** in the **Line Action** field, each line has been sent to the relevant partner's inbox.  

  7.  If any of the lines contains **Return to Inbox** in the **Line Action** field, they have been moved to the inbox. You can accept them in the inbox. Documents or journal lines will then be created in your company.  

  8.  If any of the lines contains **Cancel** in the **Line Action** field, you must now post a correction to the original transaction that you posted in your company.  

## To recreate intercompany inbox transactions  
Occasionally, you may want to re-create a transaction in the inbox or outbox. For example, if you accepted a transaction in your inbox but then deleted the document or journal instead of posting it, you can re-create the inbox entry and accept it again.  

 The following procedure describes to re-create inbox transactions, but the same steps also apply to the outbox.

  1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Handled IC Inbox Transactions**, and then choose the related link.  

  2.  In the **Handled IC Inbox Transactions** window, select the line with the transaction that you want to re-create in the inbox.  

  3.  On the **Actions** tab, in the **Functions** group, choose **Re-create Inbox Transaction**. Choose the **Yes** button.  

## See Also
[Managing Intercompany Transactions](intercompany-manage.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Working with General Journals](ui-work-general-journals.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
