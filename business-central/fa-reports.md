---
title: Fixed Assets Reports and Analytics
description: See which reports and analytics are available in the standard version of Business Central so that you can keep track of your fixed assets.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: reporting
ms.date: 07/13/2021
ms.author: edupont

---
# Fixed Assets Reports and Analytics in Business Central

To help you manage your fixed assets in [!INCLUDE [prod_short](includes/prod_short.md)], standard reports and analytics are built in. It moves beyond traditional reporting constraints to help you efficiently design various types of reports.  

## Reports

The following table describes some of the key reports in fixed assets reporting.

| Report | Object ID | Description |
|--|--|--|
| **Fixed Asset List** | 5601 | Shows the list of fixed asset and their setup info for a given depreciation book. |
| **Fixed Asset - Acquisition List** | 5608 | List all assets acquired within a given date range. You can also include fixed assets that are created but not yet acquired. |
| **Fixed Asset Details** | 5604 | Shows the fixed asset ledger entries for fixed assets. |
| **Fixed Asset Analysis** | 5600 | An analysis report where you can specify two date columns and three data columns to see in the report. For example, to generate a report to use for reconciling with the general ledger, add columns for acquisition cost at ending date, depreciation at ending date, and book value at ending date. A check report could have acquisitions/net change, write-down/net change, and Appreciation/net change, so every change to fixed asset can be checked if necessary. If you select the **Budget Report** field and specify an ending date in the future, the report will calculate the future depreciation and can give estimates for future depreciation and book values, if you selected those fields as report columns. |
| **Fixed Asset Projected Value** | 5607 | Shows the projected depreciation amounts and book value for a future period for assets. The report is useful when you are using different depreciation methods for your assets and want to estimate next year's depreciation, for example. Use the report to create the budget amounts for depreciation by selecting a budget and the **Copy to G/L Budget** field. |
| **Fixed Asset Book Value 01** | 5605 | Shows detailed information about acquisition cost, depreciation value, and book value for both individual assets and groups of assets. For each of these three amount types, amounts are calculated at the beginning and at the end of a specified period and for the period itself. If you select the **Budget Report** field, the report will calculate the expected depreciation for the period. Enter a *group type* if you want the report to group the fixed assets and print group totals. For example, if you have set up six FA classes, select the *FA Class* option to have group totals printed for each of the six class codes.|
| **Fixed Asset Book Value 02** | 5606 |Shows the breakdown of fixed asset book value by changes in acquisition, depreciation, and appreciation within the period with a further breakdown by additions and disposals within the period. Use this report to describe the changes in fixed assets for a given period when many different changes occur across the grouping of fixed assets. If you select the **Budget Report** field, the report will calculate the expected depreciation for the period. Enter a *group type* if you want the report to group the fixed assets and print group totals. For example, if you have set up six FA classes, select the *FA Class* option to have group totals printed for each of the six class codes. |
| **Fixed Asset G/L Analysis**| 5610 |Shows an analysis of your fixed assets (FA) with various types of data for individual assets and/or groups of assets. On the Fixed Assets FastTab, you can set filters if you want the report to include only certain fixed assets. On the Options FastTab, tailor the report to meet your specific needs. The report is similar to the **Fixed Asset Analysis** report, but specifically for reconciling to the general ledger and specifically for validating the disposal entries. The report assumes that you know the G/L accounts that are specified in the  posting setup. |
| **Fixed Asset Register** |5603  |Shows posted fixed asset ledger entries that are sorted and divided by register number. You can determine which registers' entries are shown by setting a filter. It is important to set a filter; otherwise, the report may show a very large amount of information. |

## See also

[Analyzing Financial Statements in Microsoft Excel](finance-analyze-excel.md)  
[Working with Dimensions](finance-dimensions.md)  
[Managing Fixed Assets](fa-manage.md)  
[Local Functionality Overview](about-localization.md)  
[Accountant Experiences in [!INCLUDE[prod_long](includes/prod_long.md)]](finance-accounting.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
