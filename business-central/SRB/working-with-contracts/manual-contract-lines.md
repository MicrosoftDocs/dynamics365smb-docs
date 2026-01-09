---
title: Manual Contract Lines in Subscription Billing
description: You can create contract lines manually for simple contract extension.
author: TobiSIT
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 8052, 8070,
ms.date: 12/16/2025
ms.service: dynamics-365-business-central
---


# Manual Contract Lines in Subscription Billing

Enable flexible contract management by manually creating contract lines for items or G/L accounts, supporting easy recurring invoicing and partial crediting. This feature streamlines contract setup and enhances control over subscription billing in Business Central.

## Overview

Manually created contract lines allow users to create and invoice contract lines without prerequisites. This supports scenarios such as recurring billing and partial crediting of previously invoiced amounts, improving accuracy and efficiency in subscription management.

## Prerequisites

- Access to the Subscription Billing module.
- Permissions to create and edit contracts and contract lines.

## Key Concepts

- **Subscription Contract Line:** An individual line within a customer or vendor subscription contract, which can be manually created and configured.
- **Subscription:** Automatically created when a subscription contract line of type “Item” or “G/L Account” is added.
- **Negative Quantity:** Used for crediting previously invoiced amounts.

## How to Create Manual Contract Lines

### Creating a Contract Line

Open a customer or vendor subscription contract and then, in the lines, select the type ("Item" or "G/L Account") for a new line.
- Enter the required fields:
  - **No.** (Item or G/L Account number)
  - **Subscription Line Start Date**
  - **Billing Rhythm**
  - **Billing Base Period**
  - **Quantity**
  - **Calculation Base**
  - **Calculation Base %**
- A corresponding subscription is created automatically once all mandatory fields are filled. Then, the line can be invoiced as usual. If the line is deleted without further processing (e.g., invoicing), the corresponding subscription is also deleted automatically.

> [!NOTE]
> Mandatory fields are marked with a red asterisk. If any field is missing, the subscription is not created and an error message is shown at the respective field.

### Field Details and Defaults

- **Type:** Specifies the type of contract line (Item or G/L Account).
- **No.:** Specifies the Item or G/L Account to be invoiced recurringly.
- **Default Period Calculation:** Set to “Align to End of the Month” for manually created contract lines.
- **Created in Contract Line:** Indicates if the subscription was created by manually adding a contract line (system-controlled).

### Editing and Deleting Contract Lines

- Changes in contract line fields (e.g., quantity) are transferred to the subscription or subscription line.
- If multiple subscription lines exist, a corresponding notification will be displayed.
- Changing the type of a contract line is treated as deleting the contract line.
- Before deletion, checks are performed:
  - If “Created in Contract Line” is Yes and no billing lines or archived billing lines exist, the subscription line is deleted with the contract line.
  - If archived billing lines exist, only the contract line is deleted,the subscription line remains.
  - If “Created in Contract Line” is No, no changes are made.

### Negative Quantities

- Negative quantities are basically allowed in subscription lines.
- When invoiced, the negative quantity is transferred to the billing line.
- If the total invoiced lines are positive, an invoice is created; otherwise, a credit memo is created.
- Negative quantities are transferred to archived billing lines and posted invoice lines when the invoice or credit memo is posted.
- Cancellation of posted invoice lines with negative quantities is handled the same way as for positive quantities.

#### Crediting a Previously Invoiced Amount

- Create a new contract line with a negative quantity (e.g., -1).
- Set the end date so the line is only invoiced once.
- The credit will be granted with the next regular invoice.

## Best Practices

- Use manual contract lines for flexible contract scenarios, such as ad-hoc item billing or partial crediting.
- Ensure all mandatory fields are completed to avoid errors during contract line creation.
- Regularly review contract lines and subscriptions for accuracy, especially after edits or deletions.

## Related Topics

- [Subscription Billing Setup](#)
- [Customer Contracts](#)
- [Vendor Contracts](#)
-
