---
title: Chat with Copilot FAQ
description:  Learn how to chat with Copilot in Business Central. Find answers to common questions about chat features, settings, and limitations. 
author: jswymer
ms.author: jswymer
ms.reviewer: solsen
ms.topic: faq
ms.collection:
  - bap-ai-copilot
ms.date: 07/04/2025
ms.custom: bap-template jswymer
---
# Chat with Copilot FAQ

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

This article answers some common questions about chatting with Copilot in [!INCLUDE[prod_short](includes/prod_short.md)]. For questions related to AI and chat, consult [Responsible AI FAQs for chat with Copilot](faqs-chat-with-copilot.md).

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Can admins grant or deny permission to individual users to get access to chat?

Starting in 2025 release wave 1 (update 26.0), admins can control precisely who has access to Chat with Copilot. Learn more in [Configure Copilot and agent capabilities](enable-ai.md#granting-user-access).

## Can Copilot answer questions about any records? 

When you chat with Copilot about records and pages, Copilot searches your company data within [!INCLUDE[prod_short](includes/prod_short.md)] on your behalf and can only access the data you have permission to access. [!INCLUDE[prod_short](includes/prod_short.md)]'s extensive security, privacy, and compliance controls also apply to Copilot. For example, you can't ask Copilot to show masked or secret fields or retrieve records controlled by record-level security.

## Is chat available on tablet, phone, or other form factors?

No, the chat pane is only available on the [!INCLUDE[web_client](includes/web_client.md)].

## In which countries or regions can I chat with Copilot?

Starting in update 25.4, chat is available in all [!INCLUDE[prod_short](includes/prod_short.md)] countries and regions. If you're unable to access the chat pane, find the answer in [What can I do if the chat pane doesn't show?](#what-can-i-do-if-the-chat-pane-doesnt-show)

## I don't use Business Central in English. What are my options?

As of January 2025, chat is available no matter which language you use in [!INCLUDE[prod_short](includes/prod_short.md)].

[!INCLUDE[copilot-language-support-en-only](includes/copilot-language-support-en-only.md)]

## Does chat work with my customizations?

It depends on the type of question you ask Copilot. For example:

- If you ask questions to find records, it can find records in your custom tables or find and filter custom fields.
- If you ask Copilot for an explanation or guidance, it an provide answers about functionality from the apps that you have installed to [!INCLUDE[prod_short](includes/prod_short.md)].

Learn how to improve Copilot output as a developer in [Influencing Copilot and agents without extending them](/dynamics365/business-central/dev-itpro/developer/copilot-and-agents-influence-without-extending).

## How does Copilot locate records? 

When you ask to find a single record, multiple records, or a field from a record, Copilot uses various mechanisms to search for this information. Copilot generates the appropriate sorting and filtering on list pages and their corresponding source tables. It uses the fields on the page and fields on the underlying tables as part of these operations and in its responses.

## Does Copilot have access to all fields on a table? 

No. Copilot has access to most but not all fields when finding records. For example, it excludes fields that might contain passwords or other secrets. Learn which field data types are excluded in [Influencing Copilot and agents without extending them](/dynamics365/business-central/dev-itpro/developer/copilot-and-agents-influence-without-extending).

Similarly, when you ask Copilot to show a specific field from a record, some fields are excluded and might not be part of Copilot’s response. For example, if your admin hasn't given you permission to personalize Business Central, Copilot shows only the fields typically displayed by default on the list pages.

## How do I open a record or page from chat?

When you ask Copilot to find records in [!INCLUDE[prod_short](includes/prod_short.md)], it shows any records it finds as selectable tiles or links in the chat pane. While in preview, Copilot doesn't automatically navigate to any page.

## Why do I get different answers from Copilot for the same question?

Copilot might occasionally answer in different ways. Answers aren't always identical.

## How do I use the Copy function on chat messages?

You can use the Copy button to copy a message from earlier in your conversation with Copilot, paste it into the input box to try again or try a variation of your message to Copilot. When Copilot provides a record summary in the Copilot pane, this can also be copied using a Copy menu item.

## Can I customize or extend chat?

While in preview, the chat pane and Copilot's responses can't be modified directly through customization, add-ins, tools, or personalization. However, Chat is ready to work with data and Help from your installed apps. Learn about how to influence Copilot output as a developer in [Influencing Copilot and agents without extending them](/dynamics365/business-central/dev-itpro/developer/copilot-and-agents-influence-without-extending).

## Does Copilot search for data in other companies or environments?

Copilot only searches for records in the company you're currently signed into. It doesn't search for data across multiple environments or companies.

## How does chat treat data residency? 

The chat feature relies on Azure OpenAI Service for AI and Microsoft Learn for online documentation and Bing Search to provide answers about any apps you installed. 

- Azure OpenAI Service  
  Learn more about data residency and Azure OpenAI Service in [Azure OpenAI Service and Business Central data](azure-openai-data.md) and [Copilot data movement across geographies](ai-copilot-data-movement.md).

- Microsoft Learn online service  
  Endpoints are available in the US, Switzerland, and Europe Azure geographies. For EU customers, this means their data never leaves the EU Data Boundary, and [!INCLUDE[prod_short](includes/prod_short.md)] always connects to endpoints in Switzerland or Europe Azure geographies.

  If your [!INCLUDE[prod_short](includes/prod_short.md)] environment is deployed to any other Azure geography, [!INCLUDE[prod_short](includes/prod_short.md)] connects to the Microsoft Learn online service outside your environment's geographic region or compliance boundary. When you use chat to ask for explanations on how to do things in [!INCLUDE[prod_short](includes/prod_short.md)], only a few search keywords derived from your message to Copilot are sent to the Microsoft Learn online service in a different Azure geography. They're processed and not stored for more than one day.

  To prevent chat from connecting to the Microsoft Learn online service, deactivate the chat feature using the **Copilot & agent capabilities** page. Learn more in [Configure Copilot and agent capabilities](enable-ai.md#activate-features).
- Bing Search  
  Service endpoints are available in the US only and Bing Search operates under different terms. If your [!INCLUDE[prod_short](includes/prod_short.md)] environment is deployed to any other Azure geography, [!INCLUDE[prod_short](includes/prod_short.md)] connects to the Bing Search service outside your environment’s geographic region or compliance boundary. When you use chat to ask for explanations about add-on apps, only the input prompt is to the Bing Search service. This is processed and not stored for more than one day. 
 
  To prevent chat from connecting to the Bing Search service, turn of the Enable Bing Search switch from the Copilot & agent capabilities page. Learn more about how Copilot searches the web using Bing in [Searching the web with Copilot (preview)](ai-search-web-copilot.md). 

## What can I do if the chat pane doesn't show?

- Make sure your [!INCLUDE[prod_short](includes/prod_short.md)] is version 25.4 or later.
- For Business Central versions 25.4 to 25.5, make sure the entry for "Chat with Copilot" is enabled for all users in the **Feature Management** page.
- Make sure you have permission to chat with Copilot. Learn more in [Configure Copilot & agent capabilities](enable-ai.md#granting-user-access).
- For Business Central version 26 and later, make sure **Chat** is active in the **Copilot & agent capabilities** page. In some countries and regions, Chat with Copilot isn't active by default. Learn more in [Configure Copilot & agent capabilities](enable-ai.md).

## How is Microsoft improving chat with Copilot?

We're continually working on improving reliability and response time. We announced the next expansion of chat where Copilot can answer questions about how to use installed add-on apps. Learn more in [Chat with Copilot to learn how to use installed add-on apps](/dynamics365/release-plan/2025wave1/smb/dynamics365-business-central/chat-copilot-learn-use-installed-add-on-apps).

We encourage administrators to try out experimental features on sandbox environments. To experience the latest improvements to chat, enable the **Feature: Enables advanced navigation (not data) search capabilities by utilizing semantic similarity search on application metadata.** key on the **Feature Management** page. This feature uses superior AI technology to match user inquiries with the names of pages, fields, and tables. Learn more in [Use semantic search to find pages and reports with Copilot chat](/dynamics365/business-central/dev-itpro/developer/semantic-search-feature-key).

We look forward to getting your feedback about how Copilot can provide better assistance to your workday.

## Why does Copilot only show three records in the chat pane?

When you ask Copilot to find records, the way you phrase the question determines how Copilot identifies and applies filters on pages to find what you are looking for. To keep answers concise, the chat pane displays a maximum of three record tiles, even when Copilot finds more relevant records.

## Why does Copilot give incorrect answers to calculations?

While in preview, chat with Copilot can help you find records, explain concepts, and guide you to how to complete tasks in [!INCLUDE[prod_short](includes/prod_short.md)]. Other use cases aren't supported, such as adding up a field across records or calculating the average monthly amount. We hope to add basic mathematics abilities to Copilot in the future.

## Can I use speech instead of typing my prompts?

You can chat with Copilot by using voice typing to talk instead of type your words in the chat pane. Voice typing uses online speech recognition and is available with Windows. To use voice, activate the chat message box, then use the <kbd>Windows</kbd>+<kbd>H</kbd> shortcut and start speaking. Learn more at [Use voice typing to talk instead of type on your PC](https://support.microsoft.com/windows/use-voice-typing-to-talk-instead-of-type-on-your-pc-fec94565-c4bd-329d-e59a-af033fa5689f).

## Next steps

- [Chat with Copilot (preview)](chat-with-copilot.md)
