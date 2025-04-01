---
title: Responsible AI FAQ for Chat with Copilot (preview)
description: This FAQ provides information about the AI technology used for chatting with Copilot in Business Central. It includes key considerations and details about how AI is used, how it was tested and evaluated, and any specific limitations.
ms.date: 04/01/2025
ms.custom: 
  - responsible-ai-faqs
ms.topic: article
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.search.keywords: copilot, AI, chat 
---
# Responsible AI FAQ for Chat with Copilot (preview)

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

These frequently asked questions (FAQ) describe the AI impact of Chat with Copilot in [!INCLUDE[prod_short](includes/prod_short.md)]. If you're interested in general questions about using the feature, see [FAQ for chat with Copilot](chat-with-copilot-faq.md).

## What is Chat with Copilot?

Microsoft Copilot is an AI-powered assistant that helps you be more creative, productive, and efficient. You can chat with Copilot in Business Central to get answers and insights about [!INCLUDE[prod_short](includes/prod_short.md)] and your business data by typing what you want to know in natural language.

Chat with Copilot, also called chat, is an interactive feature that answers your questions without requiring you to navigate the user interface or the product documentation. The Copilot pane is available from anywhere in the [!INCLUDE[prod_short](includes/prod_short.md)] client.

You can ask questions in natural language, like "How do I deliver goods to my customers directly from my vendors?" or "Do we have any office chairs in stock for under $600?" In response, Copilot provides answers in natural language. Depending on the questions, answers can include plain text, links to records or pages in [!INCLUDE[prod_short](includes/prod_short.md)], and links to [!INCLUDE[prod_short](includes/prod_short.md)] help articles on Microsoft Learn.

## What are the capabilities of Chat with Copilot?

You can chat with Copilot to get answers to the following classes of questions:

### Explain and guide

You can ask Copilot to explain a specific concept related to [!INCLUDE[prod_short](includes/prod_short.md)], like what are dimensions, or provide guidance on how to complete a task, like how to post a sales order. Copilot searches the official [!INCLUDE[prod_short](includes/prod_short.md)] documentation published by Microsoft, and provides an answer based on the documentation.

- Copilot uses the knowledge on Microsoft Learn (not a broad web search) to semantically search only Dynamics 365 [!INCLUDE[prod_short](includes/prod_short.md)] documentation on Microsoft Learn. This includes product documentation, release plans, local functionality content, and troubleshooting content.

- Copilot doesn't take action, create new data, or modify any configuration. It simply summarizes any paragraphs it finds on Microsoft Learn that match the question or prompt in chat.

### Find business data and related pages

You can ask Copilot to locate pages by name or request records based on specific fields and constraints. If Copilot finds a match, it responds with a link to the relevant record or page, which you can then select to open. Chat with Copilot works closely with analysis assist to generate data analysis tabs directly from the Chat pane, helping you gain insights into your data. This approach is used whenever you ask questions best illustrated by grouped records or simple calculations, such as totals or averages.

- Copilot converts the natural language input into a query consisting of a table search, sort, and filter criteria.

  The capability uses [!INCLUDE[prod_short](includes/prod_short.md)]'s native data search capabilities to find matching data from tables within the companies database. The search runs under your own identity for security and compliance. It doesn't search outside of the [!INCLUDE[prod_short](includes/prod_short.md)] database.

- Copilot doesn't take action, create new data, or modify any configuration. It only summarizes the records received from the [!INCLUDE[prod_short](includes/prod_short.md)] native data search.

## What is the intended use of Chat with Copilot?

Chat is designed for enterprise use and answering questions that relate to [!INCLUDE[prod_short](includes/prod_short.md)] and the business data it contains. The feature helps you solve common tasks such as finding records or getting guidance. You can express yourself in your own words, making your work easier and more accessible when working with [!INCLUDE[prod_short](includes/prod_short.md)].

## How was Chat with Copilot evaluated? What metrics are used to measure performance?

