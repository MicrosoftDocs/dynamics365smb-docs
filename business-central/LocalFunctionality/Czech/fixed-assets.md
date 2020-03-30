---
title: Czech Local Functionality - Fixed Assets | Microsoft Docs
description: This section describes Czech local functionality - Fixed Assets
author: ACMartinKunes

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: Czech, finance, CZ, Fixed Assets
ms.date: 04/01/2020
ms.reviewer: v-pejano
ms.author: v-makune
---

# Fixed Assets

## Fixed Assets Tax Depreciation  
The Fixed Assets Tax Depreciation feature calculates and posts tax depreciation in compliance with the Income Tax Act (Law 586/1992 §26 - §33). This feature has a special setup for tax depreciation groups to enable entering rates and coefficients for new depreciation methods with fixed assets tax depreciation.

Each long-term tangible fixed asset belongs to a depreciation group. These groups determine minimal depreciation periods and parameters used for calculating depreciation. The following depreciation methods are provided for long-term tangible fixed asset (FA) depreciations for tax purposes:

- Regular – This method is based on the acquisition value and percentage (straight line).
- Accelerated – This method is based on the book value and coefficient (declining balance).
- Regular based on the acquisition value and percentage (straight-line intangible).

Each long-term fixed asset belongs to a depreciation group. These groups determine minimal depreciation periods and parameters that will be used for calculating depreciation.

## Calculation of Depreciation Basis in Fixed Assets

Due to Czech legislation, it is necessary to calculate tax depreciations from the depreciable basis which can be different from acquisition costs. According to the requirements, a depreciation basis by the Czech declining-balance depreciation method for the second and following years of a fixed asset's life should be calculated by the new formula defined in the Income Tax Act.

Changes have been made in the calculation of depreciation amounts by the CZ declining-balance depreciation method for the second and following years of a fixed asset's life by the formula stated above. The tax depreciation is calculated annually and the **Force No. of Days** option is recommended for calculating the correct depreciation amount.

## Fixed Assets Depreciation Holidays

The Fixed Asset Depreciation Holidays feature (according to the Income Tax Act – Law 586/1992 §26 part 8) enables user to discontinue depreciation for selected fixed assets and for specified periods. The system determines the depreciation schedule after the break period ends.
The list of depreciation methods for which the discontinuing of depreciation has been implemented is as follows:

- Straight line
- Regular
- Accelerated
- Straight line for intangible fixed assets
- Enhanced depreciation methods and straight-line methods to pick up the threads of the depreciation schedule end after the break depreciation period.  

Users can open the FA depreciation book and fill in the **Depreciation Interrupt** and **Depreciation Interrupt up to** fields. The **Keep Depr. Ending Date** field defines if you want to maintain the depreciation schedule.

## Two-Step Fixed Asset Acquisition

There are two steps to accomplish when acquiring a fixed asset in Czech accounting. When a company gets an invoice for a fixed asset acquisition, it must be posted. Since the initial use of the fixed asset, the used fixed asset is posted. Both the acquisition and put-to-use steps are required and connected with G/L entries. Fixed assets are not depreciated until they are put to use.

For this process, use the **Custom 2** fixed asset posting type for the first step (acquisition) and **Acquisition** fixed asset posting type for the second step (put to use). Select the **Fixed Asset Acquisition as Custom2** check box on the **Fixed Asset Setup** page to start using this feature.

The value **Custom 2** is renamed in Czech language from "Vlastní 2" to "Pořízení" for correct FA purchase identification and better accountant understanding.

## Fixed Asset Posting of Disposal

Czech accounting standards require specific posting when a fixed asset is being disposed of or being sold. After selling or posting fixed assets, the posting of disposal ensures the fixed asset value remains the same as that of the acquired value after depreciation.

The fixed asset remains unchanged even after it is put to use. When the fixed asset is depreciated periodically, a corresponding sum is debited from the acquired cost at the time of disposal. The balance amount is the current fixed asset value.

On the **Depreciation Book** page, select the **Corresponding G/L Entries on Disposal** check box to make this feature operational. Also select the **Corresponding FA Entries on Disposal** check box to retain the correspondence between G/L entries and FA entries.  

## Different Types of Disposal and Maintenance

In Czech accounting, it is necessary to post different types of disposal and different types of maintenance of fixed assets to specific G/L accounts. A standard way offers only one method of disposal and maintenance posting.

A new setup is added for this, namely the **FA Extended Posting Group** table. This table allows to set up each FA posting group:

- Posting disposals to different accounts in combination with **Reason Code** field for disposals
- Posting maintenance in combination with the **Maintenance Code** field for maintenance

## Fixed Assets Clasification

### Classification Code

The Tax of Income Law 586/1992 insists on sorting fixed assets by production classification marked CZ-CPA and by building operations classification marked CZ-CC. The new **Classification Code** table and the **Classification Code** field are added. The field is used for FA classification to the tax group.

## Fixed Asset Location/Responsible History Report

This feature provides users with the ability to track changes to the location and responsible employee for fixed assets.

With the addition of this feature, users are able to control location history of the fixed asset and the history of employees responsible for the fixed asset.
This feature also provides reports for company verification where a specific fixed asset is/was located or to whom it is/was assigned.

To enable FA Location and responsible-employee tracking (FA history), user must first enable this feature by selecting the **Fixed Assets History** check box on the **Fixed Asset Setup** page. User can then start to track changes in fixed assets' location and responsible employees. The changes are stored in the **FA History Entry** table.

Items of fixed assets:
- Save changes in FA evidence
- Include time and user stamp changes

New reports for transactions and history documentation added:
- FA Assignment/Discharge
- FA History

## Fixed Assets Reporting

In order to comply with the requirements in legislation reporting features and local reporting practices of Czech companies, this feature provides the following reports:

- **Fixed Asset Card** – combines data from the standard **FA List** and **FA Details** reports, grouping details per FA depreciation book.
- **FA Receipt** – is printed when a particular fixed asset is received to be put to use. Such document must be signed by company officials.
- **FA Disposal** – is printed when a particular fixed asset is disposed of or damaged.
- **FA – Analysis G/L Account** – used to compare it with G/L account.
- **Fixed Asset – Analysis 2** – users can define 3 columns for date, 4 columns for amount field, group totals, and export to Excel.
- **Fixed Asset – Analys. Dep. Book** – user can choose 2 depreciation books for comparison.
- **FA Phys. Inventory List** – companies are obliged to reconcile the physical state of fixed assets and book value in order to prepare the financial statement.  
- **FA Inventory List** – prints the fixed assets inventory per responsible employee or location code.

The following standard reports have been adjusted for the Czech Republic (new Group total, etc.):
- **Fixed Asset – Analysis**
- **Fixed Asset – Book Value 01**
- **Fixed Asset – Book Value 02**
- **Fixed Asset – Projected Value**
- **Fixed Asset – G/L Analysis**
- **Maintenance – Analysis**

## See Also
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](finance.md)  
