---
title: Add Comments to Cards and Documents
description: Add extra information to accounts, customers cards, or sales orders to communicate agreements, such as a special price or delivery method, to other users.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: tasks, work
ms.search.form: 124, 30
ms.date: 11/10/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Add comments to cards and documents

You can add extra information to G/L accounts, customers cards, or sales orders to communicate exceptions or special agreements to other users.
Practically all cards and document have a **Comments** action, which opens the **Comment Sheet** page where you can write or read comments. On documents, you can also add comments to individual lines.

You can transfer comments on ongoing documents to related posted documents. For example, if you turn on **Copy Comments Order to Shpt.**, a comment on a sales order is transferred to the posted sales shipment.

Use the **Sales & Receivables Setup** and **Purchases & Payables Setup** pages to specify which document types receive copied comments, such as from a sales order to a sales invoice.

> [!NOTE]
> Comments aren't printed or output to reports or externally-facing documents.

The following procedure describes how to add a comment to an item card. The steps are similar for all other cards and documents, except on document lines, the **Comments** action is placed on a lines action menu.

## To add a comment to an item card

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Items**, and then choose the related link.
2. Open the relevant item card.
3. Choose the **Comments** action.
4. On the **Comment Sheet** page, enter any text, and then choose the **OK** button.

## Related information

[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[General Business Functionality](ui-across-business-areas.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
