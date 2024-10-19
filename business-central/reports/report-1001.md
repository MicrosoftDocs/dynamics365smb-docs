---
title: Inventory Valuation (report)
description: Reconcile your inventory subledger to the inventory account(s) in the general ledger at the end of each period. Analyse the changes to expected costs posted during the period, and determine the value of inventory on hand for financial reporting.
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

The *Inventory Valuation* report shows beginning Inventory Balance (Quantity and Value) based on the Starting Date entered and Closing Inventory Balance based on the Ending Date entered. You can also see the decreases and increases in Quantity and Value within the period.

You can choose to include Expected Costs, which will reconcile to your Inventory (Interim) Accounts should you be using Expected Cost Posting.

The final column Cost Posted to G/L should be equal to the Ending Date Value column. If it is not, it is because Post Inventory Cost to G/L has not been run. 

Depending on your Inventory Posting Setup you can run the report with different Location Filters and compare Inventory Posting Group Totals to the related G/L Accounts to ensure that  your Inventory Subledger Balance to the General Ledger Inventory Balance Sheet Accounts.

To ensure that the report is up-to-date, it's recommended to run the Adjust Cost - Item Entries batch job prior to running this report.

**Note!** In the US, Canada, and Mexico, this report isn't available. Instead, use the localized version of Inventory Valuation (10139) report.


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

As a financial analyst, use the report to:
* Reconcile the inventory subledger to the inventory account(s) in the general ledger at the end of each period
* Analyze the changes to expected costs posted during the period and reconcile them with inventory accounts in the general ledger
* Determine the value of inventory on hand for financial reporting purposes

As an inventory manager, use the report to:
* Analyze the inventory valuation for selected items to ensure that they are being valued accurately
* Determine the value of inventory on hand for planning purposes
* Monitor changes to expected costs posted during the period to identify discrepancies

As a supply chain manager, use the report to:
* Analyze the inventory valuation for selected items to ensure that the company is maintaining adequate inventory levels
* Determine the value of inventory on hand for planning purposes, such as ensuring that there is enough inventory to meet customer demand
* Monitor changes to expected costs posted during the period to identify discrepancies and take corrective action if necessary


## Try the report

Try the report here: [Inventory Valuation](https://businesscentral.dynamics.com?report=1001)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]


## See also

[Inventory and warehouse report overview](../reports/inventory-WMS-reports.md)   
[Ad-hoc analysis of inventory data](../ad-hoc-analysis-inventory.md)   
[Inventory analytics overview](../inventory-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]