---
title: Manage Fixed Assets (contains video)
description: Learn about the fixed assets functionality and get an overview of how to work with and manage your fixed assets.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bnielse
ms.topic: conceptual
ms.search.keywords: machinery, buildings
ms.search.form: 5604, 5606, 5664, 5601, 5602, 5658, 5603, 5671, 5641, 5629, 5633, 5634, 5649, 5622, 5650
ms.date: 03/25/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Manage fixed assets

The Fixed Assets functionality in [!INCLUDE[prod_short](includes/prod_short.md)] provides an overview of your fixed assets and ensures correct periodic depreciation. It also enables you to keep track of your maintenance costs, manage insurance policies, post fixed asset transactions, and generate various reports and statistics.

## Video overview

The following video covers the basics of fixed assets:

> [!Video https://www.microsoft.com/en-us/videoplayer/embed/RE4AegS?rel=0]

## Initial setup of fixed assets

Before you can manage fixed assets, you must complete the following setups:
- Default values
- Fixed asset accounting
- Posting groups and types
- Allocation keys
- Fixed asset journals

For more information, see [Setting Up Fixed Assets](fa-setup.md).


## Fixed assets analytics 

This section describes the analytical tools you can use to get insights into your fixed assets data.

| To... | See |
| --- | --- |
| Learn about capabilities for analyzing fixed assets data. | [Fixed assets analytics overview](fa-analytics-overview.md) |
| Explore built-in fixed assets reports. | [Built-in fixed assets reports](fa-reports.md) |
| Monitor maintenance costs | [Monitor maintenance costs](fa-how-maintain.md#to-monitor-maintenance-costs)|
| Monitor insurance coverage | [Monitor insurance coverage](fa-how-insure.md#to-monitor-insurance-coverage) |
| View disposal ledger entries | [View disposal ledger entries](fa-how-dispose-retire.md#to-view-disposal-ledger-entries) |
| View projected disposal values | [View projected disposal values](fa-how-manage-budgets.md#to-view-projected-disposal-values) |


## Register fixed assets

For each fixed asset, you must set up a card containing information about the asset. You can set up buildings or production equipment as a main asset with a component list, and you can group them in various ways, such as by class, department, or location. Then you can begin to acquire, maintain, and sell the fixed assets. You can also set up budgeted assets. Budgeting lets you include any anticipated acquisitions and sales in reports.

| To  | See |
| --- | --- |
| Manage fixed asset budgets, budget acquisition costs, budget disposals of fixed assets, and budget depreciation. |[Manage Budgets for Fixed Assets](fa-how-manage-budgets.md) |
| Create fixed assets, assign depreciation methods, post acquisitions, salvage values, and print fixed asset lists. |[Acquire Fixed Assets](fa-how-acquire.md) |


## Set up depreciations for your fixed assets

To track fixed asset depreciations and other financial transactions for fixed assets, set up one or more depreciation books for each one. Depreciation is done by running a report to calculate periodic depreciation, filling in a journal with the resulting entries, and then posting the journal. [!INCLUDE[prod_short](includes/prod_short.md)] supports several depreciation methods. For more information, see [Depreciation Methods](fa-depreciation-methods.md). You can set up multiple depreciation books per fixed asset for different purposes, such as one for tax reporting and another for internal reporting.

| To  | See |
| --- | --- |
| Learn about different fixed asset depreciation methods. |[Depreciation Methods](fa-depreciation-methods.md) |
| Calculate depreciation, post depreciation, and analyze depreciation in fixed assets reports. |[Depreciate or Amortize Fixed Assets](fa-how-depreciate-amortize.md) |
| View changed depreciation book values | [View changed depreciation book values](fa-how-trans-split-combine.md#to-view-changed-depreciation-book-values-due-to-fixed-asset-reclassification) |
| Manually record fixed asset transactions on the **Fixed Asset G/L Journal** page or on the **Fixed Asset Journal** page, depending on whether the transactions are for financial reporting or for internal management. | [Set Up Fixed Asset Depreciation](fa-how-setup-depreciation.md) |


## Fixed assets maintenance and insurance

For each asset, you can record maintenance costs and the next service date. Tracking maintenance expenses can be important for budgeting purposes and deciding whether to replace a fixed asset. You can attach each fixed asset to one or more insurance policies, and verify that policy premiums align with the value of the assets.

| To  | See |
| --- | --- |
| Record service visits, post maintenance costs, and monitor maintenance costs. |[Maintain Fixed Assets](fa-how-maintain.md) |
| Monitor maintenance costs | [Monitor maintenance costs](fa-how-maintain.md#to-monitor-maintenance-costs)|
| Update insurance information, post acquisition costs to insurance policies, modify insurance coverage, view insurance statistics, and list insurance policies. |[Insure Fixed Assets](fa-how-insure.md) |
| Monitor insurance coverage | [Monitor insurance coverage](fa-how-insure.md#to-monitor-insurance-coverage) |


## Reclassify, transfer, split up/combine, adjust value, write-down, and dispose fixed assets

| To  | See |
| --- | --- |
| Reclassify fixed assets, transfer fixed assets to different locations, split up or combine assets. |[Transfer, Split, or Combine Fixed Assets](fa-how-trans-split-combine.md) |
| Adjust values of fixed assets, post appreciation, and post write-down transactions. |[Revalue Fixed Assets](fa-how-revalue.md) |
| Post disposal transactions, view disposal ledger entries, and post partial disposals. |[Dispose of or Retire Fixed Assets](fa-how-dispose-retire.md) |
| View disposal ledger entries | [View disposal ledger entries](fa-how-dispose-retire.md#to-view-disposal-ledger-entries) |
| View projected disposal values | [View projected disposal values](fa-how-manage-budgets.md#to-view-projected-disposal-values) |


## See also

[Setting Up Fixed Assets](fa-setup.md)  
[Fixed assets analytics overview](fa-analytics-overview.md)   
[Finance overview](finance.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Change Which Features are Displayed](ui-experiences.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]
