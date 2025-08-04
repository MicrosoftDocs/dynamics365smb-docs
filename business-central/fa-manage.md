---
title: Manage fixed assets
description: Learn about the fixed assets functionality and get an overview of how to work with and manage your fixed assets.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: machinery, buildings
ms.search.form: 5601_Primary, 5604, 5606, 5664, 5601, 5602, 5658, 5603, 5671, 5641, 5629, 5633, 5634, 5649, 5622, 5650
ms.date: 06/10/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Manage fixed assets

The fixed assets functionality in [!INCLUDE[prod_short](includes/prod_short.md)] provides an overview of your fixed assets and helps ensure that their depreciation is correct. It also helps you track maintenance costs, manage insurance policies, post fixed asset transactions, and generate various reports and statistics.

## What is a fixed asset?

Fixed assets differ from other items in your warehouse. A fixed asset, also known as a capital asset, is a tangible piece of property, plant, or equipment (PP&E) that you own or manage with the expectation that it will continue to help generate income. An asset is fixed when it’s an item that your business won’t consume, sell, or convert to cash within the next calendar year. Fixed assets are different than current assets, which are in cash or slated to be converted to cash within the next 12 months. Fixed assets also differ from your inventory, because inventory is typically consumed within a short time.

## Types of fixed assets

Businesses typically invest in a few types of fixed assets. Some examples are:

- Buildings and facilities
- Computer equipment and software
- Furniture and fixtures
- Machinery
- Vehicles

## Understanding fixed asset accounting

Fixed asset accounting means keeping precise financial records about your capital assets. These records include details about the five stages in an asset's lifecycle. After your initial purchase, each fixed asset’s lifecycle includes at least three of the following stages:

- Acquisition: You add a new fixed asset to your books.
- Depreciation: You record an asset's periodic decline in value, which you use a depreciation method to calculate. To learn more, go to [FA Depreciation Calculation](LocalFunctionality/India/FA_Depreciation.md).
- Revaluation: You record an assessment of the current fair market value of an asset. To learn more, go to [Revalue Fixed Assets](fa-how-revalue.md).
- Impairment: You record a reduction in value due to events or circumstances.
- Disposal: You sell, scrap, or use another way dispose of an asset at the end of its service life.

Audits are also included in the detailed checks of your company’s accounting records after closing the books for the financial year. Whether internal or external, audits are where you might notice inconsistencies or differences between your notes and the actual state of your assets. Audits promote transparency in your assets and accounting if you’re losing more money than anticipated.

## Video overview

The following video covers the basics of fixed assets:

