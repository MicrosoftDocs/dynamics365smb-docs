---
title: Manage FA Budgets
description: Set up details for future investments, disposals, and depreciation of fixed assets to support budget planning and forecasting.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: forecast, manage budgets, fixed assets
ms.search.form: 5610, 5611
ms.date: 08/06/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Manage budgets for fixed assets

You can set up budgeted fixed assets. For example, this lets you include anticipated acquisitions and sales in reports.  

To prepare your budgeted income statement, budgeted balance sheet, and cash budget, you need information about future investments, disposals, and depreciation of fixed assets. You can get this information from the **Fixed Asset - Projected Value** report. Before you print this report, you must prepare the budget.  

## Budget the acquisition cost of a fixed asset

To prepare a budget, you have to set up fixed asset cards for fixed assets that you intend to buy in the future. The budget fixed assets are set up as ordinary fixed assets, but it must be set up to not post to the general ledger.

When you post the acquisition cost, you enter the number of the budgeted fixed asset in the **Budgeted FA No.** field. This posts an acquisition cost with an opposite sign for the budgeted asset. This means that the total acquisition cost on the budgeted asset is the difference between the budgeted and the actual acquisition cost.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Fixed Assets**, and then choose the related link.
2. Choose the **New** action to create a new fixed asset card for the budgeted fixed asset.
3. Select the **Budgeted Asset** check box to prevent posting to the general ledger.
4. Fill in the remaining fields, assign a depreciation book, and then post the first acquisition cost with the budgeted fixed asset entered in the **Budgeted FA No.** field on the journal line. Learn more in [Acquire Fixed Assets](fa-how-acquire.md).

## Budget the disposal of a fixed asset

If you plan to sell assets within the budget period, you can enter information about sales price and sales date.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Fixed Assets**, and then choose the related link.
2. Select the fixed asset to be disposed of, and then choose the **Depreciation Books** action.
3. On the **FA Depreciation Books** page, fill in the **Projected Disposal Date** and **Projected Proceeds on Disposal** fields. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## View projected disposal values

To see the projected disposal values and have the gain and loss calculated, you can use the **FA Projected Value** report.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **FA Projected Value**, and then choose the related link.
2. Fill in the fields as necessary.
3. Choose the **Print** or **Preview** button.

## Budget depreciation

You can use the **Fixed Asset - Projected Value** report to calculate future depreciation. The report shows the book value and accumulated depreciation at the start of the selected period, changes during the period, and the book value and accumulated depreciation at the end of the selected period.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Fixed Asset Projected Value**, and then choose the related link.
2. Fill in the fields as necessary.
3. To see total values for all assets, clear the **Print per Fixed Asset** check box.
4. Leave the **Fixed Asset** FastTab blank to have all assets included. In the **Budgeted Asset** field, enter **No** to exclude budgeted assets or **Yes** to see budgeted assets only.
5. Choose the **Print** or **Preview** button.

## Related information

- [Fixed Assets](fa-manage.md)  
- [Fixed assets analytics overview](fa-analytics-overview.md)
- [Setting Up Fixed Assets](fa-setup.md)  
- [Finance](finance.md)  
- [Getting Ready for Doing Business](ui-get-ready-business.md)  
- [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
