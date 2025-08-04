---
title: Transferring and posting cost entries
description: Before you define cost allocations, you must understand the various sources that cost entries come from.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.form:  1100, 1103, 1104, 1108, 1113, 1135
ms.date: 07/26/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Transferring and posting cost entries

Before you define cost allocations, you must understand how cost entries come from the following sources:  

- Automatic transfer of general ledger entries.  
- Manual cost posting for pure cost entries, internal charges, and manual allocations.  
- Automatic allocation postings for actual costs.  
- Transfer of budget entries to actual.

## Criteria for transferring general ledger entries to cost entries

It's important to understand the criteria for transferring general ledger entries to cost entries. During the transfer, the **Transfer GL Entries to CA** batch job uses the following criteria to determine if and how the general ledger entries are transferred.  

General ledger entries are transferred if:  

- The entries have dimension values corresponding to either a cost center or a cost object.  
- The entries have dimension values that correspond to a cost center and a cost object. For these entries, the cost center takes precedence. This helps avoid a situation where a cost type appears in both a cost object and a cost center and is therefore counted twice in the statistics.  
- The document number in the entries is empty, so it will appear with a document number of 0000 in the cost entries.  
- The entries are transferred to a cost type that allows for combined entries and these entries are transferred as a combined entry either monthly or daily.  

General ledger entries aren't transferred if:  

- The entries have dimension values that don't correspond to a cost center or a cost object.  
- The entries have an amount of zero.  
- The entries have a general ledger account that has been deleted.  
- The entries have a general ledger account that isn't of the type **Income Statement**.  
- The entries have a general ledger account that isn't assigned a cost type.  
- The entries have a posting date before the **Starting Date for G/L Transfer**.  
- The entries have been posted with a closing date. These are typically entries that set back the balance of the income statement at the end of the year.

## Transferring general ledger entries to cost entries

You can transfer general ledger entries to cost entries.  

Before you run the process for transferring general ledger entries to cost entries, you must prepare the transfer to avoid manual correction posting.  

### To prepare the transfer  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cost Accounting Setup**, and then choose the related link.  
2.  On the **Cost Accounting Setup** page, verify that the **Starting Date for G/L Transfer** field is set to the correct value.  
3.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Cost Types**, and then choose the related link.  
4.  On the **Cost Type Card** page, verify that the **G/L Account Range** field is linked correctly for each cost type to take entries from the general ledger.  
5.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, and then choose the related link.  
6.  For each relevant general ledger account, on the **G/L Account Card** page, verify that the **Cost Type No.** field is linked correctly to a cost type. For more information, see [Setting Up Cost Accounting](finance-set-up-cost-accounting.md).  
7.  Verify that all relevant general ledger entries have dimension values that correspond to a cost center and a cost object.  

### To transfer general ledger entries to cost entries

1.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transfer GL Entries to CA**, and then choose the related link.  
2.  Choose the **Yes** button to start the transfer. The process transfers all general ledger entries that haven't already been transferred.  

During the transfer, the process creates connections in the entries in the **Cost Entry** table and the **Cost Register** table. This makes it possible to trace the source of cost entries.

## Automatic transfer and combined entries

In cost accounting, you can transfer general ledger entries to a cost type by using a combined posting. You can specify if a cost type receives combined entries in the **Combine Entries** field in the cost type definition. The following table describes the different options.  

|Combine Entries|Description|  
|---------------------|-----------------|  
|None|Each general ledger entry is transferred individually to the corresponding cost type.|  
|Day|General ledger entries with the same posting date are transferred as one entry to the corresponding cost type.|  
|Month|All general ledger entries in the same calendar month are transferred as one entry to the corresponding cost type.|  

> [!IMPORTANT]  
>  If you have selected the **Auto Transfer from G/L** check box on the **Cost Accounting Setup** page, [!INCLUDE[prod_short](includes/prod_short.md)] updates the cost accounting after every posting in the general ledger. Combined entries are not possible.

## Results of transferring general ledger entries to cost entries

During the transfer of general ledger entries to cost entries, [!INCLUDE[prod_short](includes/prod_short.md)] creates connections in the entries in the **G/L Entry** table, the **Cost Entry** table, and the **Cost Register** table to make it possible to trace the connections between cost entries and general ledger entries.  

### General ledger entries

For each general ledger entry that is transferred to cost accounting, [!INCLUDE[prod_short](includes/prod_short.md)] fills the cost **Entry No.** field.  

### Cost entries

For each cost entry, [!INCLUDE[prod_short](includes/prod_short.md)] saves the entry number of the corresponding general ledger entry in the **G/L Entry No.** field in the **Cost Entry** table.  

For combined cost entries, [!INCLUDE[prod_short](includes/prod_short.md)] saves the entry number of the last general ledger entry, which is the entry with the highest entry number.  

The **G/L Account** field in the **Cost Entry** table contains the number of the general ledger account that the cost entry came from.  

For single cost entries, [!INCLUDE[prod_short](includes/prod_short.md)] transfers the posting text from the general ledger entry to the **Description** text field. For combined entries, the text field shows these entries are transferred as combined entries. For example, for a combined entry for the month of October in 2013, the text can be **Combined Entries, October 2013**.  

### Cost register

In the **Cost Register** table, [!INCLUDE[prod_short](includes/prod_short.md)] creates an entry with the source transfer from general ledger. The entry records the first and last entry numbers of the general ledger entries that are transferred, in addition to the first, and last entry numbers of the cost entries that are created.

## Related information

 [About Cost Accounting](finance-about-cost-accounting.md)  
 [Setting Up Cost Accounting](finance-set-up-cost-accounting.md)  
 [Defining and Allocating Costs](finance-define-and-allocate-costs.md)  
 [Accounting for Costs](finance-manage-cost-accounting.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
