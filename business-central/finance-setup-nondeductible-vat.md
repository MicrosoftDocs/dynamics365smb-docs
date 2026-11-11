---
title: Set Up Nondeductible VAT in Business Central
description: Set up nondeductible VAT in Business Central, specify the percentage of VAT you can't deduct, and choose how to post amounts and include them in costs.
author: altotovi
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.search.keywords: VAT, non-deductible, setup
ms.search.form: 187, 472, 473
ms.date: 11/11/2026
ms.custom: bap-template
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Set up nondeductible VAT in Business Central

Nondeductible value-added tax (VAT) is the VAT that's payable by a purchaser but that isn't deductible from the purchaser's own VAT liability. Companies can usually recover VAT on the purchase of goods and services that are related to their business activities. However, in some situations, a business incurs VAT that isn't deductible. These situations are typically related to the local regulations and can differ among countries/regions. However, the model of using nondeductible or partially deductible VAT is similar. You can use proportional VAT to calculate VAT when there's deductible and nondeductible VAT.

In general, VAT can't be deducted for some purchases because of the following factors:

- **The type of goods or services that are purchased**: VAT is fully or partially nondeductible according to the law about goods such as cars, mobile phones, and food purchased at restaurants.
- **Partially deductible prorated VAT**: VAT is prorated according to the ratio between the sales operations that VAT is owed for and all performed operations. VAT that exceeds this ratio can't be deducted.

Because it can be difficult to know where and how an item is used, contact the local tax authorities in your country/region. They can help determine whether you can deduct a specified percentage of the VAT, based on historical data.

> [!IMPORTANT]
> This global feature is available in countries/regions with VAT enabled, except Belgium, Italy, and Norway. These localizations have their own VAT features. Don't enable the global feature in these localizations because the upgrade procedure doesn't exist.

## Use nondeductible VAT

1. [!INCLUDE[open-search](includes/open-search.md)], enter **VAT Setup**, and then select the related link.
1. Select the **Enable Non-Deductible VAT** checkbox.
1. Configure how [!INCLUDE [prod_short](includes/prod_short.md)] treats nondeductible VAT values.

    1. In the **Use For Item Cost** field, specify whether the nondeductible VAT must be added to the item cost when you purchase items. Otherwise, the nondeductible VAT won't influence the item cost and the full amount is recorded only at the general ledger level.
    1. Select the **Use For Fixed Asset Cost** checkbox to add the nondeductible VAT to the fixed asset cost when you purchase new fixed assets. Otherwise, the nondeductible VAT won't influence the fixed asset cost and the full amount is recorded only at the general ledger level.
    1. Select the **Use For Project Cost** checkbox to specify that the nondeductible VAT must be added to the project cost when you purchase items for the project. Otherwise, the nondeductible VAT won't influence the project cost and the full amount is recorded only at the general ledger level.
    1. Select the **Show Non-Ded. VAT In Lines** checkbox to show nondeductible VAT on document lines. This checkbox controls visibility, not whether the amounts are calculated.

> [!IMPORTANT]
> After you enable nondeductible VAT, you can't turn it off. The feature can change data and upgrade database tables. We recommend enabling and testing the feature in a sandbox environment before enabling it in production.

## Use the nondeductible VAT percentage

1. [!INCLUDE[open-search](includes/open-search.md)], enter **VAT Posting Setup**, and then select the related link.
1. On the **VAT Posting Setup** page, set the fields as described in the following table.

    | Field | Description |
    |-------|-------------|
    | **Allow Non-Deductible VAT** | Specify whether nondeductible VAT applies to the current combination of a VAT business posting group and a VAT product posting group. Choose **Allow** to use nondeductible VAT or **Do Not Allow** to prevent its use for this combination. |
    | **Non-Deductible VAT %** | Specify the percentage of the VAT amount that can't be deducted. For example, if VAT is 100 and this field is 20, the nondeductible VAT amount is 20. |
    | **Non-Deductible Purchase VAT Account** | Specify the G/L account for the VAT amount that can't be deducted. If you leave this field blank, the amount is posted to the purchase line's account or the applicable fixed asset G/L account instead. |

1. Close the page.

> [!NOTE]
> You can't use unrealized VAT together with nondeductible VAT.
>
> Don't use the same **VAT Identifier** for VAT posting setup combinations that have different **Non-Deductible VAT %** values. Otherwise, the total nondeductible VAT amount will be calculated incorrectly.

## Related information

[Financial Management](finance.md)  
[Design details: Nondeductible VAT](design-details-nondeductible-vat.md)  
[Use nondeductible VAT](finance-how-use-non-deductible-vat.md)  
[Set Up Calculations and Posting Methods for Value-Added Tax](finance-setup-vat.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
