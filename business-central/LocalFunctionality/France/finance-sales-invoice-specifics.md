---
title: Deliver sales invoice with French specifics
description: Learn how to set up and work with specifics in French sales invoices.
author: altotovi
ms.author: altotovi
ms.reviewer: kfend
ms.service: dynamics365-business-central
ms.topic: how-to
ms.date: 05/26/2023
ms.custom: bap-template
ms.search.keywords: sales, invoice, order, siren 
ms.search.form: 21, 42, 43, 44
---

# Deliver sales invoice with French specifics
This article explains how to set up and work with the sales invoice information that is specific to France.

## Create a new customer  

When you create a new customer in France, there is some information that must be included. To create the **Customer** card properly, on the **Invoicing** FastTab, enter a value in the **SIREN No.** field. This number is mandatory for printing sales invoices.  

If the new **Customer** card is created from existing **Contact** card, the value in the **SIREN No.** field will be copied from the contact.

## Working with the sales documents 

When you create new sales document, you can select whether to print *VAT paid on debts*. To do this, enable the **VAT Paid on Debts** field on the **Invoice Details** FastTab. 

When you print sales documents, [!INCLUDE[prod_long](includes/prod_long.md)] automatically shows in the comment if a sales invoice includes only goods, only services, or both of them. This determiniation depends on the **Type** field option on the **Item** card (Inventory or Service), the resources used, or the General ledger account.  

> [!NOTE]
> If you use an alternative address in the sales invoice, [!INCLUDE[prod_long](includes/prod_long.md)] automatically shows this address in the comment of printed report.  

You can find training information about sales invoices at [Microsoft Learn](/learn/modules/process-intrastat-dynamics-365-business-central/index).

## See also

[Financial Management](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
