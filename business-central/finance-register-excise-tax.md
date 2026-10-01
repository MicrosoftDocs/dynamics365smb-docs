---
title: Register excise tax
description: Learn how to generate, register, and review excise tax journal entries for items and fixed assets in Dynamics 365 Business Central.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: tax
ms.search.form: Primary_6287, 6285, 7414
ms.date: 08/26/2026
ms.custom: bap-template
---

# Register excise tax

Excise taxes are levied on the production or sale of specific goods, such as fuel, alcohol, and tobacco. In [!INCLUDE [prod_short](includes/prod_short.md)], you can register and track excise tax information to ensure accurate tax reporting and compliance with regulatory requirements. By registering excise tax, your company can streamline tax calculations, maintain detailed audit trails, and reduce the risk of non-compliance penalties.

> [!NOTE]
> Registering excise taxes doesn't create general ledger entries. It only calculates the excise tax amounts for reporting purposes.

## Register excise tax

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Excise Journal**, and select the related link.
1. Select the journal batch that you want to use.
1. Choose the **Generate Excise Tax Entries** action to open the **Generate Excise Tax Journal Entries** page.
1. In the **Posting Date**, **Starting Date**, and **Ending Date** fields, enter the dates for the journal lines and ledger entries.
1. If needed, filter the excise tax types in the **Code** field, or limit the entries with the **Item Filter** and **Fixed Asset Filter** fields.
1. Choose **OK** to generate the journal lines.
1. Review the generated lines.
1. If needed, use the **Dimensions** action to add dimensions to the selected line.
1. Choose the **Register** action.

When an item has multiple excise tax types, [!INCLUDE [prod_short](includes/prod_short.md)] creates a separate journal line for each applicable tax type and item ledger entry. The tax type must be enabled and allowed for the entry type.

If the batch has an **Excise Tax Type Filter**, generation includes only that tax type. If the filter is blank, generation includes all enabled tax types.

Generating the journal again doesn't create another line for a tax type that is already in the journal or registered for the same item ledger entry. You can register the tax types at different times. [!INCLUDE [prod_short](includes/prod_short.md)] marks the item ledger entry as **Excise Tax Posted** only after you register all applicable tax types.

## Review your excise tax transactions

After you register your excise taxes for items or fixed assets, you can use the **Excise Taxes Transaction Logs** page to review the data. To drill down into the transactions, use the **Item Ledger Entry** and **FA Ledger Entry** actions to explore the related ledger entries.

## Related information

[Set up excise tax](finance-set-up-excise-tax.md)  
[Use CBAM and EPR calculations](sustainability-cbam-epr-calculations.md)  
[Financial management](finance.md)

[!INCLUDE [footer-banner](includes/footer-banner.md)]