- The feature underwent extensive testing during which numerous English language texts covering a broad range of topics and styles of expressing intent were given to Copilot. The outcomes were evaluated against accuracy, relevance, and safety.
  
- The feature is built in accordance with Microsoft's Responsible AI Standard. [Learn more about responsible AI from Microsoft](https://aka.ms/RAI).

## How does Microsoft monitor the quality of generated content?

Microsoft has various systems in place to ensure that content generated by Copilot is of the highest quality, detect abuse, and ensure safety for our customers and their data.

You can provide feedback to every Copilot response and report inaccurate or inappropriate content to help Microsoft improve this feature. 

- You can provide feedback by using the like (thumbs up) or dislike (thumbs down) icon on the **Copilot** pane in [!INCLUDE[prod_short](includes/prod_short.md)].
  
- We analyze and utilize your feedback on the feature to help us improve responses.
  
- If you encounter inappropriate generated content, report it to Microsoft by using this feedback form: [Report abuse](https://go.microsoft.com/fwlink/?linkid=2249810).
  
- Microsoft might disable the Copilot features for selected customers if abuse of the functionality is detected.

## What are the limitations of Chat with Copilot? How can users minimize the impact of the Chat with Copilot limitations when using the system?

- General limitations of AI

  AI systems are valuable tools but they're nondeterministic. The content they generate might not be accurate. So, it's important to use your judgment to review and verify responses Copilot before making decisions that could affect stakeholders like customers and partners. For most responses, Copilot also includes citations or reference links that you can use to quickly verify whether Copilot gives a correct answer. For example, when asked how to perform some task, Copilot includes links to the source article. When asked to find a record based on specific criteria, Copilot includes links that describe the list page it identified as the topic of conversation. It also provides information about any filters or sorting that was applied to reach an answer.

- Language limitations

  - [!INCLUDE[copilot-language-support-en-only](includes/copilot-language-support-en-only.md)]

    If you chat with Copilot in a language other than English, Copilot might either respond in the same language, in English, or not at all. While in preview, chat is intended for use with the English language only.

  - The quality of answers can be lower under the following conditions:
    - The language of chat messages to Copilot is something other than en-US.
    - The language setting for the user in [!INCLUDE[prod_short](includes/prod_short.md)] differs from the primary language of the data in the [!INCLUDE[prod_short](includes/prod_short.md)] database.

- Specific industry, product, and topic limitations

   Chat includes built-in safety mechanisms that prevent the undesirable generation of harmful content, such as sexually explicit content or incitement of violence. Sometimes, customers operate in industries, sell products and services, or work with processes that naturally overlap with what might be considered inappropriate in other contexts, or work with data that might trigger these safeguards. Chat might not perform as well in these cases.

## What data does Chat with Copilot collect and how is it used

Microsoft doesn't use your company data, including the text you send to Copilot, to train the foundational AI models for the benefit of others. Company administrators have full control to govern this data that is part of their Azure subscription. Because administrators or others in your company might have access to this data as determined by your employer, we recommend you don't enter sensitive data such as passwords or other secrets.

## What does Chat with Copilot offer for security

Chat is designed to be secure and executes under the user's identity, inheriting all security permissions and other restrictions and never operating outside of [!INCLUDE[prod_short](includes/prod_short.md)]'s platform security. This design means that Copilot can only access data that you have access to.

For users with SUPER permission, chat can more easily locate unsecured data that's typically harder to get to for other users. Organizations that don't apply [!INCLUDE[prod_short](includes/prod_short.md)]'s security model to restrict which tables and objects each user or user role has access to, might be at elevated risk when using chat. Therefore, we recommend that your organization either implements [!INCLUDE[prod_short](includes/prod_short.md)]'s security model or deactivates chat.

## Related information

[Chat with Copilot (preview)](chat-with-copilot.md)  
[Analyze data in lists with help from Copilot (preview)](analysis-assist.md)  