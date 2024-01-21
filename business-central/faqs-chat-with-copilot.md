---
title: FAQs for chat (preview) with Copilot
description: This FAQ provides information about the AI technology used for chatting with Copilot in Business Central. It includes key considerations and details about how AI is used, how it was tested and evaluated, and any specific limitations.
ms.date: 01/10/2024
ms.custom: 
  - responsible-ai-faqs
ms.topic: article
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.search.keywords: copilot, AI, chat 
---
# FAQ for Chat with Copilot (preview)

[!INCLUDE[production-ready-preview-dynamics365](includes/production-ready-preview-dynamics365.md)]

These frequently asked questions (FAQ) describe the AI impact of Chat with Copilot in [!INCLUDE[prod_short](includes/prod_short.md)].

## What is Chat with Copilot?

Chat with Copilot is an interactive feature that answers questions and finds business data related to Business Central, without users having to navigate the user interface or the product documentation. Chat with Copilot pane is available from anywhere in the Business Central client.

Users ask questions in natural language, like "How do I deliver goods to my customers directly from my vendors?" or "Do we have any office chairs in stock for under $600?". In response, chat with Copilot provides answers in natural language. Depending on the questions, answers can include plain text, links to records or pages in Business Central, and links to Business Central help articles on Microsoft Learn.

## What are capabilities of Chat with Copilot?

Chat with Copilot offers the following distinct skills:

### Explain and guide

Users can ask Copilot to expain a specific concept related to Business Central, like what are dimensions, or provide guidance on how to complete a task, like how to post a sales order. Chat with Copilot searches the official Business Central documentation published by Microsoft, and provides an answer based on the documentation.

- Copilot uses Microsoft Learn Knowledge Service (not Bing web search) to semantically search only Dynamics 365 Business Central documentation on Microsoft Learn. 

- Copilot doesn't take action, create new data, or modify any configuration. It simply summarizes an answer grounded in matching documentation snippets.

### Find business data and related pages

Users can ask questions about specific records/entities within the company in Business Central that they're working with, such as customers, vendors, sales orders, and items, and more. Users locate pages (by name) or records based on their fields and constraints. If Copilot finds answer, it responds with a link to the relevant record or page, which the user then can select to open.

- Copilot converts the natural language input into a query consisting of a table search, sort, and filter criteria.

  The capability uses the Business Central's native data search capabilities to find matching data from tables within the companies database. The search runs under the user's own identity for security and compliance. It doesn't search outside of the Business Central database. go beyond the boundary of BC. 

- Copilot doesn't take action, create new data, or modify any configuration. It only summarizes the records received from the Business Central native data search. 

## What is the intended use of Chat with Copilot?

Copilot has two intended uses:

- Answer users' inquiries to explain a concept or provide instructions on how to accomplish some task in Business Central. 
- Answer users inquiries to navigate to a specific Business Central page, or find one or more business records stored in the companies database and let the user choose to navigate them.

## How was Chat with Copilot evaluated? What metrics are used to measure performance?

- The feature underwent extensive testing where numerous texts in different languages were evaluated by language experts against various criteria. Testing was based on [!INCLUDE[prod_short](includes/prod_short.md)]'s demonstration data and other fictitious product catalogs.
- This feature is built in accordance with Microsoft's Responsible AI Standard. [Learn more about responsible AI from Microsoft](https://aka.ms/RAI).

## How does Microsoft monitor the quality of generated content?

Microsoft has various systems in place to ensure Copilot capabilities remain operational and generate content of the highest quality.

Users have the opportunity to provide feedback to report inappropriate content and improve the functionality.

- If you encounter inappropriate generated content, report it to Microsoft by using this feedback form: [Report abuse](https://go.microsoft.com/fwlink/?linkid=2249810). 

  Microsoft might disable the Copilot-driven features for selected customers if abuse of the functionality is detected.

- We track user feedback on the feature to help us improve suggestions.

  You provide feedback by using the like (thumbs up) or dislike (thumbs down) icon on the **Copilot** pane in [!INCLUDE[prod_short](includes/prod_short.md)].

## What are the limitations of Chat with Copilot? How can users minimize the impact of the Chat with Copilot limitations when using the system?

- General limitations of AI

  AI systems are valuable tools, they are nondeterministic. This means that perfect accuracy of any generated content, suggestions or insights isn't possible. Failure to understand this limitation can lead to over-reliance on the system and unmerited decisions that can impact any stakeholders including customers, their customers, and partners. To mitigate any risks, always review and verify responses generated by chat with Copilot using good judgment.

- Language limitations

  - Chat with Copilot is only supported in English for the following locales: en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA.

    Inaccurate responses might be returned when users interact with the feature in languages other than the supported languages.

  - The quality of answers can be lower under the following conditions:
    - The language locale is something other than en-US.
    - When the language setting for the user in Business Central differs from the primary language of the data in the [!INCLUDE[prod_short](includes/prod_short.md)] database.

- Specific industry, product, and topic limitations

   Chat with Copilot includes built-in safety mechanisms that prevent the undesirable generation of harmful content, such as sexually explicit content or incitement of violence. Sometimes, customers operate in industries, sell products and services, or work with processes that naturally overlap with what might be considered inappropriate in other contexts, or work with data that might trigger these safeguards. Chat with Copilot might not perform as well in these cases.

<!--## What operational factors and settings allow for effective and responsible use of the feature?-->

## What data does Chat with Copilot collect and how is it used

Microsoft doesn't use your company data, including the text you send to Copilot, to train the foundational models for the benefit of others. Company administrators have full control to govern this data that is part of their Azure subscription. Because administrators or others in your company might have access to this data as determined by your employer, we recommend users don't enter sensitive data such as passwords or other secrets.

## What does Chat with Copilot offer for security

Chat with Copilot is designed to be secure and executes under the user's identity, inheriting all security permissions and other restrictions and never operating outside of Business Central's platform security. This means that Copilot can only access data that the user has access to. For users that have SUPER permission, chat can more easily locate unsecured data that's typically harder to get to for other users.

Organizations that don't apply Business Central's security model to restrict which tables and objects each user or user role has access to, might be at elevated risk when using chat. Therefore, we recommend that your organization either implements Business Central's security model or deactivates Chat with Copilot.

## See also

[Chat with Copilot (preview)](chat-with-copilot.md)
