---
title: Set Up Automatic Account Groups in Sweden
description: Set up automatic account groups in the Swedish version of Business Central to allocate journal and document amounts across accounts and dimensions.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: automatic account posting groups, automatic account codes, posting groups
ms.search.form: 4850, 4851, 4852
ms.date: 10/23/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up automatic account posting groups in the Swedish version

To use automatic account codes, create an automatic account group. The group defines the accounts and dimensions to which amounts are allocated.

## Set up automatic account posting groups

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Automatic Account Groups**, and then choose the related link.
1. Choose **New**.
1. On the **General** FastTab, enter a unique **No.** and a **Description** for the group.
1. In the lines, fill in the fields as described in the following table.

    | Field | Description |
    |-------|-------------|
    | **Allocation %** | Enter the percentage of the source line's amount excluding VAT to allocate. |
    | **G/L Account No.** | Select the posting account for the allocation, or leave the field blank to use the source line's G/L account. An account you select must allow direct posting and must not be blocked. |
    | **Shortcut Dimension 1 Code** and **Shortcut Dimension 2 Code** | Specify dimension values for the allocation. The field names reflect your company's global dimension names. |

1. Use the line's **Dimensions** action if you need to assign additional dimensions.
1. Check that **Total Balance** is zero before you use the group.

> [!NOTE]
> **Total Balance** is the sum of **Allocation %** across the group's lines. Posting is blocked if the percentages don't total zero.

## Related information

- [Automatic Account Codes](automatic-account-codes.md)  
- [Setting Up Posting Groups](../../finance-posting-groups.md)  
- [Work with General Journals](../../ui-work-general-journals.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
