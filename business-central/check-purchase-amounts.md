---
title: Check amounts on purchase invoices and credit memos
description: You can verify that the total amount on purchase invoices and credit memos equals the total amounts, including VAT, on the lines.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords:
ms.date: 03/14/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Check amounts on purchase invoices and credit memos

> [!NOTE]
> Businesses around the world can benefit from this functionality, so in 2025 release wave 1 we moved it out of the Dutch version and made it available to everyone.

Before posting a purchase invoice or credit memo, [!INCLUDE [prod_short](includes/prod_short.md)] checks whether the amount including VAT and the VAT amount on the document equals the total amount on the purchase lines. This check requires that you fill in the **Doc. Amount Incl. VAT** and **Doc. Amount VAT** fields on the purchase invoice or credit memo.  

When the document has only one purchase line, or all lines are subject to the same VAT percentage, [!INCLUDE [prod_short](includes/prod_short.md)] calculates the value in the **Doc. Amount VAT** field when you add purchase lines and fill in the **Doc. Amount Incl. VAT** field. If there are several lines with different VAT percentages, you must manually enter the value in the **Doc. Amount VAT** field.  

By default, [!INCLUDE [prod_short](includes/prod_short.md)] checks the total amounts. If you prefer that it doesn't, you can turn off the **Check Doc. Total Amounts** toggle on the **Purchases & Payables Setup** page.  

If the total amount on the document differs from the total amount of its lines, you can add a few values to the page that can help you find out why. You can add the total amount, total base amount, total VAT amount, and total amount including VAT values. The values display at the bottom of the document. To avoid clutter on the page during daily work, these values are hidden. To add these values to the document, turn on the **Show Totals on Purch. Inv.-CM.** toggle on the **Purchases & Payables Setup** page.  

> [!NOTE]  
> If you turn on this feature, [!INCLUDE [prod_short](includes/prod_short.md)] recalculates totals on all purchase invoices and credit memos which, depending on the number of documents, might take some time.
>
> You can't turn on this feature if you have purchase invoices or credit memos that don't have lines, or where a quantity isn't specified on the lines.  

## Related information
  
[Set Up Validation of Purchase Amounts](how-to-set-up-validation-of-purchase-amounts.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
