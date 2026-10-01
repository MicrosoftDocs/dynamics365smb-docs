---
title: Responsible AI FAQ for Chat with Copilot (preview)
description: This FAQ provides information about the AI technology used for chatting with Copilot in Business Central. It includes key considerations and details about how AI is used, how it was tested and evaluated, and any specific limitations.
ms.date: 09/16/2026
ms.update-cycle: 180-days
ms.custom: 
  - responsible-ai-faqs
ms.topic: faq
ai-usage: ai-assisted
author: jswymer
ms.author: jswymer
ms.reviewer: solsen
ms.search.keywords: copilot, AI, chat 
ms.collection:
  - bap-ai-copilot
---
# Responsible AI FAQ for Chat with Copilot (preview) 

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

> [!IMPORTANT]
> This article applies to the legacy **Chat with Copilot** experience in Business Central versions up to 28. Starting with Business Central version 29.0, **Microsoft Copilot in Business Central** replaces Chat with Copilot.
>
> For responsible AI information about the new experience, see [Application card: Microsoft Copilot in Business Central](microsoft-copilot-in-business-central-application-card.md).

## What is Chat with Copilot?

Microsoft Copilot is an AI-powered assistant that helps you be more creative, productive, and efficient. You can chat with Copilot in Business Central to get answers and insights about [!INCLUDE[prod_short](includes/prod_short.md)] and your business data by typing what you want to know in natural language.

Chat with Copilot, also called chat, is an interactive feature that answers your questions without requiring you to navigate the user interface or online documentation. The Copilot pane is available from anywhere in the [!INCLUDE[prod_short](includes/prod_short.md)] client.

You can ask questions in natural language, like "How do I deliver goods to my customers directly from my vendors?" or "Do we have any office chairs in stock for under $600?" In response, Copilot provides answers in natural language. Depending on the questions, answers can include plain text, links to records or pages in [!INCLUDE[prod_short](includes/prod_short.md)], and links to [!INCLUDE[prod_short](includes/prod_short.md)] help articles on Microsoft Learn.

## What are the capabilities of Chat with Copilot?

You can chat with Copilot to get answers to the following classes of questions:

### Explain and guide

You can ask Copilot to explain a specific concept related to [!INCLUDE[prod_short](includes/prod_short.md)], like what are dimensions, or provide guidance on how to complete a task, like how to post a sales order. Copilot searches the official [!INCLUDE[prod_short](includes/prod_short.md)] documentation published by Microsoft, and provides an answer based on the documentation.

- Copilot uses the knowledge on Microsoft Learn (not a broad web search) to semantically search only Dynamics 365 [!INCLUDE[prod_short](includes/prod_short.md)] documentation on Microsoft Learn. This includes product documentation, release plans, local functionality content, and troubleshooting content.
- Copilot can also use knowledge from the non-Microsoft apps that your administrator installed to [!INCLUDE[prod_short](includes/prod_short.md)]. This knowledge source is provided by the app publisher as part of the app, so Copilot doesn't do a broad web search here either. 
- Copilot doesn't take action, create new data, or modify any configuration. It simply summarizes any paragraphs it finds on in online documentation that match the question or prompt in chat.

### Find business data and related pages

You can ask Copilot to locate pages by name or request records based on specific fields and constraints. If Copilot finds a match, it responds with a link to the relevant record or page, which you can then select to open. Copilot can also help with questions best answered by grouped records or simple calculations, such as totals or averages, using the data it can access in the company you're signed in to.

- Copilot converts the natural language input into a query consisting of a table search, sort, and filter criteria.

  The capability uses [!INCLUDE[prod_short](includes/prod_short.md)]'s native data search capabilities to find matching data from tables within the companies database. The search runs under your own identity for security and compliance. It doesn't search outside of the [!INCLUDE[prod_short](includes/prod_short.md)] database.

- Copilot doesn't take action, create new data, or modify any configuration. It only summarizes the records received from the [!INCLUDE[prod_short](includes/prod_short.md)] native data search.

## What is the intended use of Chat with Copilot?

Chat is designed for enterprise use and answering questions that relate to [!INCLUDE[prod_short](includes/prod_short.md)] and the business data it contains. The feature helps you solve common tasks such as finding records or getting guidance. You can express yourself in your own words, making your work easier and more accessible when working with [!INCLUDE[prod_short](includes/prod_short.md)].

## How was Chat with Copilot evaluated? What metrics are used to measure performance?

- The feature underwent extensive testing during which numerous English language texts covering a broad range of topics and styles of expressing intent were given to Copilot. The outcomes were evaluated against accuracy, relevance, and safety.
  
- The feature is built in accordance with Microsoft's Responsible AI Standard. [Learn more about responsible AI from Microsoft](https://aka.ms/RAI).

## How does Microsoft monitor the quality of generated content?

Microsoft has various systems in place to ensure that content generated by Copilot is high quality, detect abuse, and ensure safety for customers and their data.

To help Microsoft improve this feature, provide feedback to every Copilot response and report inaccurate or inappropriate content. 

- Use the like (thumbs up) or dislike (thumbs down) icon on the **Copilot** pane in [!INCLUDE[prod_short](includes/prod_short.md)] to provide feedback.
  
- Microsoft analyzes and uses your feedback on the feature to improve responses.
  
- If you encounter inappropriate generated content, report it to Microsoft by using this feedback form: [Report abuse](https://go.microsoft.com/fwlink/?linkid=2249810).
  
- If Microsoft detects abuse of the functionality, it might disable the Copilot features for selected customers.

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

## What does Chat with Copilot offer for security?

Chat is designed to be secure and runs under your identity. It inherits all your security permissions and other restrictions, and it never operates outside of [!INCLUDE[prod_short](includes/prod_short.md)]'s platform security. This design means that Copilot can only access data that you can access.

For users with SUPER permission, chat can more easily locate unsecured data that's typically harder to access for other users. If your organization doesn't apply [!INCLUDE[prod_short](includes/prod_short.md)]'s security model to restrict which tables and objects each user or user role can access, your organization might be at elevated risk when using chat. Therefore, we recommend that your organization either implement [!INCLUDE[prod_short](includes/prod_short.md)]'s security model or deactivate chat.

When Copilot needs to answer questions about non-Microsoft apps, it searches the online help content associated with those apps, powered by Bing Search. To ensure security and safety:

- Copilot only searches these specific URLs and doesn't perform a broad web search.
- [!INCLUDE[prod_short](includes/prod_short.md)] applies various mechanisms such as content filtering and malicious site detection to reduce risk from these websites.

Learn more about how Copilot searches the web in [Searching the web with Copilot (preview)](ai-search-web-copilot.md).

[!INCLUDE[ai-data-collection](includes/ai-data-collection.md)]

## Related information

[Chat with Copilot (preview)](chat-with-copilot.md)  
[Analyze data in lists with help from Copilot (preview)](analysis-assist.md)  
