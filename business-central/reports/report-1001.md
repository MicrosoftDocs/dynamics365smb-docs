---
title: Inventory Valuation (report)
description: Reconcile your inventory subledger with inventory accounts in the general ledger at the end of each period. Analyze the changes to expected costs posted during the period, and determine the value of on-hand inventory for financial reporting.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: Report_1001_Primary
ms.date: 10/18/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/18/2024
ai.usage: ai-assisted
---

# Inventory Valuation (report)

The **Inventory Valuation** report shows:

* The beginning balance (quantity and value) based on a starting date you specify.
* The closing balance based on an ending date you specify entered.

You can also find decreases and increases in quantity and value in the period.

If you use expected cost posting, you can choose to include expected costs that reconcile to your inventory (interim) accounts.

The value in the **Cost Posted to G/L** column should equal the value in the **Ending Date Value** column. If it isn't, it's because you didn't run **Post Inventory Cost to G/L**.

Depending on settings on the **Inventory Posting Setup** page, you can run the report with different location filters and compare inventory posting group totals to the related G/L Accounts to ensure that your inventory subledger balances with the general ledger inventory balance sheet accounts.

> [!TIP]
> To ensure that the report is up-to-date, we recommend that you run the **Adjust Cost - Item Entries** batch job before you generate this report.

> [!NOTE]
> This report isn't available in the US, Canada, and Mexico. Instead, use the localized version of the **Inventory Valuation** (10139) report.

## Use cases

<!-- 
Prompt

Below is a report in an ERP system. Provide 3-4 use cases for different personas working with inventory.
Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

## Report description
Displays inventory valuation for selected items in your inventory. The report also shows information about the value of increases and decreases in inventory over time.

The report will also print the expected cost of entries that have been posted as received or shipped, depending on whether you enable the Include Expected Cost toggle.

If you enable Include Expected Cost, the report groups entries and shows a group total of invoiced and expected costs for each Inventory Posting Group.

You can also narrow your report output with the Location and Variant Filters. However, as the report is built on top of a value entry, you can't use Bin Filter.

To ensure that the Inventory Valuation report is up-to-date, it's recommended to run the Adjust Cost - Item Entries batch job prior to running this report.

In the US, Canada, and Mexico, this report isn't available. Instead, use the localized version of Inventory Valuation (10139) report.

### What the report does
Displays beginning Inventory Balance (Quantity and Value) based on the Starting Date entered and Closing Inventory Balance based on the Ending Date entered. You can also see the decreases and increases in Quantity and Value within the period.

You can choose to include Expected Costs, which will reconcile to your Inventory (Interim) Accounts should you be using Expected Cost Posting.

The final column Cost Posted to G/L should be equal to the Ending Date Value column. If it is not, it is because Post Inventory Cost to G/L has not been run. 

Depending on your Inventory Posting Setup you can run the report with different Location Filters and compare Inventory Posting Group Totals to the related G/L Accounts to ensure that  your Inventory Subledger Balance to the General Ledger Inventory Balance Sheet Accounts.

To ensure that the report is up-to-date, it's recommended to run the Adjust Cost - Item Entries batch job prior to running this report.

In the US, Canada, and Mexico, this report isn't available. Instead, use the localized version of Inventory Valuation (10139) report.

### Use cases
Reconcile your inventory subledger to the inventory account(s) in the general ledger at the end of each period.

Analyse the changes to expected costs posted during the period, and determine the value of inventory on hand for financial reporting.

Please include your data sources and URLs

-->

Financial analysts use the report to:

* Reconcile the inventory subledger to inventory accounts in the general ledger at the end of each period.
* Analyze the changes to expected costs posted during the period and reconcile them with inventory accounts in the general ledger.
* Determine the value of on-hand inventory for financial reporting.

Inventory managers use the report to:

* Analyze inventory valuation for selected items to ensure that it's accurate.
* Determine the value of on-hand inventory for planning purposes.
* Monitor changes to expected costs posted during a period to identify discrepancies.

Supply chain managers use the report to:

* Analyze the inventory valuation for selected items to ensure adequate inventory levels.
* Determine the value of on-hand inventory for planning purposes. For example, to ensure that their inventory can meet customer demand.
* Monitor changes to expected costs posted during the period to identify discrepancies and take corrective action if necessary

## Try the report

Try the report here: [Inventory Valuation](https://businesscentral.dynamics.com?report=1001)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Inventory and warehouse report overview](../inventory-WMS-reports.md)   
[Ad hoc analysis of inventory data](../ad-hoc-analysis-inventory.md)   
[Inventory analytics overview](../inventory-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]