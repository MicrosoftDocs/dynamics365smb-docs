---
title: Suggest number series with Copilot (preview)
description: This article provides information about the AI technology used in Business Central.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: jswymer
ms.topic: article
ms.search.form:
ms.date: 04/01/2025
ms.service: dynamics-365-business-central
ms.collection: bap-ai-copilot
ms.custom: bap-template
---

# Suggest number series with Copilot (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

This article explains how you can quickly generate number series in [!INCLUDE [prod_short](includes/prod_short.md)] with assistance from Copilot.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Available languages

[!INCLUDE [copilot-geo-and-language-availability](includes/copilot-geo-and-language-availability.md)]

## Prerequisites

- The suggest number series feature is activated. An administrator must complete this task. [Learn more about how to configure Copilot and agent capabilities](enable-ai.md).
- You're familiar with number series in [!INCLUDE [prod_short](includes/prod_short.md)]. To learn more, go to [Create number series](ui-create-number-series.md).

## About number series suggestions with Copilot

For each company you set up in [!INCLUDE [prod_short](includes/prod_short.md)], you must assign unique identifiers to things like:

- General ledger accounts
- Customer and vendor accounts
- Invoices and other documents

Numbering isn't only important for identification. A well-designed numbering system also makes the company more manageable and easier to analyze, and can reduce data entry errors.

By letting you use natural language or structured input, Copilot can reduce the time it takes to set up number series and make it easier to maintain them. For example, when you need to update year or month-based numbering for many draft and posted documents in [!INCLUDE [prod_short](includes/prod_short.md)].

## Review the suggestions and refine your prompt

You can set up number series for one or more specific entities, such as items, or one or more feature areas (modules), such as Inventory, Finance, Sales, and Purchasing, and so on.

For specific entities, such as purchase orders, Copilot might also suggest blanket purchase orders and purchase return orders.

For feature areas, Copilot looks at the fields on the **Numbering** FastTab on the related setup page. For example, for Inventory, it looks at the FastTab on the **Inventory Setup** page. For Sales and Purchasing, it looks at the FastTab on the **Sales & Receivables** and **Purchases & Payables** pages. However, it also looks at related entities, which means it might suggest series for entities that aren't on the setup page. For example, when you create a series for Warehouse Management, Copilot might suggest a series for items.

We recommend that you carefully review the results and adjust your prompt to exclude unwanted series. For example, both the Warehouse and Inventory areas might suggest series for items. To avoid a conflict, you can exclude items in your prompt for one of those areas.

## Generate number series

Copilot can help you create and update number series on the **No. Series** page. The **Generate** action opens the **Generate No. Series with Copilot** dialog where you can enter a prompt.

To help you write the prompt, the Prompt Guide :::image type="content" source="media/prompt-guide-icon.png" alt-text="Show the Prompt Guide icon."::: button provides sets of prompts that you can use as-is, or as inspiration.

- Create entirely new number series.
- Change and update numbering in existing series.
- Create a new number series for the next year.

After you enter your prompt and choose **Generate**, Copilot creates proposals for one or more number series. You can review the proposals in the **No. Series Proposals** view. You can remove the proposals that you don't like, and edit the ones you do. When you're ready, you can choose **Keep it** to add or update a proposal. In addition, Copilot updates various setup pages with the number series you decided to keep.

## Examples of prompts

|Intent  |Prompt  |
|---------|---------|
|Create a number series that includes a year. For accountants, including a year on numbers for posted documents can make it easier to find hard copies in folders.     |Create contract credit memo number series. Make sure it includes the last two digits of the current year.         |
|Maintain number series and prepare for next year.     | Set up a contract credit memo number series in the service management module for the next year.        |
|Create number series in a completely empty company. This is where Copilot can save your hours, or even days, in new implementations.     | Create numbers series for the new company. Make sure all posted documents contain the last to digits of the current year.        |

## Related information

[FAQ for Suggest Number Series with Copilot (preview)](faq-suggest-number-series-with-copilot.md)  
[Troubleshoot Copilot and agent capabilities](ai-copilot-troubleshooting.md)  
[Responsible AI FAQ for bank reconciliation assist](faqs-bank-reconciliation.md)  
[Create number series](ui-create-number-series.md)  
