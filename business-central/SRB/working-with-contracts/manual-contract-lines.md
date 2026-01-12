---
title: Manually create contract lines
description: You can create contract lines manually for simple contract extension.
author: bholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 8052, 8070,
ms.date: 01/12/2026
ms.service: dynamics-365-business-central
---


# Manually create contract lines

Enable flexible contract management by manually creating contract lines for items or G/L accounts, supporting easy recurring invoicing and partial crediting. This feature streamlines contract setup and enhances control over subscription billing in Business Central.

Manually created contract lines let you create and invoice contract lines without prerequisites. This process supports scenarios such as recurring billing and partial crediting of previously invoiced amounts, improving accuracy and efficiency in subscription management.

## Key concepts

- **Subscription Contract Line:** An individual line within a customer or vendor subscription contract, which can be manually created and configured.
- **Subscription:** Automatically created when a subscription contract line of type “Item” or “G/L Account” is added.
- **Negative Quantity:** Used for crediting previously invoiced amounts.

## Create a contract line

Open a customer or vendor subscription contract and then, in the lines, select the type **Item** or **G/L Account** for a new line. Fill in the required fields:

- **No.** (Item or G/L Account number)
- **Subscription Line Start Date**
- **Billing Rhythm**
- **Billing Base Period**
- **Quantity**
- **Calculation Base**
- **Calculation Base %**

A corresponding subscription is created automatically after you fill in all mandatory fields. Then, the line can be invoiced as usual. If the line is deleted without further processing, such as invoicing, the corresponding subscription is also deleted automatically.

> [!NOTE]
> Mandatory fields are marked with a red asterisk. If any field is missing, the subscription isn't created and an error message shows in the respective field.

### Field details and defaults

- **Type:** Specifies the type of contract line (Item or G/L Account).
- **No.:** Specifies the item or G/L account to be invoiced recurringly.
- **Default Period Calculation:** Choose **Align to End of the Month** for manually created contract lines.
- **Created in Contract Line:** Indicates whether the subscription was created by manually by adding a contract line (system-controlled).

### Edit and delete contract lines

- Changes in contract line fields, such as the **Quantity** field, transfer to the subscription or subscription line.
- If multiple subscription lines exist, a notification displays.
- Changing the type of a contract line is treated as deleting the contract line.
- Before deletion, checks are performed:
  - If **Created in Contract Line** is **Yes** and no billing lines or archived billing lines exist, the subscription line is deleted with the contract line.
  - If archived billing lines exist, only the contract line is deleted,the subscription line remains.
  - If **Created in Contract Line** is **No**, no changes are made.

### Negative quantities

Negative quantities are allowed in subscription lines. When invoiced, the negative quantity is transferred to the billing line. If the total invoiced lines are positive, an invoice is created. Otherwise, a credit memo is created. Negative quantities transfer to archived billing lines and posted invoice lines when the invoice or credit memo is posted. Cancellation of posted invoice lines with negative quantities is handled the same way as for positive quantities.

#### Credit a previously invoiced amount

Create a new contract line with a negative quantity, for example, -1. Then set the end date so the line is only invoiced one time. The credit will be granted with the next regular invoice.

## Best Practices

- Use manual contract lines for flexible contract scenarios, such as ad-hoc item billing or partial crediting.
- Ensure all mandatory fields are completed to avoid errors during contract line creation.
- Regularly review contract lines and subscriptions for accuracy, especially after edits or deletions.

## Related information

[Subscription Billing Setup](#)
[Customer Contracts](#)
[Vendor Contracts](#)

