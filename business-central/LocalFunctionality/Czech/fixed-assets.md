---
title: Czech Local Functionality - Fixed Assets | Microsoft Docs
description: This section describes Czech local functionality - Fixed Assets
author: ACMartinKunes

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: Czech, finance, CZ, Fixed Assets
ms.date: 12/30/2019
ms.reviewer: v-pejano
ms.author: v-makune
---

# Fixed Assets

## Fixed Assets Tax Depreciation  
The Fixed Assets Tax Depreciation feature calculates and posts tax depreciation in compliance with the Income Tax Act (Law 586/1992 §26 - §33). This feature has a special setup for tax depreciation groups to enable entering rates and coefficients for new depreciation methods with Fixed Assets Tax Depreciation.

Each long-term tangible Fixed Asset belongs to a depreciation group. These groups determine minimal depreciation periods and parameters used for calculating depreciation.
The following depreciation methods are provided for long-term tangible Fixed Asset (FA) depreciations for tax purposes:

- Regular – This method is based on the acquisition value and percentage (straight line).
- Accelerated – This method is based on the book value and coefficient (declining balance).
- Regular based on the acquisition value and percentage (straight-line intangible).

Each long-term Fixed Asset belongs to a depreciation group. These groups determine minimal depreciation periods and parameters that will be used for calculating depreciation.

## Calculation of Depreciation Basis in Fixed Assets

Due to the Czech legislation, it is necessary to calculate tax depreciations from the depreciable basis which can be different from acquisition costs. According to the requirements, a depreciation basis by Czech Declining-balance depreciation method for the second and following years of Fixed Asset life should be calculated by the new formula defined in the Income Tax Act.
Changes have been made in the calculation of depreciation amount by the CZ Declining-balance depreciation method for the second and following years of Fixed Asset life by the formula stated above. The Tax depreciation is calculated annually and the Force No. of Days option is recommended for calculating the correct depreciation amount. 

## Fixed Assets Depreciation Holidays

The Fixed Asset Depreciation Holidays feature (by Income Tax Act – Law 586/1992 §26 part 8) enables user to discontinue depreciation for selected Fixed Asset and for specified periods. The system determines the depreciation schedule after the break period ends. 
The list of depreciation methods for which the discontinuing of depreciation has been implemented is as follows:

- Straight line
- Regular
- Accelerated
- Straight line for intangible fixed assets
- Enhanced depreciation methods and straight-line methods to pick up the threads of the depreciation schedule end after the break depreciation period.  

User can open FA Depreciation book and fill in the fields Depreciation Interrupt and Depreciation Interrupt up to. Field Keep Depr. Ending Date defines if you want to maintain the depreciation schedule.

## Two Steps Fixed Asset Acquisition

There are two steps to accomplish when acquiring a Fixed Asset in the Czech accounting. When a company gets an invoice for a Fixed Asset acquisition, it has to be posted. Since the moment of initial use of the Fixed Asset, the used Fixed Asset is posted. Both the acquisition and put in use steps are required and connected with G/L Entries. Fixed Assets are not depreciated until put in use.

For this topic, use Custom 2 fixed asset posting type for the first step (Acquisition) and Acquisition Fixed Asset posting type for the second step (Put in Use). Select the Fixed Asset Acquisition as Custom2 check box in Fixed Asset Setup to start use of this feature.
Value Custom 2 is renamed in Czech language from "Vlastní 2" to "Pořízení" for correct FA purchase identification and better accountant understanding.

## Fixed Asset Posting of Disposal

Czech accounting standards require specific posting when a Fixed Asset is being disposed of or be-ing sold. After selling or posting Fixed Assets (FA), Fixed Asset Posting of disposal ensures the Fixed Asset value remains the same as that of the acquired value after depreciation.

The Fixed Asset remains unchanged even after it is put to use. When the Fixed Asset is depreciated periodically, a corresponding sum is debited from the acquired cost at the time of disposal. The balance amount is the current Fixed Asset value.

On Depreciation Book, select the Corresponding G/L Entries on Disposal check box to make this feature operational. Also select the Corresponding FA Entries on Disposal check box to retain the correspondence between G/L Entries and FA Entries.  

## Different Types of Disposal and Maintenance

In the Czech accounting, it is necessary to post different types of disposal and different types of maintenance of Fixed Assets to specific G/L Accounts. A standard way offers only one method of disposal and maintenance posting.

A new setup was added for this feature – FA Extended Posting Group table. This table allows to set up each FA Posting group:

- Posting disposal to different Accounts in combination with Reason Code used  for disposal 
- Posting maintenance in combination with Maintenance Code used for maintenance

## Fixed assets clasification

### Classification Code

Tax of Income Law 586/1992 insists on sorting Fixed Assets by Production Classification marked CZ-CPA and by Classification building operations marked CZ-CC. The new Classification Code table and Classification Code field on Fixed Asset were added. This field is used for FA classification to the tax group.

## Fixed Asset Location/Responsible History Report

This feature provides users with ability to track Fixed Asset Location and Responsible Employee changes.
With the addition of this feature users are able to control location history of the Fixed Asset and history of employees responsible for the Fixed Asset.
This feature also provides reports for company verification where specific FA is/was located or to whom it is/was assigned.
To enable FA Location and Responsible Employee tracking (further as FA History) user first needs to enable this feature in Fixed Asset Setup with checkmark in the Fixed Assets History field. After enabling FA History in FA Setup, user can start tracking changes of FA Location and Responsible employees – these changes are stored in table FA History Entry.

Items of fixed assets:
- Save changes in FA evidence
- Include time and user stamp changes

New reports for transactions and history documentation added:
- FA Assignment/Discharge
- FA History

## Fixed Assets Reporting

In order to comply with the requirements in legislation reporting features and local reporting practices of Czech companies, this feature provides following reports:

- **Fixed Asset Card** – report combines data from standard FA List and FA details report, grouping details per FA Depreciation book.
- **FA Receipt** – report is printed when particular Fixed Asset is received to be put in use. Such document must be signed by company officials.
- **FA Disposal** – report is printed when particular Fixed Asset is disposed or damaged.
- **FA – Analysis G/L Account** – user can use this report to compare it with G/L Account.
- **Fixed Asset – Analysis 2** – user can define 3 columns for date, 4 columns for amount field, group total and choose export to Excel.
- **Fixed Asset – Analys. Dep. Book** – user can choose 2 depreciation books for comparison.
- **FA Phys. Inventory List** – companies are obliged to reconcile the physical state of Fixed Assets and book value in order to prepare the financial statement.  
- **FA Inventory List** – prints the FA Inventory list for Responsible Employee or for FA Location Code.

The following standard reports have been adjusted for the Czech Republic (new Group total, etc.):
- Fixed Asset – Analysis
- Fixed Asset – Book Value 01
- Fixed Asset – Book Value 02
- Fixed Asset – Projected Value
- Fixed Asset – G/L Analysis
- Maintenance – Analysis

## See Also
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](finance.md)  
