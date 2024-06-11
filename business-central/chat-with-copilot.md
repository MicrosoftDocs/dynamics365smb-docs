---
title: Chat with Copilot (preview)
description: Learn about how to use chat with Copilot to find data and get help in Business Central.
author: jswymer 
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to 
ms.date: 03/18/2024
ms.custom: bap-template 
ms.collection:
  - bap-ai-copilot
  - get-started
---

# Chat with Copilot (preview)

[!INCLUDE[preview-banner](includes/preview-banner.md)]

This article explains how to chat with Copilot to get answers about your company data and assistance with tasks and subject matters related to Business Central.​

[!INCLUDE[production-ready-preview-dynamics365](includes/production-ready-preview-dynamics365.md)]

## About chat with Copilot

Microsoft Copilot is the AI-powered assistant that helps spark creativity, boost productivity, and eliminate tedious tasks. You can chat with Copilot in Business Central to answer questions and find business data by expressing what you're looking for in natural language. You can use chat to:

- Find business data for the company you're working with in Business Central. Use chat to look up (and open) data about entities/records related to business processes, such as customers, vendors, sales orders, and items, and more. For example, ask Copilot: "Show me the latest sales order for Adatum."
- Explain a concept or get guidance on how to accomplish a task. For example, ask "Help me understand dimensions" or "How do I post a sales order."
- Understand the purpose and typical use of individual fields. When you choose **Ask Copilot** in a tooltip for a field, chat opens with an Explain prompt for the field name and Copilot provides information about it. Copilot links to the articles it referenced, so it's easy to verify the description.

  The answers that Copilot provides are based solely on the official Dynamics 365 Business Central documentation, which is available on Microsoft Learn at [Dynamics 365 Business Central documentation](/dynamics365/business-central/).

Chat with Copilot circumvents the need to navigate the user interface or product help, which can save time and increase productivity.
  
