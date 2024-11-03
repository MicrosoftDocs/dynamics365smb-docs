---
author: brentholtorf
ms.topic: include
ms.date: 10/24/2024
ms.author: kepontop
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

The following table describes some of the key reports in fixed assets management.

| To... | Open in [!INCLUDE [prod_short](prod_short.md)] (CTRL+select) | Learn more | ID | 
|-------|------------| ------------|----|
| [!INCLUDE[report-5600-scenario](../includes/report-5600-scenario-include.md)] | [Fixed Asset Analysis](https://businesscentral.dynamics.com?report=5600) | [About *Fixed Asset Analysis*](../reports/report-5600.md) | 5600 |
| [!INCLUDE[report-5601-scenario](../includes/report-5601-scenario-include.md)] | [Fixed Asset List](https://businesscentral.dynamics.com?report=5601) | [About *Fixed Asset List*](../reports/report-5601.md) | 5601 |
| [!INCLUDE[report-5603-scenario](../includes/report-5603-scenario-include.md)] | [Fixed Asset Register](https://businesscentral.dynamics.com?report=5603) | [About *Fixed Asset Register*](../reports/report-5603.md) | 5603 |
| [!INCLUDE[report-5604-scenario](../includes/report-5604-scenario-include.md)] | [Fixed Asset Details](https://businesscentral.dynamics.com?report=5604) | [About *Fixed Asset Details*](../reports/report-5604.md) | 5604 |
| [!INCLUDE[report-5605-scenario](../includes/report-5605-scenario-include.md)] | [Fixed Asset Book Value 01](https://businesscentral.dynamics.com?report=5605) | [About *Fixed Asset Book Value 01*](../reports/report-5605.md) | 5605 |
| [!INCLUDE[report-5606-scenario](../includes/report-5606-scenario-include.md)] | [Fixed Asset Book Value 02](https://businesscentral.dynamics.com?report=5606) | [About *Fixed Asset Book Value 02*](../reports/report-5606.md) | 5606 |
| [!INCLUDE[report-5607-scenario](../includes/report-5607-scenario-include.md)] | [Fixed Asset Projected Value](https://businesscentral.dynamics.com?report=5607) | [About *Fixed Asset Projected Value*](../reports/report-5607.md) | 5607 |
| [!INCLUDE[report-5608-scenario](../includes/report-5608-scenario-include.md)] | [Fixed Asset - Acquisition List](https://businesscentral.dynamics.com?report=5608) | [About *Fixed Asset - Acquisition List*](../reports/report-5608.md) | 5608 |
| [!INCLUDE[report-5610-scenario](../includes/report-5610-scenario-include.md)] | [Fixed Asset G/L Analysis](https://businesscentral.dynamics.com?report=5610) | [About *Fixed Asset G/L Analysis*](../reports/report-5610.md) | 5610 |
| [!INCLUDE[report-5611-scenario](../includes/report-5611-scenario-include.md)] | [FA Posting Group - Net Change Report](https://businesscentral.dynamics.com?report=5611) | [About *FA Posting Group - Net Change Report*](../reports/report-5611.md) | 5611 |
| [!INCLUDE[report-5620-scenario](../includes/report-5620-scenario-include.md)] | [Insurance - Analysis](https://businesscentral.dynamics.com?report=5620) | [About *Insurance - Analysis*](../reports/report-5620.md) | 5620 |
| [!INCLUDE[report-5621-scenario](../includes/report-5621-scenario-include.md)] | [Insurance - List](https://businesscentral.dynamics.com?report=5621) | [About *Insurance - List*](../reports/report-5621.md) | 5621 |
| [!INCLUDE[report-5625-scenario](../includes/report-5625-scenario-include.md)] | [Insurance - Tot. Value Insured](https://businesscentral.dynamics.com?report=5625) | [About *Insurance - Tot. Value Insured*](../reports/report-5625.md) | 5625 |


<!-- TODO: Add articles for these

https://learn.microsoft.com/en-us/dynamics365/business-central/fa-how-insure#to-monitor-insurance-coverage


5623	Insurance Register
Shows posted insurance ledger entries that are sorted and divided by register number. You can determine which registers' entries are shown by setting a filter. It is important to set a filter; otherwise, the report may show a very large amount of information.

The report can be defined so that it functions as a part of the posting process; that is, it can be printed when you post. To print the register when the journal is posted, on the Action Pane, in the Process actions group, choose Post and Print in the journal. The report can be used either for documenting the posted entries or for auditing.



5624	Insurance - Coverage Details
hows the individual fixed assets that are linked to each insurance policy. For each insurance policy, the report shows one or more amounts for each asset. These are the amounts that need insurance coverage. These amounts can differ from the actual insurance policy's coverage.


5626 
Insurance - Uninsured FAs
To check whether you forgot to assign a fixed asset to an insurance policy, you can print or preview the Insurance - Uninsured FAs report. This report displays fixed assets for which amounts aren't posted to the insurance coverage ledger.


5622
Insurance Journal - Test
Shows the journal lines in an insurance journal. You can use the report to have the lines checked before you post the journal.

If you run the report from the Actions tab and post in a journal window, the report automatically filters by the current journal template and journal batch names. In this case, you do not have to enter anything on the tabs. If you run the report from the report list, you can define what is to be included in it by setting filters.


5636
Shows a list of fixed asset ledger entries, sorted by document type and number. The report includes the document type, document number, posting date and source code of the entry, the description and number of the fixed asset, and so on. A warning appears when there is a gap in the number series or the documents were not posted in document-number order.


5602
Shows the journal lines in an FA journal. You can use the report to have the lines checked before you post the journal.

If you run the test report from a journal window, the report is automatically filtered by the current journal template and journal batch names. In this case, you do not have to enter anything on the FastTabs.



5630
Maintenance - Analysis
Shows detailed maintenance expenses for fixed assets. The report can show maintenance expenses for fixed assets for different time periods broken down by maintenance types or other categories such as, fixed asset class.

Options
Field	Description
Depreciation Book

Select the depreciation book code for the depreciation book to be included in the report.

Date Selection

Select the date options that can be used in the report. You can choose between the posting date and the fixed asset posting date.

Starting Date

Enter the first date to be included in the report.

Ending Date

Enter the last date to be included in the report.

Amount Field 1 , Amount Field 2, Amount Field 3

The report has three amount fields that can show maintenance amounts broken down by different maintenance types. Select the maintenance code for the maintenance type you want to include in the report.

Period 1 , Period 2, Period 3

Select one of the options: Before Starting Date, Net Change or at Ending Date. Net Change is the period between the starting and ending date. The selected option determines how the program calculates the maintenance amounts shown in the report.

Group Totals

Select if you want the report to group fixed assets and print totals using the category defined in this field. For example, maintenance expenses for fixed assets can be shown for each fixed asset class.

Print per Fixed Asset

Select if you want the report to show amounts for each fixed asset.



5634
Maintenance - Details
Shows detailed information about the maintenance ledger entries that have been posted to each fixed asset for the depreciation book that you specify in the report.

Options
Field	Description
Depreciation Book
Select the depreciation book code for the depreciation book to be included in the report.

New Page per FA
Select if you want the report to print data for each fixed asset on a separate page.

Include Reversed Entries
Select if you want to include reversed entries in the report.



5635
Maintenance - Next Service
Shows each fixed asset and shows the next date on which service and repairs are planned for each asset. For each asset, the program retrieves this date from the Next Service Date field on the fixed asset card.

Options
Field	Description
Starting Date
Enter the first date to be included in the report. Fixed assets that have a next service date before the date in this field will not be included.

Ending Date
Enter the last date to be included in the report. Fixed assets that have a next service date after the date in this field will not be included.



5633
Maintenance Register
Shows posted maintenance entries that are sorted and divided by register number. You can determine which registers' entries are shown by setting a filter. It is important to set a filter; otherwise, the report may show a very large amount of information.

The report can be defined so that it functions as a part of the posting process; that is, it can be printed when you post. To print the register when the journal is posted, on the Actions tab, in the Posting group, choose Post and Print in the journal. The report can be used for documenting the posted entries or for auditing.



Ad-hoc analysis:

To view insurance coverage ledger entries
You can view the entries that you made in the insurance coverage ledger.

Choose the Lightbulb that opens the Tell Me feature. icon, enter Insurance, and then choose the related link.
Select the relevant insurance policy, and then choose the Coverage Ledger Entries action. -->


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
