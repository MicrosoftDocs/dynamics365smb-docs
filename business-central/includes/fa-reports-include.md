---
author: brentholtorf
ms.topic: include
ms.date: 04/01/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---



The following table describes some of the key reports in fixed assets management.

| To... | Open in [!INCLUDE [prod_short](prod_short.md)] (CTRL+select) | Learn more | ID | 
|-------|------------| ------------|----|
| [!INCLUDE[report-5600-scenario](../includes/report-5600-scenario-include.md)] | [Fixed Asset Analysis](https://businesscentral.dynamics.com?report=5600) | [About *Fixed Asset AnalysisInventory - Transaction Detail*](../reports/report-5600.md) | 5600 |




<!-- 

| | [Fixed Asset List](https://businesscentral.dynamics.com?report=5601) | [About *Fixed Asset ListInventory - Transaction Detail*](../reports/report-5601.md) | 5601 |
| | [Fixed Asset Register](https://businesscentral.dynamics.com?report=5603) | [About *Fixed Asset RegisterInventory - Transaction Detail*](../reports/report-5603.md) | 5603 |
| | [Fixed Asset Details](https://businesscentral.dynamics.com?report=5604) | [About *Fixed Asset DetailsInventory - Transaction Detail*](../reports/report-5604.md) | 5604 |
| | [Fixed Asset Book Value 01](https://businesscentral.dynamics.com?report=5605) | [About *Fixed Asset Book Value 01Inventory - Transaction Detail*](../reports/report-5605.md) | 5605 |
| | [Fixed Asset Book Value 02](https://businesscentral.dynamics.com?report=5606) | [About *Fixed Asset Book Value 02Inventory - Transaction Detail*](../reports/report-5606.md) | 5606 |
| | [Fixed Asset Projected Value](https://businesscentral.dynamics.com?report=5607) | [About *Fixed Asset Projected ValueInventory - Transaction Detail*](../reports/report-5607.md) | 5607 |
| | [Fixed Asset - Acquisition List](https://businesscentral.dynamics.com?report=5608) | [About *Fixed Asset - Acquisition ListInventory - Transaction Detail*](../reports/report-5608.md) | 5608 |
| | [Fixed Asset G/L Analysis](https://businesscentral.dynamics.com?report=5610) | [About *Fixed Asset G/L AnalysisInventory - Transaction Detail*$../reports/report-5610.md) | 5610 |


5600
About Fixed Asset Analysis
Fixed Asset Analysis Report is a flexible reporting option that provides a comprehensive examination of an organization's fixed assets, such as property, plant, and equipment (PP&E), for different purposes. If the purpose is to reconcile asset values with GL then fields like acquisition, depreciation can be selected. If the purpose is about reviewing net value along with write down value, users can use this report accordingly by choosing the relevant amount fields and amount fields for multiple periods.

5601
The Fixed Asset List report provides a comprehensive listing of all fixed assets owned by an organization at a specific point in time. This report is crucial for asset management, financial reporting, and compliance purposes.

5603
About Fixed Asset Register
The Fixed Asset Register report is a comprehensive and structured document that serves as the central repository of all fixed asset transactions done by an organization.

5604
About Fixed Asset Details
The Fixed Asset Details report provides a comprehensive overview of all relevant information pertaining to each fixed asset owned by an organization. This report serves as a detailed transaction information and reference tool for asset management.

5605
About Fixed Asset Book Value 01
The Fixed Asset - Book Value 01 report helps obtain detailed information for different groups of assets about acquisition cost, depreciation value and book value. The detailed information are also summarized at a group level if needed. The report shows the output structured over multiple columns.

5606
About Fixed Asset Book Value 02
The Fixed Asset Book Value 02 report is useful when the user wants to view the movement in valuation of assets over a period time. There is further breakdown of values under additions and disposals during the period , further grouped under classes/subclasses if needed.

5607
About Fixed Asset Projected Value
Fixed Asset Projected Value Report is a detailed analysis that forecasts the future value of an organization's fixed assets over a specified period. This is specially useful where there are multiple depreciation methods and there is need to review the projected values of depreciation.

5608
About Fixed Asset Acquisition List
The Fixed Asset Acquisition List report is a detailed accounting document that provides an organized summary of all fixed assets acquired by an organization during a specific period. This report is essential for tracking new additions to the asset base and ensuring accurate financial reporting.

5610
About Fixed Asset G/L Analysis
The Fixed Assets G/L Analysis report is essential for financial management and reporting, offering detailed insights into the accounting treatment and reconciliation of subledger with the general ledger mainly validating the disposal entries. Structurally it is similar to FA Analysis report but this one is focused on GL reconciliation purpose. 
-->


## The old way
The following table describes some of the key reports in fixed assets reporting.

| Report | Description | Id | 
|--|--|--|
| [Fixed Asset List](https://businesscentral.dynamics.com?report=5601)| Shows the list of fixed asset and their setup info for a given depreciation book. |5601 |
| [Fixed Asset - Acquisition List](https://businesscentral.dynamics.com?report=5608) |  List all assets acquired within a given date range. You can also include fixed assets that are created but not yet acquired. |5608 |
| [Fixed Asset Details](https://businesscentral.dynamics.com?report=5604)| Shows the fixed asset ledger entries for fixed assets. |5604 |
| [Fixed Asset Analysis](https://businesscentral.dynamics.com?report=5600)| An analysis report where you can specify two date columns and three data columns to see in the report. For example, to generate a report to use for reconciling with the general ledger, add columns for acquisition cost at ending date, depreciation at ending date, and book value at ending date. A check report could have acquisitions/net change, write-down/net change, and Appreciation/net change, so every change to fixed asset can be checked if necessary. If you select the **Budget Report** field and specify an ending date in the future, the report will calculate the future depreciation and can give estimates for future depreciation and book values, if you selected those fields as report columns. |5600|
| [Fixed Asset Projected Value](https://businesscentral.dynamics.com?report=5607)| Shows the projected depreciation amounts and book value for a future period for assets. The report is useful when you are using different depreciation methods for your assets and want to estimate next year's depreciation, for example. Use the report to create the budget amounts for depreciation by selecting a budget and the **Copy to G/L Budget** field. |5607 |
| [Fixed Asset Book Value 01](https://businesscentral.dynamics.com?report=5605)|Shows detailed information about acquisition cost, depreciation value, and book value for both individual assets and groups of assets. For each of these three amount types, amounts are calculated at the beginning and at the end of a specified period and for the period itself. If you select the **Budget Report** field, the report will calculate the expected depreciation for the period. Enter a *group type* if you want the report to group the fixed assets and print group totals. For example, if you have set up six FA classes, select the *FA Class* option to have group totals printed for each of the six class codes.|5605|
| [Fixed Asset Book Value 02](https://businesscentral.dynamics.com?report=5606)|Shows the breakdown of fixed asset book value by changes in acquisition, depreciation, and appreciation within the period with a further breakdown by additions and disposals within the period. Use this report to describe the changes in fixed assets for a given period when many different changes occur across the grouping of fixed assets. If you select the **Budget Report** field, the report will calculate the expected depreciation for the period. Enter a *group type* if you want the report to group the fixed assets and print group totals. For example, if you have set up six FA classes, select the *FA Class* option to have group totals printed for each of the six class codes. |5606|
| [Fixed Asset G/L Analysis](https://businesscentral.dynamics.com?report=5610)|Shows an analysis of your fixed assets (FA) with various types of data for individual assets and/or groups of assets. On the Fixed Assets FastTab, you can set filters if you want the report to include only certain fixed assets. On the Options FastTab, tailor the report to meet your specific needs. The report is similar to the **Fixed Asset Analysis** report, but specifically for reconciling to the general ledger and specifically for validating the disposal entries. The report assumes that you know the G/L accounts that are specified in the  posting setup. | 5610 |
| [Fixed Asset Register](https://businesscentral.dynamics.com?report=5603) |Shows posted fixed asset ledger entries that are sorted and divided by register number. You can determine which registers' entries are shown by setting a filter. It is important to set a filter; otherwise, the report may show a very large amount of information. |5603  |
