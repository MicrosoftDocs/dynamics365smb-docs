---
title: Set Up Fixed Asset for Depreciation Calculation
description: Set up fixed asset depreciation books, accounting periods, asset blocks, and additional depreciation for the India localization of Business Central.
author: v-debapd
ms.topic: overview
ms.devlang: al
ms.search.keywords: India, local, IN, English, fixed asset setup, depreciation calculation, depreciation books 
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up fixed asset for depreciation calculation

## Overview

Business Central includes fixed asset depreciation calculations for the Indian localization.

The functionality supports block-based income tax depreciation and shift-based depreciation. Configure rates and periods for your applicable requirements; the setup doesn't determine legal eligibility.

## Process

Following is the list of Setups, user needs to configure for Fixed Assets in **Business Central**.

- [Depreciation Book](fa_overview.md#set-up-fa-depreciation-books)
- [FA Accounting Period Income Tax](fa_overview.md#set-up-fa-accounting-period-for-income-tax)
- [FA Block Code](fa_overview.md#set-up-fa-block-code)
- [Setup for Additional Depreciation](fa_overview.md#set-up-additional-depreciation)

## Set up FA depreciation books

Fixed assets must have a depreciation book to record depreciations for the fixed assets.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Depreciation Books**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**No. of Days Non Seasonal**|Specifies the number of non seasonal days.|
    |**No. of Days Seasonal**|Specifies the number of seasonal days.|
    |**FA Book Type**|Select **Income Tax** for block-based depreciation. Leave the field blank for shift-based depreciation.|
    |**Depr. Threshold Days**|Specifies the threshold days for depreciation calculation.|
    |**Depr. Reduction %**|Specifies the reduction percentage for depreciation calculation.|

Before selecting **Income Tax**, clear **Fiscal Year 365 Days** and set both seasonal day fields to zero. The book validation requires these settings. Use the seasonal day fields for books with a blank **FA Book Type**.

## Set up FA accounting period for income tax

Fixed Asset Income Tax Accounting Period needs to be created for depreciation calculation.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Fixed Asset Accounting Periods Inc. Tax**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Starting Date**|Specify the starting date of the accounting period.|
    |**Name**|Specify the name of months.|
    |**New Fiscal Year**|Specify which month is the starting of a new fiscal year.|

## Set up FA block code

Fixed Asset Block Code is required for depreciation calculation for Income Tax Act.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **FA Classes**, and then choose the related link.
1. Select the relevant class, and choose **Blocks**.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Code**|Enter the relevant code of the block.|  
    |**Description**|Specify the description of the block.|
    |**Book Value**|Specifies the total book value of the block.|
    |**Depreciation %**|Specify the depreciation percentage of the block.|
    |**No. of Assets**|Shows the number of assets in the block with an income tax depreciation book and no disposal date.|
    |**Add. Depreciation %**|Specify the additional depreciation percentage of the block.|
    |**FA Class Code**|Specifies the fixed asset class code for which the block is attached.|

## Set up additional depreciation

Setup must be done to calculate additional depreciation for Fixed Assets.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Fixed Assets**, and then choose the related link.
1. Open the relevant asset, and enable **Add. Depr. Applicable**.

## Related information

[Fixed Asset Depreciation](FA_Depreciation.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]