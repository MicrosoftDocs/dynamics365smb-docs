---
author: brentholtorf
ms.topic: include
ms.date: 10/24/2024
ms.author: kepontop
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

The following table describes some of the key reports in fixed asset management.

| To... | Open in [!INCLUDE [prod_short](prod_short.md)] (CTRL+select) | Learn more | ID |
|-------|------------| ------------|----|
| [!INCLUDE[report-4412-scenario](../includes/report-4412-scenario-include.md)] | [Fixed Asset Analysis Excel](https://businesscentral.dynamics.com?report=4412) | [About Fixed Asset Analysis Excel](../reports/report-4412.md) | 4412 |
| [!INCLUDE[report-4411-scenario](../includes/report-4411-scenario-include.md)] | [Fixed Asset Details Excel](https://businesscentral.dynamics.com?report=4411) | [About Fixed Asset Details Excel](../reports/report-4411.md) | 4411 |
| [!INCLUDE[report-4413-scenario](../includes/report-4413-scenario-include.md)] | [Fixed Asset Projected Value Excel](https://businesscentral.dynamics.com?report=4413) | [About Fixed Asset Projected Value Excel](../reports/report-4413.md) | 4413 |
| [!INCLUDE[report-5601-scenario](../includes/report-5601-scenario-include.md)] | [Fixed Asset List](https://businesscentral.dynamics.com?report=5601) | [About Fixed Asset List](../reports/report-5601.md) | 5601 |
| [!INCLUDE[report-5602-scenario](../includes/report-5602-scenario-include.md)] | [Fixed Asset Journal - Test](https://businesscentral.dynamics.com?report=5602) | [About Fixed Asset Journal - Test](../reports/report-5602.md) | 5602 |
| [!INCLUDE[report-5603-scenario](../includes/report-5603-scenario-include.md)] | [Fixed Asset Register](https://businesscentral.dynamics.com?report=5603) | [About Fixed Asset Register](../reports/report-5603.md) | 5603 |
| [!INCLUDE[report-5605-scenario](../includes/report-5605-scenario-include.md)] | [Fixed Asset Book Value 01](https://businesscentral.dynamics.com?report=5605) | [About Fixed Asset Book Value 01](../reports/report-5605.md) | 5605 |
| [!INCLUDE[report-5606-scenario](../includes/report-5606-scenario-include.md)] | [Fixed Asset Book Value 02](https://businesscentral.dynamics.com?report=5606) | [About Fixed Asset Book Value 02](../reports/report-5606.md) | 5606 |
| [!INCLUDE[report-5608-scenario](../includes/report-5608-scenario-include.md)] | [Fixed Asset - Acquisition List](https://businesscentral.dynamics.com?report=5608) | [About Fixed Asset - Acquisition List](../reports/report-5608.md) | 5608 |
| [!INCLUDE[report-5610-scenario](../includes/report-5610-scenario-include.md)] | [Fixed Asset G/L Analysis](https://businesscentral.dynamics.com?report=5610) | [About Fixed Asset G/L Analysis](../reports/report-5610.md) | 5610 |
| [!INCLUDE[report-5611-scenario](../includes/report-5611-scenario-include.md)] | [FA Posting Group - Net Change Report](https://businesscentral.dynamics.com?report=5611) | [About FA Posting Group - Net Change Report](../reports/report-5611.md) | 5611 |
| [!INCLUDE[report-5636-scenario](../includes/report-5636-scenario-include.md)] | [Fixed Asset Document Nos.](https://businesscentral.dynamics.com?report=5636) | [About Fixed Asset Document Nos.](../reports/report-5636.md) | 5636 |
| This is a legacy report for fixed assets. Refer to the report documentation for alternatives. | [Fixed Asset Analysis](https://businesscentral.dynamics.com?report=5600) | [About Fixed Asset Analysis (legacy)](../reports/report-5600.md) | 5600 |
| This is a legacy report for fixed assets. Refer to the report documentation for alternatives. | [Fixed Asset Details](https://businesscentral.dynamics.com?report=5604) | [About Fixed Asset (FA) Details (legacy)](../reports/report-5604.md) | 5604 |
| This is a legacy report for fixed assets. Refer to the report documentation for alternatives. | [Fixed Asset Projected Value](https://businesscentral.dynamics.com?report=5607) | [About Fixed Asset Projected Value (legacy)](../reports/report-5607.md) | 5607 |

<!-- remove after 2025-01-01

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
 -->
