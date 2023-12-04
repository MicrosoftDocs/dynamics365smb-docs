---
title: Set up non-deductible VAT
description: This article explains how to configure non-deductible VAT in Microsoft Dynamics 365 Business Central.
author: altotovi
ms.author: altotovi
ms.reviewer: 
ms.service: dynamics365-business-central
ms.topic: how-to
ms.search.keywords: VAT, non-deductible, setup
ms.search.form: 187, 472, 473
ms.date: 04/26/2023
ms.custom: bap-template

---

# Set up non-deductible VAT

Non-deductible value-added tax (VAT) is the VAT that's payable by a purchaser but that isn't deductible from the purchaser's own VAT liability. Companies can usually recover VAT on the purchase of goods and services that are related to their business activities. However, in some situations, a business incurs VAT that isn't deductible. These situations are typically related to the local regulations and can differ among countries/regions. However, the model of using non-deductible or partially deductible VAT is similar. You can use proportional VAT to calculate VAT when there's deductible and non-deductible VAT.

In general, VAT can't be deducted for some purchases because of the following factors:

- **The type of goods or services that are purchased** – VAT is fully or partially non-deductible by a provision of the law about goods such as cars, mobile phones, and food that's purchased at restaurants.
- **Partially deductible pro-rated VAT** – VAT is pro-rated according to the ratio between the sales operations that VAT is owed for and all operations that have been performed. VAT that exceeds this ratio can't be deducted.

Because it can be difficult to know where and how an item is used, you must contact the local tax authorities in your country/region to determine whether a specified percentage of the VAT is deductible based on historical data. 

> [!IMPORTANT]
> This global feature is available in all countries with enabled VAT **except for Belgium, Italy, and Norway**. These localizations already have existing local feature and will be upgraded in the future. Don't run this feature in these countries because the upgrade procedure doesn't exist.

## Use non-deductible VAT

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Setup**, and then select the related link.
2. Select the **Enable Non-Deductible VAT** checkbox.

    > [!IMPORTANT]
    > After you enable non-deductible VAT, you can't turn it off, because the feature might include changes to data and might initiate an upgrade of some database tables. Microsoft strongly recommends that you first enable and test this feature in the sandbox environment before you enable it in the production environment.

3. Configure how the system will treat non-deductible VAT values.

    1. In the **Use For Item Cost** field, specify whether the non-deductible VAT must be added to the item cost when you purchase items. Otherwise, the non-deductible VAT won't have an influence on the item cost, and the full amount will be recorded only at the general ledger level.
    2. Select the **Use For Fixed Asset Cost** checkbox to add the non-deductible VAT to the fixed asset cost when you purchase new fixed assets. Otherwise, the non-deductible VAT won't have an influence on the fixed asset cost, and the full amount will be recorded only at the general ledger level.
    3. Select the **Use For Job Cost** checkbox to specify that the non-deductible VAT must be added to the job cost when you purchase items for the job. Otherwise, the non-deductible VAT won't have an influence on the job cost, and the full amount will be recorded only at the general ledger level.
    4. Select the **Show Non-Ded. VAT In Lines** checkbox to specify that the non-deductible VAT must be shown on document line pages for easier manipulation of VAT amounts.

## Use the non-deductible VAT percentage

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Posting Setup**, and then select the related link.
2. On the **VAT Posting Setup** page, set the fields as described in the following table.

    | Field | Description |
    |-------|-------------|
    | Allow Non-Deductible VAT | Specify whether the non-deductible VAT is considered for the current combination of a VAT business posting group and a VAT product posting group. |
    | Non-Deductible VAT % | Specify the percentage of the transaction amount that VAT isn't applied to. |
    | Non- Deductible Purchase VAT Account | Specify the account that's associated with the VAT amount that isn't deducted because of the type of goods or services that are purchased. |

    > [!NOTE]
    > To have general ledger (G/L) entries that use the dedicated account instead of the sales/purchase account, you can either leave the **Non-Deductible Purchase VAT Account** field blank or set the **G/L Account** field.

3. Select **OK**.

> [!NOTE]
> You can't use unrealized VAT together with non-deductible VAT.
>
> Don't use the same **VAT identifier** value for both normal VAT where the **Non-Deductible VAT %** field is set to **0** (zero) and normal VAT where the **Non-Deductible VAT %** field is set to a non-zero value. Otherwise, the total non-deductible VAT amount will be incorrectly calculated.

## See also

[Financial Management](finance.md)  
[Design details: Non-deductible VAT](design-details-nondeductible-vat.md)  
[Use non-deductible VAT](finance-how-use-non-deductible-vat.md)  
[Set Up Calculations and Posting Methods for Value-Added Tax](finance-setup-vat.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
