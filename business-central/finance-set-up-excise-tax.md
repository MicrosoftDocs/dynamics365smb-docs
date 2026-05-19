---
title: Set up excise tax
description: This article describes how to set up excise tax.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 
ms.date: 03/16/2026
ms.custom: bap-template
---

# Set up excise tax

Some countries/regions require businesses to register and report excise taxes on the production or sale of specific goods, such as fuel, alcohol, and tobacco. This article describes what you need to set up in [!INCLUDE [prod_short](includes/prod_short.md)] so that you can do that.

Before you can calculate excise taxes, you must configure [excise tax types](#set-up-excise-tax-types). Excise tax types represent the goods or services that you want to register excise tax for. For each excise tax type, you can define a tax basis as weight, sugar content, active content, volume, pure alcohol (ABV), or quantity. Also, set up excise duty rates for each excise tax type to calculate the final tax amount based on the selected basis and the accumulated excise‑liable quantity.

Finally, configure the items and fixed assets you want to include in excise tax calculations.

## Set up excise tax types

Excise tax types represent the goods you want to register excise tax for.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Excise Tax Types**, and select the related link.
1. Fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]
1. To make the types available on excise tax journals, turn on the **Enabled** toggle.
1. Choose the **Configure Entry Permissions** action to open the **Excise Tax Entry Permissions** page. 
1. In the **Excise Entry Type** field, specify the type of document to include in excise tax calculations. 
1. On the **Excise Tax Types** page, choose the **Item/FA Rates** action to open the **Excise Tax Item/FA Rates** page.
1. On the **Excise Tax Item/FA Rates** page, in the **Source Type** field, specify whether the rate applies to items of fixed assets.
1. In the **Source No.** field, select the item or fixed asset only if this rate applies to a single, specific item or fixed asset. Otherwise, leave this field blank because excise rates for items and fixed assets are defined on their respective cards.
1. In the **Excise Duty** field, specify the amount of tax to register for the item or fixed asset.
1. In the **Effective From Date** field, specify the date from which you want to calculate excise tax for the item or fixed asset.
1. Optionally, in the **Report Caption** field, enter text to include in your excise tax report. For example, if you're registering tax for plastics and using weight as the measure, you might enter "Plastic Excise Tax (by Weight)."

## Set up items and fixed assets for excise tax

To prepare items and fixed assets for registering excise tax, on the **Excise Tax** FastTab of the **Item Card** or **Fixed Asset Card** pages, specify the relevant type of excise tax, the unit of measure, and the quantity.

> [!NOTE]
> You can only assign one excise tax type to an item or fixed asset. You can't combine multiple excise taxes for the same item or fixed asset.

## Set up a number series for excise tax journals

You must create a number series for excise tax journals. To learn more about number series, go to [Create number series](ui-create-number-series.md).

1. [!INCLUDE [open-search](includes/open-search.md)], enter **No. Series**, and select the related link.
1. Fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

## Set up a journal batch for excise taxes

You must set up a separate journal batch for each excise tax type. For example, one for alcohol, one for sugar, one for plastic, and so on.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Excise Journals**, and select the related link.
1. In the **Journal Batch Name** field, choose the :::image type="content" source="media/assist-edit-icon.png" alt-text="Screenshot of the AssistEdit icon.":::.
1. On the **Excise Journal Batches** page, choose **New**.
1. In the **Batch Name** field, enter a name that matches the type of excise tax that the journal is for.
1. In the **Excise Tax Type Filter** field, choose the type of excise tax that the journal is for. To create a new filter, follow these steps:
   1. In the drop-down, choose **New**.
   1. In the **Code** field, enter a name that matches the type of excise tax that the journal is for.
   1. Fill in the remaining fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  
1. In the **Type** field, choose **Excises**.
1. Fill in the remaining fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

## Related information

[Register excise tax](finance-register-excise-tax.md)  
[Use CBAM and EPR calculations](sustainability-cbam-epr-calculations.md)  

[!INCLUDE [footer-banner](includes/footer-banner.md)]