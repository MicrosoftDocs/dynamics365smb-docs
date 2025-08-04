---
title: Set Up Codes for Audit Trails
description: Learn about the tasks to set up source codes and reason codes that you can use to track audit trails.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: accounting, auditing, bookkeeping
ms.search.form: 257, 259, 279
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Setting Up Source Codes and Reason Codes for Audit Trails

All posted entries are automatically assigned a source code so that transactions can be traced to their origin. If you want to give entries a supplementary source code, you can use reason codes. Reason codes are used to indicate why an entry was created. When you set up reason codes, you can assign them to entire journal templates and journal batches, and you can assign them to individual journal lines and documents.  

For both source codes and reason codes, use codes that are easy to remember and descriptive. The code must be unique, and you can set up as many codes as you like.

## Define source codes

Sometimes, you want see how a particular entry arose, such as whether it came from posting a general journal or a purchase invoice. A source code indicates where an entry was created. Entries are created when journals and invoices are posted and when certain batch jobs are executed. Each posting type has a specific source code that is assigned when individual entries are created.  

Posting journals, orders, invoices, or credit memos, and running various batch jobs, creates entries in the financial statements. The **Source Code Setup** page contains several FastTabs, one for each application area. Each FastTab contains the source codes that are applicable for that application area.

When you post or run a batch job, the correct source code is automatically attached to the entry. For example, when you post from the general journal, the entry is coded as *GENJNL*. You can then filter the **General Ledger Entries** page to show which entries were posted from the general journal or from sales documents, for example

### To define source codes

1. Choose the ![Search for Page or Report.](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Source Code Setup**, and then choose the related link.  

2. In the **Source Code Setup** window, for each each posting type and batch job, specify the relevant source code.  

You can change the contents of a field later, and that change will then impact future postings.

## Change source codes

You may want to change a source code. For example, you want to change the source code *GENJNL* to *GNJ*.

### To change source codes

1. Choose the ![Search for Page or Report.](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Source Codes**, and then choose the related link.

2. On the line with the code to be changed, select the code in the **Code** field.

3. Enter the new code, and then choose the **Yes** button. You can also change the contents of the **Description** field.

All new entries that are posted from the general journal will have the new source code.

## Define reason codes

Reason codes supplement the source codes and are used to indicate why an entry was created. You can assign reason codes on individual entries, and you can assign permanent codes to specific journal templates and journal batches. When a reason code is linked to a journal line or a sales or purchase header, all entries are marked with the reason code when they are posted.  

### To set up reason codes

1. Choose the ![Search for Page or Report.](media/ui-search/search_small.png "Search for Page or Report icon")  icon, enter **Reason Codes**, and then choose the related link.

2. In the **Reason Codes** window, enter the first code in the **Code** field. In the **Description** field, enter an explanatory text.

Repeat the procedure for each code you want to use. You can set up any number of codes.

The following procedure describes how to add a reason code to a journal template, but similar steps apply to adding a reason code to a journal line or journal batch.  

### To assign reason codes to journal templates

1. Choose the ![Search for Page or Report.](media/ui-search/search_small.png "Search for Page or Report icon")  icon, enter **General Journal Templates**, and then choose the related link.

2. On the line with the selected journal template, in the **Reason Code** field, specify the relevant code.

3. Close the journal template.

The selected reason code will be copied to new journal batches created under this journal template. You assign reason codes to journal templates in the other application areas in the same way.

### To use reason codes on sales and purchase documents

1. Open the relevant sales or purchase document.

2. On the sales or purchase header, enter the code in the **Reason Code** field.

When the invoice is posted, the reason code is copied to each general ledger, customer, and vendor entry. You cannot assign different reason codes to the individual purchase and sales lines because all lines are posted as one entry.

## Related information

[Finance](finance.md)  
[Reconciling Bank Accounts](bank-manage-bank-accounts.md)  
[Work with Dimensions](finance-dimensions.md)  
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Analyzing Cash Flow in Your Company](finance-analyze-cash-flow.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]
