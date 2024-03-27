---
title: Map E-Documents to Purchase Order Lines with Copilot
description: Learn about how to use Copilot to map e-documents to purchase order lines.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: altotovi
ms.topic: how-to 
ms.collection:
  - get-started
  - bap-ai-copilot
ms.date: 02/23/2024
ms.custom: bap-template 
---

# Map e-documents to purchase order lines with Copilot (preview)

[!INCLUDE[preview-banner](includes/preview-banner.md)]

As procurement processes become more digital, the e-documents feature in Business Central plays a key role in automating the vendor invoice reception and processing. Copilot can assist in this process by improving the mapping and matching of vendor invoices to purchase orders. This reduces time-consuming tasks that would normally include extensive search, lookup, and data entry. The benefit is compounded by the fact that vendor invoices often don't relate exactly with purchase orders, in which case Copilot is better positioned to identify the corresponding purchase orders. Enhanced matching capabilities particularly benefit small and midsized organizations that need efficient document tracking for purchase order lines. Copilot is the AI-powered assistant for work that boosts creativity and improves productivity for Business Central users.

In the initial release of the **e-document** app, we introduced fundamental scenarios for e-documents for the entire sales process. However, there's a need for enhancements and automation in handling the received documents, especially in the context of purchase processes. Copilot refines how you manage e-documents in the purchase process, particularly with respect to purchase orders. The e-documents framework lets you specify the type of purchase document to create for each vendor when you receive e-invoices from them. Previously, the only option was to create a purchase invoice, either as a document or a general ledger journal.

You can now update an existing purchase order in Business Central with the information received in the e-invoice.

> [!NOTE]
> - This feature is available as a production-ready preview for production and sandbox environments in any country localization, with the exception of Canada. Production-ready previews are subject to supplemental terms of use. For more information, see [Supplemental terms of use for Dynamics 365 preview](https://go.microsoft.com/fwlink/?linkid=2105274).
> - AI-generated content may be incorrect.

## Identify purchase orders

First, you can identify the purchase orders that you can automatically match.

## Map lines

Copilot helps you automatically match e-invoice lines with purchase order lines, and offers extra matching intelligence to improve the matches.

After they're matched and mapped, Business Central updates the matched purchase order with the relevant receipt information to ensure the right quantities are received on the order lines.

## See also

[E-Documents overview](finance-edocuments-overview.md)  
[Use e-documents in sales and purchases](finance-how-use-edocuments.md)  
[Troubleshoot Copilot and AI capabilities](ai-copilot-troubleshooting.md)  
[Responsible AI FAQ for bank reconciliation assist](faqs-bank-reconciliation.md)  
