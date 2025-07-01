---
title: Linking Advance Invoice to Final Document
description: This section describes Advance Payments Localization for Czech extension functionality.
author: v-pejano

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: Czech, Advance Payments, Localization
ms.date: 10/01/2021
ms.reviewer: v-pejano
ms.author: v-pejano
---

# Linking Advance Invoice to Final Document

## Using an Advance Invoice in the Final Invoice

To use an advance invoice in the final invoice, follow these steps:

1. Enter the invoice in the system as usual. To link one or more advances to the invoice, use the **Link Advance Letter** action from the invoice header.
2. On the **Advance Letter Application** page, use the **New** function and expand the **Advance Letter No.** field to view a list of available advances for assignment to the invoice. Only advances with the same currency code and paid amounts by the sales invoice posting date are shown. Confirm the selected advance, which is then transferred to the **Advance Letter Application** page to link the invoice and the advance.
You can continue selecting more advances this way. Click another row on the page and again use the **Advance Letter No.** field to add additional advances to the linkage.
3. In the **Amount** field, specify how much of each advance should be applied to the invoice. You can apply multiple advances partially.
4. When the advance assignment is configured as intended, confirm the page with the **OK** button.

Note:

- An advance will always be applied up to the maximum value of the invoice. If the advance amount exceeds the invoice amount and the user doesn't reduce it manually, only the invoice amount will be deducted.
- If the user chooses partial application of the advance, only the specified portion will be deducted.
- If partial amounts from multiple advances are selected and their total exceeds the invoice value, the system will automatically apply the advances based on their payment date.
- Once the advances are assigned as desired, confirm the page by clicking **OK**.

## Viewing Information About Advance Usage in the Final Invoice

- In the **FactBox** of the invoice under **Advance Usage**, you can view the number of applied advances, their numbers and the total invoice amount after deducting advances.
- Standard invoice statistics do not include the advances. However, a preview posting can be run, which will show all entries, including those from applied advances.

## Unlinking Advance Invoice from Final Document

If you do not wish to use an advance in the invoice, it can be removed from the linkage:

1. Choose the ![Lightbulb icon to open the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Invoice**, and then select the related link.
2. Open the selected sales invoice and use the **Link Advance Letter** action, which opens the page with the linked advances.
3. On this page, you can edit amounts or remove the entire row with the advance. Ensure the page is in editable mode and that changes are saved.
4. Use the ellipsis (three dots) and choose **Delete**, then confirm the removal of the row with the linked advance letter.

After posting the invoice with the advance, a line with the **Usage** item type is created on the advance for the amount applied from the invoice. If a VAT document was also posted with the payment, a **VAT Usage** line is automatically created to deduct the VAT.

A VAT credit note can be printed from the advance history from the **VAT Usage** entry.  
The **VAT Usage** entry is created with the same date and document number as the sales invoice.

## Using Advance Invoice Created from an Order

- If the advance was created from an order, no additional configuration is needed for using the advance from that order.
- If a VAT document is posted for the advance, the VAT will be deducted automatically during invoice posting, and a VAT credit note will be generated.
- Just like for invoices, the order’s **Advance Usage** FactBox shows the number of linked advances and the total invoice amount after deducting advances.
- An order can be shipped and invoiced even if the advance has not been paid by the order’s posting date. The user will be notified and can decide whether to post the document.
- If the advance created from the order is not paid and the order is posted and invoiced, the link between the order and the advance is automatically removed, and the advance can be used for another final invoice after payment.

## See also

[Advance Payments for Czech Republic (Extension)](ui-extensions-advance-payments-localization-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](../../finance.md)
