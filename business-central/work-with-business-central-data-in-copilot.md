---
title: Work with Business Central data in Microsoft Copilot
description: Learn what Microsoft Copilot can access in Business Central and how permissions and licensing affect its use of your business data.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to
ms.date: 10/02/2026
ms.update-cycle: 180-days
ms.custom: bap-template
ai-usage: ai-assisted
ms.collection:
  - bap-ai-copilot
  - get-started
---

# Work with Business Central data in Microsoft Copilot

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

After you learn the basics of Microsoft Copilot in [Use Microsoft Copilot in Business Central](chat-with-copilot.md), use this article to understand what Copilot can access and what it can do with your Business Central data.

When you use Copilot, keep these access, permission, and licensing principles in mind:

- Microsoft Copilot works on your behalf and can access only the Business Central data that you have permission to access. Your Business Central permissions determine which records and fields Copilot can use.
- Microsoft Copilot has read-only access to Business Central data. It can retrieve, summarize, and explain information, but it can't create, modify, or delete Business Central records.
- Having a Microsoft Copilot license doesn't give you access to additional Business Central data. The license provides additional Microsoft Copilot capabilities, such as access to work data through Work IQ, but your access to Business Central data remains governed by your Business Central permissions.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Find and analyze business data

Ask questions about customers, vendors, items, sales orders, purchase orders, and other business data in your company.

For example:

- `Show me the latest sales order for Adatum`
- `Show me customer ledger entries for Adatum from last month`
- `Which customers received the most discounts?`

## Learn how to complete tasks

Ask for explanations or guidance on Business Central concepts and processes.

For example:

- `How do I post a sales order?`
- `Explain dimensions.`
- `How do I save filters for later?`

## Understand pages and fields

Ask Copilot to explain pages, fields, and business concepts in Business Central.

For example:

- `What is the purpose of the Gen. Bus. Posting Group field?`
- `Explain the Inventory Setup page.`

## Get help for installed apps

Copilot can also help you understand functionality provided by apps installed in your environment.

For example:

- `How do I cancel a hotel reservation?`
- `How do I create a travel expense?`

## Explore more advanced scenarios

After you try the basic prompts, ask Copilot to compare information, identify patterns, and combine information from different sources. You can continue the conversation with follow-up questions to refine the response.

Copilot responses can be incomplete or incorrect. Review the cited sources and verify important amounts, calculations, and conclusions before you make a business decision.

### Analyze Business Central data

In the following scenarios, Copilot uses Business Central data that you have
permission to access.

#### Prioritize sales orders that need attention

If you're reviewing open orders, ask Copilot to identify the orders that might
need your attention and explain how it prioritized them.

For example:

```text
Show me my five most urgent open sales orders. Consider the requested 
delivery date and shipment date, explain why you prioritized each order, 
and include links to the orders.
```

You can then continue with a follow-up prompt:

```text
For those orders, summarize the items and quantities that might affect fulfillment.
```

This scenario can help you focus your review, but you should open the cited
orders and verify their current status before you take further action.

#### Review slow-moving inventory

If you want to understand which stocked items have had comparatively little
sales activity, try:

```text
Which items sold the least in the last three months and still have inventory 
on hand? Show the quantity sold, quantity on hand, and inventory value, and 
cite the records used.
```

You can follow up with:

```text
Which of these items represent the highest inventory value?
```

This scenario can help you identify items for further review. Verify calculated
values and the period Copilot used, especially when inventory transactions have
been posted recently.

### Combine Business Central data with information from the web

Microsoft Copilot can use current, publicly available information from the web when your organization allows web search. Web search in Microsoft Copilot is separate from the **Enable Bing Search** setting in Business Central.

Learn more about web search in [How web search works in Microsoft Copilot Chat and agents](https://support.microsoft.com/microsoft-365-copilot/how-web-search-works-in-microsoft-365-copilot-chat-and-agents).

#### Compare inventory value in another currency

If your inventory is valued in a currency other than the currency you want to report in, you can combine Business Central values with a current exchange rate from the web.

For example:

```text
Give me the top five items in inventory based on their inventory value, 
converted to DKK using the latest available exchange rate. Cite the 
Business Central records and the web source, and state the exchange-rate 
date and any assumptions you used.
```

Review the Business Central values, conversion rate, calculation, and effective
date before you use the result for financial reporting or decision-making.

#### Research external requirements before configuring Business Central

You can also use information from the web together with Business Central
product guidance. For example:

```text
Summarize the current sales tax considerations for Oregon and California, 
and explain which areas of sales tax setup in Business Central I should 
review. Separate external tax information from Business Central guidance 
and cite your sources.
```

External requirements can change. Verify tax, regulatory, or legal information
against current official sources and consult a qualified professional when
necessary.

### Combine Business Central data with your work data

> [!NOTE]
> The scenarios in this section require a Microsoft Copilot license and access to your Microsoft 365 work data through Work IQ. Copilot can reference only the emails, files, chats, meetings, and other work content that you already have permission to access.

#### Prepare for a customer meeting

If you have an upcoming meeting with a customer, Copilot can combine recent
Business Central information with relevant Microsoft 365 work content.

For example:

```text
I have a meeting with ADATUM tomorrow. Summarize their latest sales figures, 
open invoices, and recent sales orders from Business Central together with 
relevant recent emails and meeting notes. Cite each source and list any 
questions I might need to resolve before the meeting.
```

You can follow up with:

```text
Organize the information into customer highlights, open issues, 
and suggested discussion points.
```

Review the cited Business Central records, emails, and meeting content before
you use the summary.

#### Gather information for a credit-limit review

Copilot can gather information that might be relevant when you review a
customer's credit limit, but it shouldn't make the decision for you.

For example:

```text
Based on ADATUM's recent sales orders, current balance, payment history,
overdue invoices, and recent emails, summarize the evidence that could 
support or oppose reviewing their credit limit. Don't recommend or change 
a credit limit. Cite the records and messages used, and identify any 
information that is missing.
```

Use the response as supporting information only. Review the cited records,
follow your organization's credit-management policies, and make the final
decision through your established review and approval process.

## Related information

[Use Microsoft Copilot in Business Central](chat-with-copilot.md)  
[Microsoft Copilot in Business Central FAQ](chat-with-copilot-faq.md)  
[Configure Copilot and agent capabilities](enable-ai.md)  
[Responsible AI FAQ for chat with Copilot](faqs-chat-with-copilot.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
