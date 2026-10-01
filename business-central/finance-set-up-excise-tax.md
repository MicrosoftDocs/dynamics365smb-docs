---
title: Set up excise tax
description: Learn how to set up excise tax types, assign one or more excise taxes to items, configure fixed assets, and prepare excise journals.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: Primary_7414, 7416, 30, 5600, 6285
ms.date: 08/26/2026
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

You can assign multiple excise tax types to an item. Each excise tax type has its own quantity and unit of measure.

### Set up excise taxes for an item

1. Open the **Item Card** page for the item.
1. Choose the **Excise Taxes** action.
1. On the **Excise Taxes** page, add a line.
1. In the **Excise Tax Type Code** field, select an enabled excise tax type.
1. In the **Quantity for Excise Tax** field, enter the quantity that the tax calculation uses.
1. In the **Excise Tax Unit of Measure Code** field, select the unit of measure for the quantity.
1. Repeat these steps for each excise tax type that applies to the item.

You can assign an excise tax type only once to an item.

On the **Excise Taxes** page for the target item, choose **Copy from Item**, and then select the source item on the **Item List** page. [!INCLUDE [prod_short](includes/prod_short.md)] copies the excise tax types that aren't already set up for the target item. Existing lines aren't changed.

In version 29 and later, [!INCLUDE [prod_short](includes/prod_short.md)] moves the existing excise tax setup for each item to the **Excise Taxes** page during the upgrade. You don't need to recreate the setup.

### Set up excise tax for a fixed asset

Open the **Fixed Asset Card** page. On the **Excise Tax** FastTab, specify the excise tax type, quantity, and unit of measure.

> [!NOTE]
> You can assign multiple excise tax types to an item, but you can assign only one excise tax type to a fixed asset.

## Set up a number series for excise tax journals

You must create a number series for excise tax journals. To learn more about number series, go to [Create number series](ui-create-number-series.md).

1. [!INCLUDE [open-search](includes/open-search.md)], enter **No. Series**, and select the related link.
1. Fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

## Set up a journal batch for excise taxes

You can use one journal batch to process all enabled excise tax types. You can also restrict a batch to one excise tax type.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Excise Journal**, and select the related link.
1. In the **Journal Batch Name** field, choose the :::image type="content" source="media/assist-edit-icon.png" alt-text="Screenshot of the AssistEdit icon.":::.
1. On the **Excise Journal Batches** page, choose **New**.
1. In the **Batch Name** field, enter a name for the batch.
1. In the **Type** field, choose **Excises**.
1. To process one enabled excise tax type in this batch, select it in the **Excise Tax Type Filter** field. Leave the field blank to process all enabled excise tax types.
1. Fill in the remaining fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

## Related information

[Register excise tax](finance-register-excise-tax.md)  
[Use CBAM and EPR calculations](sustainability-cbam-epr-calculations.md)  

[!INCLUDE [footer-banner](includes/footer-banner.md)]
