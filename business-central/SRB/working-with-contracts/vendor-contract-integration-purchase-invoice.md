---
title: Vendor contract integration in purchase invoices
description: Get and connect vendor subscription contract lines with purchase invoices
author: bholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 51,
ms.date: 12/16/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Vendor contract integration in purchase invoices

Enhance your accounts payable process by linking purchase invoice lines to vendor subscription contract lines and retrieving contract lines directly within purchase invoices. These features streamline recurring vendor billing and ensure accurate contract-based invoicing in Business Central.

With vendor contract integration, accountants can efficiently process recurring supplier invoices by:

- Assigning purchase invoice lines to vendor contract lines.
- Retrieving open vendor contract lines directly into purchase invoices.

This setup enables automated, accurate billing and reduces manual data entry.

## Retrieve vendor contract lines in a purchase invoice

Start the invoicing process for vendor contracts directly from the purchase invoice, allowing contract lines to be called up and linked to invoice lines.

### Sample scenario

The accountant receives an invoice from a supplier that belongs to a vendor subscription contract. They want to compare the invoice with the contract and then process it without having to leave the purchase invoice. Starting from the purchase invoice, they want to be able to call up the contract elements (lines) in the purchase invoice. They must be able to adjust the billing period and the amount. This procedure ensures that the contract is updated correctly.

### How it works

1. **Get Get Vendor Subscription Contract Lines** action

   - Available in the purchase invoice header.
   - Opens a worksheet page showing all open vendor subscription contract lines for the current vendor, grouped by contract number (collapsible view).

2. **Worksheet Get Vendor Subscription Contract Lines**
   - **Selected:** Indicates the vendor subscription contract lines to be called up in the purchase invoice (editable).
   - Fields: **Contract No.**, **Your Reference**, **Type**, **No.**, **Description Subscription**, **Description Subscription Line**, **Next Invoice Date**, **Billing to Date** (editable), **Vendor Invoice Amount** (editable), **Quantity**, **Price**, **Amount**, **Calculation Base Amount**, **Calculation Base %**, **Billing Base Period**, **Billing Rhythm**. All other fields aren't editable.

3. **Details**
   - **Billing to Date** is calculated and preset based on the **Next Invoice Date** and **Billing Rhythm** settings from the vendor subscription contract line.
   - **Vendor Invoice Amount** is preset from the amount in the vendor subscription contract lines.
   - If either field is set by the user, **Selected** is automatically set to **YES**.

4. **Processing**
   - On confirmation (OK), billing lines are created (similar to **Create Invoice** in vendor subscription contract) with the relevant dates and amounts.
   - All worksheet lines are deleted after processing.
   - The **Recurring Billing** flag is set in the purchase invoice.
   - Only descriptions can be changed in invoice lines.
   
## Assign a purchase invoice line to a vendor contract line

Continue the contract invoicing process for vendor contracts based on an existing purchase invoice by connecting invoice lines to vendor contract lines.

### Sample scenario

The company receives an invoice from a supplier that belongs to a vendor subscription contract. The invoice is created automatically and presented to the accountant for review. The accountant needs to link the invoice lines with the contract elements (lines) and then process it without having to leave the purchase invoice, starting from the purchase invoice. This procedure ensures that the contract is updated correctly.

### How it works

1. **Assign Contract Line** action
   - Available in the purchase invoice line menu.
   - Opens a worksheet page showing all open vendor subscription contract lines for the current vendor, grouped by contract number (collapsible view).

2. **Worksheet Link Purchase Line with Contract Line**
   - **Selected:** Indicates the vendor subscription contract lines to connect to the invoice line.
   - Fields: **Contract No.**, **Your Reference**, **Type**, **No.**, **Description Subscription**, **Description Subscription Line**, **Next Invoice Date**, **Billing to Date** (editable), **Vendor Invoice Amount**, **Quantity**, **Price**, **Amount**, **Calculation Base Amount**, **Calculation Base %**, **Billing Base Period**, **Billing Rhythm**
   - Only **Selected** and **Billing to Date** are editable. Amounts are taken from the corresponding invoice lines and therefore aren't editable.

3. **Details**
   - **Billing to Date** is preset based on the **Next Invoice Date** and **Billing Rhythm** settings from the vendor subscription contract line.
   - **Vendor Invoice Amount** is preset from the purchase invoice line when **Selected** is set to **YES**.
   - If **Billing to Date** is changed, **Selected** is automatically set to **YES**.

4. **Processing**
   - On confirmation (OK), billing lines are created (similar to **Create Invoice** in vendor subscription contract) with the relevant dates and amounts.
   - All worksheet lines are deleted after processing.
   - The **Recurring Billing** flag is set in the purchase invoice.
   - Only descriptions can be changed in invoice lines.

## Best practices

- Use these features for recurring vendor invoices to ensure contract compliance and reduce manual entry.
- Review contract line assignments for accuracy before posting invoices.
- Utilize worksheet filters to quickly locate relevant contract lines.

## Related information

[Vendor Contracts](#)
[Recurring Billing](#)