> [!Video https://learn-video.azurefd.net/vod/player?id=32fa27be-9e9a-4637-bc9b-87eb994f5ae0]

## Initial setup of fixed assets

Before you can manage fixed assets, you must complete the following setups:

- Default values
- Fixed asset accounting
- Posting groups and types
- Allocation keys
- Fixed asset journals

To learn more, go to [Setting Up Fixed Assets](fa-setup.md).

## Fixed assets analytics

This section describes the analytical tools you can use to get insights into data about your fixed assets.

| To... | See |
| --- | --- |
| Learn about capabilities for analyzing data about fixed assets. | [Fixed assets analytics overview](fa-analytics-overview.md) |
| Do ad-hoc analysis of fixed assets data directly on list pages and queries. | [Ad-hoc analysis of fixed assets data](ad-hoc-analysis-fa.md) |
| Explore built-in reports for fixed assets. | [Built-in fixed assets reports](fa-reports.md) |
| Monitor maintenance costs. | [Monitor maintenance costs](fa-how-maintain.md#monitor-maintenance-costs)|
| Monitor insurance coverage. | [Monitor insurance coverage](fa-how-insure.md#to-monitor-insurance-coverage) |
| View disposal ledger entries. | [View disposal ledger entries](fa-how-dispose-retire.md#to-view-disposal-ledger-entries) |
| View projected disposal values. | [View projected disposal values](fa-how-manage-budgets.md#to-view-projected-disposal-values) |

## Register fixed assets

For each fixed asset, you must set up a card that contains information about them. For example, you can set up buildings or production equipment as main assets with a component list. You can group assets in various ways, such as by class, department, or location. Then you can acquire, maintain, and sell the fixed assets. You can also set up budgeted assets. Budgeting lets you include any anticipated acquisitions and sales in reports.

| To  | See |
| --- | --- |
| Manage fixed asset budgets, budget acquisition costs, budget disposals of fixed assets, and budget depreciation. |[Manage Budgets for Fixed Assets](fa-how-manage-budgets.md) |
| Create fixed assets, assign depreciation methods, post acquisitions, salvage values, and print fixed asset lists. |[Acquire Fixed Assets](fa-how-acquire.md) |

## Set up depreciations for your fixed assets

To track fixed asset depreciations and other financial transactions for fixed assets, set up one or more depreciation books for each one. There are a few steps to depreciate assets:

1. Run a report that calculates periodic depreciation.
1. Fill in a journal with the resulting entries.
1. Post the journal.

[!INCLUDE[prod_short](includes/prod_short.md)] supports several depreciation methods. To learn more, go to [Depreciation Methods](fa-depreciation-methods.md). You can set up multiple depreciation books for each fixed asset for different purposes, such as one for tax reporting and another for internal reporting.

| To  | See |
| --- | --- |
| Learn about different fixed asset depreciation methods. |[Depreciation Methods](fa-depreciation-methods.md) |
| Calculate depreciation, post depreciation, and analyze depreciation in fixed assets reports. |[Depreciate or Amortize Fixed Assets](fa-how-depreciate-amortize.md) |
| View changed depreciation book values. | [View changed depreciation book values](fa-how-trans-split-combine.md#to-view-changed-depreciation-book-values-due-to-fixed-asset-reclassification) |
| Manually record fixed asset transactions on the **Fixed Asset G/L Journal** page or on the **Fixed Asset Journal** page, depending on whether the transactions are for financial reporting or for internal management. | [Set Up Fixed Asset Depreciation](fa-how-setup-depreciation.md) |

## Fixed assets maintenance and insurance

You can record maintenance costs and the next service date for each asset. Tracking maintenance expenses can be important for budgeting purposes and deciding whether to replace a fixed asset. You can attach each fixed asset to one or more insurance policies, and verify that policy premiums align with the value of the assets.

| To  | See |
| --- | --- |
| Record service visits, post maintenance costs, and monitor maintenance costs. |[Maintain Fixed Assets](fa-how-maintain.md) |
| Monitor maintenance costs. | [Monitor maintenance costs](fa-how-maintain.md#monitor-maintenance-costs)|
| Update insurance information, post acquisition costs to insurance policies, modify insurance coverage, view insurance statistics, and list insurance policies. |[Insure Fixed Assets](fa-how-insure.md) |
| Monitor insurance coverage. | [Monitor insurance coverage](fa-how-insure.md#to-monitor-insurance-coverage) |

## Reclassify, transfer, split up/combine, adjust value, write-down, and dispose fixed assets

| To  | See |
| --- | --- |
| Reclassify fixed assets, transfer fixed assets to different locations, split up or combine assets. |[Transfer, Split, or Combine Fixed Assets](fa-how-trans-split-combine.md) |
| Adjust values of fixed assets, post appreciation, and post write-down transactions. |[Revalue Fixed Assets](fa-how-revalue.md) |
| Post disposal transactions, view disposal ledger entries, and post partial disposals. |[Dispose of or Retire Fixed Assets](fa-how-dispose-retire.md) |
| View disposal ledger entries. | [View disposal ledger entries](fa-how-dispose-retire.md#to-view-disposal-ledger-entries) |
| View projected disposal values. | [View projected disposal values](fa-how-manage-budgets.md#to-view-projected-disposal-values) |

## Tips for improving your fixed asset accounting

There are a few things you can implement in your accounting strategy for fixed assets that can help ensure you’re maximizing your earnings.

- Establish a threshold for capitalization. When you purchase an item, determine a fixed amount for capitalization. The amount helps ensure your accounting books are consistent, and makes it easier for you and your team to spot accounting errors.
- Reevaluate equipment lifecycle. It's important to correctly estimate the length of time you can use your fixed assets for their original purpose. Because accounting and depreciation rely on accurate lifecycle estimates, reevaluate when necessary because it might change over time.
- Tag your assets. It’s essential to track and tag your assets throughout their lifecycle because many factors can affect their value. Tagging helps track your items throughout the stages of their lifecycle, and help prevent theft, eliminate misplacement, and support financial statistics.
- Automate insight with fixed asset accounting software. Automating manual activities to track your data with fixed asset accounting software make processes easier to complete. Password protection can help provide access only to the people who need it and are trained for it.

## Related information

[Setting Up Fixed Assets](fa-setup.md)  
[Fixed assets analytics overview](fa-analytics-overview.md)  
[Finance overview](finance.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Change Which Features are Displayed](ui-experiences.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
