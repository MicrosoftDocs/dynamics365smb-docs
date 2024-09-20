---
title: Suggest number series with Copilot
description: This article provides information about the AI technology used in Business Central.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.form:
ms.date: 09/18/2024
ms.service: dynamics-365-business-central
ms.collection: bap-ai-copilot
ms.custom: bap-template
---

# Suggest number series with Copilot

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

This article explains how you can quickly generate number series in [!INCLUDE [prod_short](includes/prod_short.md)] with assistance from Copilot. 

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Available languages

[!INCLUDE [copilot-geo-and-language-availability](includes/copilot-geo-and-language-availability.md)]

## Prerequisites

- Suggest number series assist is activated. An administrator must complete this task. [Learn more about how to configure Copilot and AI capabilities](enable-ai.md).
- You're familiar with number series in [!INCLUDE [prod_short](includes/prod_short.md)], as described in [Create number series](ui-create-number-series.md).

## About number series suggestions with Copilot

For each company you set up in [!INCLUDE [prod_short](includes/prod_short.md)], you must assign unique identifiers to things like:

- General ledger accounts
- Customer and vendor accounts
- Invoices and other documents

Numbering isn't only important for identification. A well-designed numbering system also makes the company more manageable and easier to analyze, and can reduce data entry errors.

By letting you use natural language or structured input, Copilot can reduce the time it takes to set up number series and make it easier to maintain them. For example, when you need to update year or month-based numbering for many draft and posted documents in [!INCLUDE [prod_short](includes/prod_short.md)].

## Set up number series

Copilot can help you create and update number series faster on the **No. Series** page. The **Generate** action opens the **Generate No. Series with Copilot** dialog, where you can enter a prompt to create new, or modify existing, number series.

To help you write the prompt, the **Create new** action in the **Generate No. Series with Copilot** dialog provides sets of prompt guides that you can use as inspiration.

When you choose **Generate**, Copilot creates proposals for one or more number series. You can review the proposals in the **No. Series Proposals** view. You can remove the proposals that you don't like, and edit the ones you do. When you're ready, you can choose **Keep it** to add or update a proposal. In addition, Copilot updates various setup pages with the number series you decided to keep.

## Update number series

In the **Generate No. Series with Copilot** dialog, the **Modify existing** action offers sets of prompt guides to help you write a prompt to update an existing number series.

When you choose **Generate**, Copilot updates one or more number series proposals. You can review the proposals in the **No. Series proposals** view. You can remove the proposals Copilot generated, and edit the ones you like. When you're ready, you can choose **Keep it** to add or update a proposal.

## See also

[FAQ for Suggest Number Series with Copilot (preview)](faq-suggest-number-series-with-copilot.md)  
[Troubleshoot Copilot and AI capabilities](ai-copilot-troubleshooting.md)  
[Responsible AI FAQ for bank reconciliation assist](faqs-bank-reconciliation.md)  
[Create number series](ui-create-number-series.md)  
