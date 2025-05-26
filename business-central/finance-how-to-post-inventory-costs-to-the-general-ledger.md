---
title: Reconcile inventory costs with the general ledger
description: At the end of accounting periods a sequence of cost control and auditing tasks must be performed to report a correct and balanced inventory value. 
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: warehouse, stock
ms.search.form: 9297,
ms.date: 07/31/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Reconcile inventory costs with the general ledger

When you post inventory transactions, such as sales shipments, purchase invoices, or inventory adjustments, the changed item costs are recorded in item value entries. To reflect this change of inventory value in your financial books, the inventory costs also need to be posted to the related inventory accounts in the general ledger, such as the inventory account, adjustment account, and COGS account in the general ledger.

Unless you have selected the **Automatic Cost Posting** check box in the **Inventory Setup** window, inventory costs aren't recorded dynamically in the general ledger, and COGS isn't calculated with a sale. Therefore, you must post to the general ledger manually by running the **Post Inventory Cost to G/L** batch job to update the general ledger and potentially print a report of the value entries that are posted.

> [!IMPORTANT]  
> Before you use this batch job, you should run the **Adjust Cost - Item Entries** batch job. This ensures that, when you run this batch job, the costs that will be posted to the general ledger are up to date. This is referred to as cost adjustment. For more information, see [Adjust Item Costs](inventory-how-adjust-item-costs.md).

## To post inventory costs manually

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Post Inventory Cost to G/L**, and then choose the related link.

2. Post inventory costs to the general ledger manually by running the batch job. When you run this batch job, general ledger entries are created on the basis of value entries. To calculate the value to post, it uses the difference between the **Cost Amount (Actual)** field and the **Cost Posted to G/L** field in the value entries. If you have selected the **Expected Cost Posting to G/L** checkbox on the **Inventory Setup** page, the batch job also posts the difference between the **Cost Amount (Expected)** field and the **Exp. Cost Posted to G/L** field to interim accounts in the general ledger. You can post the entries so that they are summarized per posting group.

|Option  |Description  |
|--------------|---------|
|**Posting Method**|The batch job can either post inventory value to the general ledger per posting group or per posted entry. If you post per entry, you achieve a detailed specification of how the inventory affects the general ledger, but you also get numerous G/L entries. If you post per posting group, the batch job creates a general ledger entry per posting date per posting group combination. This means that a general ledger entry is created for each combination of posting date, general business posting group, general product posting group, inventory posting group, and location code. In addition, the batch job creates separate general ledger entries for costs with different signs.|
|**Document No.**|In this field, you can enter a document number if you have chosen the *Post per Inventory Posting Group* option. The document number appears on posted entries.|
|**Post**|Select this field if you want the batch job to post to the general ledger automatically. If you don't choose to post the inventory cost to G/L, the batch job will only print a test report showing the values that can be posted to the general ledger, and on the report will appear: **Test Report (not posted)**.|

> [!NOTE]  
> When you run this batch job, you might encounter errors having to do with missing setup or incompatible dimension setup. If the batch job encounters errors in the dimension setup, it overrides these errors and uses the dimensions of the value entry. For any other errors, the batch job skips posting the value entries and lists them at the end of the report in a section titled “Skipped Entries.” To post these entries, you must fix the errors.
> For example if you have not selected the **Expected Cost Posting to G/L** check box in the **Inventory Setup** window, then the last section of the report will list value entries that are skipped because they represent expected costs.

To see a list of errors before running the posting batch job, you can run the **Post Invt. Cost to G/L - Test** report. The test report lists all the errors encountered during a test posting. You can then fix the errors, and run the inventory cost posting batch job without skipping any entries.

If you would like to get an overview of what values could be posted to the general ledger without actually performing the posting, you can run the **Post Inventory Cost to G/L** batch job without actually posting the values to the general ledger. You do this by clearing the check mark from the **Post** field on the request page. This way, when you run the batch job, the report is produced showing the values that are ready to be posted to the general ledger, but they aren't posted.

## To audit the reconciliation between the inventory ledger and the general ledger

The **Inventory - G/L Reconciliation** page provides the following:

- Exposes reconciliation differences by comparing what is recorded in G/L and what is recorded in the inventory ledger (value entries).
- Displays unreconciled cost amounts in the value entries in the inventory ledger as if they were mapped to corresponding inventory-related accounts in G/L and compares those to the totals recorded in the same accounts in G/L.
- Reflects the double entry structure of G/L by visually presenting data as such. For example, a COGS entry has a corresponding inventory entry.
- Lets users drill down and see the entries that make up the cost amounts.
- Includes filters to narrow the analysis by date, item, and location.
- Explains reasons for reconciliation differences in informative messages.


The **Name** column on the far left in the grid lists the various G/L account types that are associated with inventory.

The **Inventory**, **Inventory (Interim)**, and **WIP Inventory** columns show the invoiced, non-invoiced, and WIP totals of each G/L account type. These are calculated from value entries, that is, they're projected onto the G/L account types where they'll end when they're eventually posted to G/L.

The **Total** column shows the sum (in bold font) of the value entry amounts in the three inventory columns.

The **G/L Total** column shows the amounts (in bold font) for each G/L account type that exists in G/L. These are calculated from G/L entries, that is, they represent inventory costs already posted to G/L.

The **Difference** column represents the difference between the value in the **G/L Total** and **Total** fields.

In the top of the **Inventory - G/L Reconciliation** page, you can enter filters to limit, for example, the period of time for which you want information.

If you select the **Show Warning** check box and if there are any discrepancies between the inventory totals and G/L totals, application shows messages in the **Warning** field of the grid that explain the discrepancy. If you choose the Warning field, application gives you more information on what the warning means.

When you have entered all relevant filters, choose the **Show Matrix** action. The data is calculated and the matrix page appears.

On the far left column in the grid, you see the various general ledger account types that are associated with inventory. The grid then shows the invoiced, non-invoiced (interim), and WIP inventory totals for each of these account types. These totals are calculated from the value entries.

The next columns show the totals for the same account types calculated from the general ledger entries.

Choose the  amount in any of the total fields to see the inventory report entries that were used to calculate the totals. For inventory totals, the inventory report entries are the sums of the value entries for the items. For the G/L totals, the inventory report entries are the sums from the general ledger entries.

## Reporting Costs and Reconciling with the General Ledger
Other reports, tracing functions, and a special reconciliation tool are available to the auditor or controller responsible for reporting a correct and balanced inventory value to the finance department.

The following table describes them.    

|**To**|**See**|  
|------------|-------------|  
|View the inventory value of selected items, including information about the quantities and values of increases and decreases in inventory over a selected period.|**Inventory Valuation** report|  
|View the inventory value of selected production orders in your WIP (work in process) inventory, such as the quantities and values of consumption, capacity usage, and output in ongoing production orders.|**Inventory Valuation - WIP** report|  
|View the inventory value of selected items, including their actual and expected cost on the date specified.|**Invt. Valuation - Cost Spec.** report|  
|Use a report to analyze the reasons for cost variances or to gain insight into the cost shares of sold items (COGS).|**Cost Shares Breakdown** report|  

## Related information  
[Managing Inventory Costs](finance-manage-inventory-costs.md)    
[Purchasing](purchasing-manage-purchasing.md)    
[Sales](sales-manage-sales.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    
[General Business Functionality](ui-across-business-areas.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
