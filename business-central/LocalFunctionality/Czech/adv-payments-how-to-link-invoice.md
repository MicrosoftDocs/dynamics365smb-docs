---
title: Link an advance invoice to a final document
description: This article describes how to link an invoice to a final document using Advance Payments in the Czech version.
author: v-pejano
ms.reviewer: v-pejano
ms.author: v-pejano
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.search.keywords: Czech, Advance Payments, Localization
ms.date: 09/17/2025
ms.custom: bap-template

---

# Link an advance invoice to a final document

To use an advance invoice in the final invoice, follow these steps:

1. To link one or more advances to the invoice, use the **Link Advance Letter** action from the invoice header.
2. On the **Advance Letter Application** page, use the **New** function and expand the **Advance Letter No.** field to view a list of available advances for assignment to the invoice. Only advances with the same currency code and paid amounts by the sales invoice posting date are shown. Confirm the selected advance, which then transfers to the **Advance Letter Application** page to link the invoice and the advance.

You can continue selecting more advances this way. Choose another row and use the **Advance Letter No.** field to add additional advances to the linkage.
3. In the **Amount** field, specify how much of each advance to apply to the invoice. You can apply multiple advances partially.
4. When the advance assignment is configured as intended, confirm the page with the **OK** button.

> [!NOTE]
>
> - An advance always applies up to the maximum value of the invoice. If the advance amount exceeds the invoice amount and you don't reduce it manually, only the invoice amount is deducted.
>
> - If you choose to partially apply the advance, only the specified portion is deducted.
> - If partial amounts from multiple advances are selected and their total exceeds the invoice value, [!INCLUDE [prod_short](../../includes/prod_short.md)] automatically applies the advances based on their payment date.
> - When the advances are assigned, confirm by clicking **OK**.

## View information about advance usage in the final invoice

- On the invoice the **FactBox** under **Advance Usage** shows the number of applied advances, their numbers, and the total invoice amount after deducting advances.
- Standard invoice statistics don't include the advances. However, you can run a preview posting that shows all entries, including those from applied advances.

## Unlink an advance invoice from a final document

If you don't want to use an advance in the invoice, you can remove it from the link.

1. Choose the ![Lightbulb icon to open the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Invoice**, and then select the related link.
2. Open the selected sales invoice. Use the **Link Advance Letter** action to open the page with the linked advances.
3. Edit the amounts, or remove the entire row with the advance. Ensure that the page is editable and that your changes are saved.
4. Choose the :::image type="content" source="../../media/assist-edit-icon.png" alt-text="Screenshot of the AssistEdit icon."::: icon, choose **Delete**, and then confirm the removal of the row with the linked advance letter.

After you post the invoice with the advance, a line with the **Usage** item type is created on the advance for the amount applied from the invoice. If a VAT document also posted with the payment, a **VAT Usage** line is automatically created to deduct the VAT.

You can print a VAT credit note from the advance history from the **VAT Usage** entry. The **VAT Usage** entry is created with the same date and document number as the sales invoice.

## Use an advance invoice created from an order

- If the advance was created from an order, no additional configuration is needed for using the advance from that order.
- If a VAT document is posted for the advance, the VAT is deducted automatically during invoice posting and a VAT credit note is generated.
- Like invoices, the order’s **Advance Usage** FactBox shows the number of linked advances and the total invoice amount after deducting advances.
- An order can be shipped and invoiced even if the advance hasn't been paid by the order’s posting date. [!INCLUDE [prod_short](../../includes/prod_short.md)] notifies you, and you can decide whether to post the document.
- If the advance created from the order isn't paid and the order is posted and invoiced, the link between the order and the advance is automatically removed. You can use the advance for another final invoice after payment.

## Related information

[Advance Payments for Czech Republic (Extension)](ui-extensions-advance-payments-localization-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](../../finance.md)
