---
title: How to Post Inventory Costs to the General Ledger| Microsoft Docs
description: Describes how to manage the physical products that you trade in, for example, handling the stock in your warehouse.
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: warehouse, stock
ms.date: 04/01/2020
ms.author: sgroespe

---
# Reconcile Inventory Costs with the General Ledger
When you post inventory transactions, such as sales shipments, purchase invoices, or inventory adjustments, the changed item costs are recorded in item value entries. To reflect this change of inventory value in your financial books, the inventory costs are automatically posted to the related inventory accounts in the general ledger. For each inventory transaction that you post, the appropriate values are posted to the inventory account, adjustment account, and COGS account in the general ledger.

Automatic cost posting is defined by the **Automatic Cost Posting** field on the **Inventory Setup** page.

Even though inventory costs are automatically posted to the general ledger, it is still necessary to ensure that the costs of goods are forwarded to the related outbound sales transaction, especially in situations where you sell goods before you invoice the purchase of those goods. This is referred to as cost adjustment. Item costs are automatically adjusted when you post item transactions, but you can also adjust item costs manually. For more information, see [Adjust Item Costs](inventory-how-adjust-item-costs.md).

## To post inventory costs manually
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") ico, enter **Post Inventory Cost to G/L**, and then choose the related link.
2. Post inventory costs to the general ledger manually by running the batch job. When you run this batch job, general ledger entries are created on the basis of value entries. You can post the entries so that they are summarized per posting group.

> [!NOTE]  
> When you run this batch job, you might encounter errors having to do with missing setup or incompatible dimension setup. If the batch job encounters errors in the dimension setup, it overrides these errors and uses the dimensions of the value entry. For any other errors, the batch job skips posting the value entries and lists them at the end of the report in a section titled “Skipped Entries.” To post these entries, you must fix the errors.

To see a list of errors before running the posting batch job, you can run the **Post Invt. Cost to G/L - Test** report. The test report lists all the errors encountered during a test posting. You can then fix the errors, and run the inventory cost posting batch job without skipping any entries.

If you would like to simply get an overview of what values could be posted to the general ledger without actually performing the posting, you can run the **Post Inventory Cost to G/L** batch job without actually posting the values to the general ledger. You do this by clearing the check mark from the **Post** field on the request page. This way, when you run the batch job, the report is produced showing the values that are ready to be posted to the general ledger, but they are not posted.

## To audit the reconciliation between the inventory ledger and the general ledger
The **Inventory - G/L Reconciliation** page provides the following:

- Exposes reconciliation differences by comparing what is recorded in G/L and what is recorded in the inventory ledger (value entries).
- Displays unreconciled cost amounts in the value entries in the inventory ledger as if they were mapped to corresponding inventory-related accounts in G/L and compares those to the totals actually recorded in the same accounts in G/L.
- Reflects the double entry structure of G/L by visually presenting data as such. For example, a COGS entry has a corresponding inventory entry.
- Lets users drill down and see the entries that make up the cost amounts.
- Includes filters to narrow the analysis by date, item, and location.
- Explains reasons for reconciliation differences in informative messages.


The **Name** column on the far left in the grid lists the various G/L account types that are associated with inventory.

The **Inventory**, **Inventory (Interim)**, and **WIP Inventory** columns show the invoiced, non-invoiced, and WIP totals of each G/L account type. These are calculated from value entries, that is, they are projected onto the G/L account types where they will end when they are eventually posted to G/L.

The **Total** column shows the sum (in bold font) of the value entry amounts in the three inventory columns.

The **G/L Total** column shows the amounts (in bold font) for each G/L account type that exists in G/L. These are calculated from G/L entries, that is, they represent inventory costs already posted to G/L.

The **Difference** column represents the difference between the value in the **G/L Total** and **Total** fields.

In the top of the **Inventory - G/L Reconciliation** page, you can enter filters to limit, for example, the period of time for which you want information.

If you select the **Show Warning** check box and if there are any discrepancies between the inventory totals and G/L totals, application shows messages in the **Warning** field of the grid that explain the discrepancy. If you choose the Warning field, application gives you more information on what the warning means.

When you have entered all relevant filters, choose the **Show Matrix** action. The data is calculated and the matrix page appears.

On the far left column in the grid, you see the various general ledger account types that are associated with inventory. The grid then shows the invoiced, non-invoiced (interim), and WIP inventory totals for each of these account types. These totals are calculated from the value entries.

The next columns show the totals for the same account types calculated from the general ledger entries.

Choose the  amount in any of the total fields to see the inventory report entries that were used to calculate the totals. For inventory totals, the inventory report entries are the sums of the value entries for the items. For the G/L totals, the inventory report entries are the sums from the general ledger entries.

## See Also  
[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)    
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[General Business Functionality](ui-across-business-areas.md)
