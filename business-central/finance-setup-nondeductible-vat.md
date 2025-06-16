---
title: Set up nondeductible VAT
description: This article explains how to configure nondeductible VAT in Microsoft Dynamics 365 Business Central.
author: altotovi
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.search.keywords: VAT, non-deductible, setup
ms.search.form: 187, 472, 473
ms.date: 08/13/2024
ms.custom: bap-template
ms.reviewer: bholtorf
---

# Set up nondeductible VAT

Nondeductible value-added tax (VAT) is the VAT that's payable by a purchaser but that isn't deductible from the purchaser's own VAT liability. Companies can usually recover VAT on the purchase of goods and services that are related to their business activities. However, in some situations, a business incurs VAT that isn't deductible. These situations are typically related to the local regulations and can differ among countries/regions. However, the model of using nondeductible or partially deductible VAT is similar. You can use proportional VAT to calculate VAT when there's deductible and nondeductible VAT.

In general, VAT can't be deducted for some purchases because of the following factors:

- **The type of goods or services that are purchased** – VAT is fully or partially nondeductible according to the law about goods such as cars, mobile phones, and food purchased at restaurants.
- **Partially deductible pro-rated VAT** – VAT is pro-rated according to the ratio between the sales operations that VAT is owed for and all performed operations. VAT that exceeds this ratio can't be deducted.

Because it can be difficult to know where and how an item is used, contact the local tax authorities in your country/region. They can help determine whether you can deduct a specified percentage of the VAT, based on historical data.

> [!IMPORTANT]
> This global feature is available in all countries with enabled VAT **except for Belgium, Italy, and Norway**. These localizations already have existing local feature and will be upgraded in the future. Don't run this feature in these countries because the upgrade procedure doesn't exist.

## Use nondeductible VAT

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Setup**, and then select the related link.
2. Select the **Enable Non-Deductible VAT** checkbox.

    > [!IMPORTANT]
    > After you enable non-deductible VAT, you can't turn it off, because the feature might include changes to data and might initiate an upgrade of some database tables. Microsoft strongly recommends that you first enable and test this feature in the sandbox environment before you enable it in the production environment.

3. Configure how the [!INCLUDE [prod_short](includes/prod_short.md)] treats nondeductible VAT values.

    1. In the **Use For Item Cost** field, specify whether the nondeductible VAT must be added to the item cost when you purchase items. Otherwise, the nondeductible VAT won't influence the item cost and the full amount is recorded only at the general ledger level.
    2. Select the **Use For Fixed Asset Cost** checkbox to add the nondeductible VAT to the fixed asset cost when you purchase new fixed assets. Otherwise, the nondeductible VAT won't influence the fixed asset cost and the full amount is recorded only at the general ledger level.
    3. Select the **Use For Job Cost** checkbox to specify that the nondeductible VAT must be added to the project cost when you purchase items for the project. Otherwise, the nondeductible VAT  won't influence the project cost and the full amount is recorded only at the general ledger level.
    4. Select the **Show Non-Ded. VAT In Lines** checkbox to specify that the nondeductible VAT must be shown on document line pages for easier manipulation of VAT amounts.

## Use the nondeductible VAT percentage

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Posting Setup**, and then select the related link.
2. On the **VAT Posting Setup** page, set the fields as described in the following table.

    | Field | Description |
    |-------|-------------|
    | **Allow Non-Deductible VAT** | Specify whether the nondeductible VAT is considered for the current combination of a VAT business posting group and a VAT product posting group. |
    | **Non-Deductible VAT %** | Specify the percentage of the transaction amount that VAT isn't applied to. |
    | **Non- Deductible Purchase VAT Account** | Specify the account associated with the VAT amount that isn't deducted because of the type of goods or services that are purchased. |

    > [!NOTE]
    > To have general ledger (G/L) entries that use the dedicated account instead of the sales/purchase account, you can either leave the **Non-Deductible Purchase VAT Account** field blank or set the **G/L Account** field.

3. Select **OK**.

> [!NOTE]
> You can't use unrealized VAT together with non-deductible VAT.
>
> Don't use the same **VAT identifier** value for both normal VAT where the **Non-Deductible VAT %** field is set to **0** (zero) and normal VAT where the **Non-Deductible VAT %** field is set to a non-zero value. Otherwise, the total non-deductible VAT amount will be incorrectly calculated.

## Related information

[Financial Management](finance.md)  
[Design details: Nondeductible VAT](design-details-nondeductible-vat.md)  
[Use nondeductible VAT](finance-how-use-non-deductible-vat.md)  
[Set Up Calculations and Posting Methods for Value-Added Tax](finance-setup-vat.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
