---
title:  Use Microsoft Copilot in Business Central (preview)
description: Learn how to use Microsoft Copilot to find data and get help in Business Central.
author: jswymer 
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to 
ms.date: 10/02/2026
ms.update-cycle: 180-days
ms.custom: bap-template 
ms.collection:
  - bap-ai-copilot
  - get-started
---

# Use Microsoft Copilot in Business Central (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

> [!NOTE]
> Microsoft Copilot replaces the previous Chat with Copilot experience starting in Business Central version 29. If you're using v28, learn more about about the previous experience in [Chat with Copilot (legacy)](chat-with-copilot-legacy.md).

This article explains how to use Microsoft Copilot to get answers about your company data and assistance with tasks and subject matters related to Business Central.​

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

[Microsoft Copilot](/copilot/overview) for apps is your next-generation AI assistant. It helps you explore and understand data in your apps through natural language conversations. Use Microsoft Copilot to boost productivity with AI-powered insights and navigation.

To learn about the broader Copilot experience, including its capabilities, navigation, and availability across devices, see [Get started with the Microsoft Copilot app](https://support.microsoft.com/en-us/microsoft-365-copilot/what-is-microsoft-copilot-app).

## Prerequisites

- The **Chat** capability must be active in your Business Central environment, and you must have permission to use it. Learn more in [Configure Copilot and agent capabilities](enable-ai.md).
- To access work data, like meetings, emails, chats, files, and more, via Work IQ, you must have a Microsoft Copilot license. Learn more in [How Copilot Chat works with and without a Microsoft Copilot license](https://support.microsoft.com/en-us/microsoft-365-copilot/how-copilot-chat-works-with-and-without-a-microsoft-365-copilot-license).

## Copilot pane

After Microsoft Copilot is enabled, you can access it through the Copilot button near the upper-right corner of the page.

:::image type="content" source="media/copilot-icon-in-header.png" alt-text="Screenshot that shows the Copilot button on a page.":::

You can expand or collapse the Microsoft Copilot pane as needed.

## Ask questions with Microsoft Copilot

Microsoft Copilot answers questions about your Business Central data. 

:::image type="content" source="media/microsoft-copilot-question-answer.png" alt-text="Screenshot that shows a question and response in Microsoft Copilot." lightbox="media/microsoft-copilot-question-answer.png":::

You can ask questions or give instructions. For example, enter `How do I release a sales order?` or `Show the latest invoices`. Learn more in [Work with Business Central data in Microsoft Copilot](work-with-business-central-data-in-copilot.md).

## Share your feedback

Help us improve Copilot responses by using the feedback controls on each response. Provide feedback for every response:

- If a response is high quality and helpful, select the thumbs up button.
- If a response is incorrect, incomplete, or not helpful, select the thumbs down button.

When you provide feedback, share as much information as possible. For example, include what you expected to see, what was missing or incorrect, and any relevant context. You can also send more context, which sends a lot more data to Microsoft as feedback. Admins can control whether users can send feedback to Microsoft. Learn more in [Manage Microsoft feedback for your organization](/privacy/microsoft-365/feedback/feedback-manage).

:::image type="content" source="media/microsoft-copilot-feedback.png" alt-text="Screenshot of Microsoft Copilot in a model-driven app, highlighting the thumbs up and thumbs down feedback buttons for a response." lightbox="media/microsoft-copilot-feedback.png":::

## Microsoft Copilot suggested questions

To help you get started, Microsoft Copilot suggests questions. Many include placeholders you can replace with appropriate text.

:::image type="content" source="media/microsoft-copilot-prompts.png" alt-text="Screenshot that shows suggested prompts that have placeholders." lightbox="media/microsoft-copilot-prompts.png":::

## Use agents in Microsoft Copilot

> [!IMPORTANT]
>
> If you select an agent in Microsoft Copilot, Copilot focuses on that agent instead of answering questions about your Business Central data. However, the agent can still use chat history. To ask questions about your Business Central data again, remove the explicit agent selection.

You can use any agent available in Microsoft Copilot directly from the side pane. When an agent is available within Microsoft Copilot, you can interact by either choosing it from the navigation panel or @ mentioning it.

:::image type="content" source="media/microsoft-copilot-opened-navigation.png" alt-text="Screenshot that shows how to open the Microsoft Copilot navigation panel with different agents displayed." lightbox="media/microsoft-copilot-opened-navigation.png":::

One of the benefits of @ mentioning an agent is that you can add or remove it from an ongoing conversation, which lets you have several agents collaborating in one conversation. When you select an agent from the navigation panel, you have a direct conversation only with the agent you selected.

:::image type="content" source="media/microsoft-copilot-at-mention.png" alt-text="Screenshot that shows how to @ mention agents in Microsoft Copilot.":::

## Navigate to pages using citations

When results have citations, select the citation result in the side pane to navigate to the page.

:::image type="content" source="media/microsoft-copilot-citation-nav.png" alt-text="Screenshot that shows a page that was navigated to after selecting a citation link." lightbox="media/microsoft-copilot-citation-nav.png":::

## Limitations

- Microsoft Copilot allows users to view data by using read-only operations. This capability means that you can only view data that matches your queries and can't make any changes. To make changes, customization with an agent is required.

- **Business Central agents aren't available from Microsoft Copilot.** You can't invoke Microsoft agents for Business Central or non-Microsoft agents built by using the Business Central agent framework from Microsoft Copilot. To use these agents, access them through their supported experiences in Business Central.

## Related information

[Microsoft Copilot in Business Central FAQ](chat-with-copilot-faq.md)
[Get started with the Microsoft Copilot app](https://support.microsoft.com/en-us/microsoft-365-copilot/what-is-microsoft-copilot-app)  
[Application Card: Microsoft Copilot in Business Central](microsoft-copilot-in-business-central-application-card.md)  
[Troubleshoot Copilot and agent capabilities](ai-copilot-troubleshooting.md)  
[Configure Copilot and agent capabilities](enable-ai.md)  
[Resources for help in Business Central](product-help-and-support.md)  
[Changing the language](ui-change-basic-settings.md#language)  
