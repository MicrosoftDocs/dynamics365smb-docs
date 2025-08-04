---
title: Deliver sales invoices with French specifics
description: Learn how to set up and work with France-specific information in French sales invoices.
author: altotovi
ms.author: altotovi
ms.reviewer: v-soumramani
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 04/14/2025
ms.custom: bap-template
ms.search.keywords: sales, invoice, order, siren, French version
ms.search.form: 21, 42, 43, 44
---

# Deliver sales invoices with French specifics

This article explains how to set up and work with sales invoice information that is specific to France.

## Create a new customer

When you create a new customer in France, some specific information must be included. To create the **Customer** card correctly, on the **Invoicing** FastTab, enter a value in the **SIREN No.** field. This number is required to print sales invoices.

If the new **Customer** card is created from an existing **Contact** card, the value in the **SIREN No.** field is copied from the contact.

## Work with the sales documents

When you create a new sales document, you can select whether to print value-added tax (VAT) that is paid on debts. To print this information, on the **Invoice Details** FastTab, enable the **VAT Paid on Debts** field.

When you print sales documents, [!INCLUDE[prod_long](../../includes/prod_long.md)] automatically indicates, in the comment, whether a sales invoice includes only goods, only services, or both goods and services. This determination is based on the value of the **Type** field on the **Item** card (**Inventory** or **Service**), the resources that are used, or the general ledger account.

> [!NOTE]
> If you use an alternative address in the sales invoice, [!INCLUDE[prod_long](../../includes/prod_long.md)] automatically shows this address in the comment of the printed report.

You can find training information about sales invoices on [Microsoft Learn](/learn/modules/process-intrastat-dynamics-365-business-central/index).

## Related information

- [Financial Management](../../finance.md)  
- [Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