> [Watch video](https://go.microsoft.com/fwlink/?linkid=2250609)

## Prerequisites

- Chat with Copilot capability is activated. This task is done by an administrator. [Learn more about configuring Copilot and AI capabilities](enable-ai.md).
- The display language in Business Central is set to one the following English locales: en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA. [Learn more about changing the language](ui-change-basic-settings.md#language).
- Your Business Central environment is in any country/region except Canada (this feature isn't yet available in Canada).

## Get started using chat with Copilot

1. In the upper-right corner of the screen, select the ![Shows the icon for chat with Copilot](media/chat-copilot-icon.png) **Copilot** icon ![Shows cllour number 1](media/callout-number-1.svg).

   The **Copilot** pane displays on the right as illustrated in the following figure:

    ![Shows the icon for chat with Copilot pane with callouts](media/chat-with-copilot-pane.svg)

1. In the **Ask a question** box at the bottom ![Shows callout number 2](media/callout-number-2.svg), enter your question, and then select the arrowhead or press <kbd>Enter</kbd> to get an answer.

   The text you enter, which is often referred to as a *prompt* in terms of Copilot, can be in the form of a question, statement, or command.

   > [!TIP]
   > Copilot includes a couple of features that can help your write questions:
   > - To get started on formulating a question, select one of the prompt guides&mdash;**Find**, **Explain**, or **Guide**&mdash;available the top of the pane ![Shows callout number 3](media/callout-number-3.svg) or from the ![Shows prompt guide icon](media/prompt-guide-icon.png) **View Prompts**  icon above **Ask a question** box ![Shows callout number 4](media/callout-number-4.svg). Prompt guides are predefined short phrases that begin a question or prompt. Apart from saving you time, they're designed to guide Copilot's responses toward a category of answers. They also help you understand how to phrase questions to get the best responses.
   > - Select the prompt suggestions above the **View prompts** button ![Shows callout number 5](media/callout-number-5.svg) to automatically ask a predefined question to get insight into how the questions and answers work. Prompt suggestions are only available when you're using the CRONUS demonstration company.

1. Review the answers displayed in the Copilot pane ![Shows callout number 6](media/callout-number-6.svg).

   Depending on your question, the answer can contain text, links to records or pages in Business Central, and links to Business Central help articles on Microsoft Learn.

1. Ask another question to refine the answer.

   Chat remembers the context, which means that you don't have to repeat key points from the original question.

## Clear chat to start over

If you want to switch to a different topic of conversation with Copilot, select the ![Shows the clear chat icon](media/clear-chat-icon.png) **Start a new Copilot chat session**  icon at the bottom of the Copilot pane above the question box. This action clears Copilot's memory of your last few messages. Starting over is often helpful after a lengthy conversation with many messages, and it can help Copilot deliver more accurate answers.

The chat is also cleared if you close or sign out of Business Central.

## <a name="tips"></a>Get the most out of your questions

This section provides ways you can improve the answers you get from Copilot.

- Ask clear and specific questions.
- Be concise and avoid long sentences or multiple sentences.
- Ask one question at a time. <!--Avoid asking about multiple questions in one message.-->
- Use natural language, expressing the questions in a friendly and conversational manner.
- Use keywords, phrases, and terms that you know are used in Business Central, either in the app or documentation.
- If the initial response doesn't fully answer your questions, ask follow-up questions or rephrase the last question.
- If you're asking a question on a different subject matter than previous question, clear the current chat session to start over.

## Example prompts

Your questions to Copilot naturally vary depending on your role, current task, the processes that your organization follows, and how you express yourself in words. The following are examples that showcase different ways of asking questions in the chat pane that can inspire you to write your own questions based on your own unique situation.

Prompt: `Find the Item with Description 'ATHENS Desk'`

In this example, you give clear instructions for Copilot to locate a single record. For example, you hint that the record is found in the Item list. You indicate the field 'Description' must be a specific text that you have typed using quotes and with correct capitalization. Copilot usually responds accurately when given a few precise hints, but you can also use more casual language as in the next example.

Prompt: `give me the latest invoice for adatum`

In this example, you ask Copilot to locate a record, but the question is less precise and might result in a less accurate answer. Copilot can often understand, or guess, that the invoice you're looking for isn't a purchase invoice but a sales invoice from the Posted Sales Invoice list. Copilot would also need to match `adatum` with `Adatum Corporation`, that is the full and precise name for the sell-to Customer name associated with the invoice.

Prompt: `Show me customer ledger entries for Adatum from about three weeks ago`

In this example, you ask copilot to solve a common date puzzle that typically requires you to open a calendar for reference, or to use advanced date range filters. Copilot can usually understand common expressions and business terms.

Prompt: `How does I save my filterrings to do them later?`

In this example, you ask Copilot for guidance on how to perform some task in Business Central. Copilot can usually understand the intent of your question, even if there are a few grammatical errors, spelling mistakes or abbreviations.

## Provide feedback on answers

You can rate the answers you get from Copilot by using the like (thumbs up) button for good rating or the dislike (thumbs down) button for a poor rating. When you select the dislike button, you can choose a reason, including inaccurate, inappropriate, or other. This information can help us improve suggestions.

<!--
1. If you want help getting you're question started, select the prompts either from the **Find**, **Explain**, or **Guide** buttons at the top of the Coplit pane or use the **View Prompts** menu above **Ask a question** box at the bottom.

   Prompts are predefined short phrases that start a question. Apart from saving you time, they're designed to target responses to specific categories. They also help you undestand how you can phrase questions to get the responses.-->
## See also

[Troubleshoot Copilot and AI capabilities](ai-copilot-troubleshooting.md)  
[Configure Copilot and AI capabilities](enable-ai.md)  
[Responsible AI FAQ for chat with Copilot](faqs-chat-with-copilot.md)  
[Resources for help in Business Central](product-help-and-support.md)  
