---
title: Responsible AI FAQ for Advanced Tell Me (preview)
description: Learn about the AI technology behind Advanced Tell Me semantic search in Business Central, including intended use, evaluation, limitations, mitigations, data, security, and feedback.
ms.date: 09/08/2025
ms.update-cycle: 180-days
ms.custom:
  - responsible-ai-faqs
ms.topic: faq
author: jswymer
ms.author: jswymer
ms.reviewer: solsen
ms.search.keywords: copilot, AI, search, semantic, navigation, advanced tell me
ms.collection:
  - bap-ai-copilot
---

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

These frequently asked questions (FAQ) describe the AI impact of Advanced Tell Me in [!INCLUDE[prod_short](includes/prod_short.md)]. For help using search, see [Finding pages and information](ui-search.md).

## What is Advanced Tell Me?

Advanced Tell Me is an AI-powered enhancement to the existing **Tell me what you want to do** (Alt+Q) feature. It provides semantic (meaning-based) search over product metadata—such as page captions, descriptions, additional search terms, and report or query metadata—so you can find pages, reports, and queries even when your wording doesn't match exact text.

## What can Advanced Tell Me do?

Advanced Tell Me improves navigation and discoverability by:

- Matching natural language and acronym queries to semantically similar metadata entities (pages, reports, queries)
- Returning relevant results when you use synonyms, alternate phrasing, or common Business Central abbreviations
- Integrating into the existing **Tell me** pane and Report Explorer through an **Advanced** tab alongside keyword results

## What is the intended use of Advanced Tell Me?

It’s intended to:

- Help you efficiently locate pages, reports, and queries in Business Central
- Reduce reliance on exact keyword matching required by classic Tell Me
- Provide intuitive, context-aware navigation

It isn’t designed to search business data (records, transactions) or external content.

## How was Advanced Tell Me evaluated? What metrics measure performance?

Evaluation used 12,118 English test cases derived from application metadata variations, covering:

- Single-word semantic matches to an object name
- Multi-word phrases matching captions, additional search terms, or about/help text
- Common Business Central abbreviations and acronyms
- Paraphrased or synonym-rich queries

Primary metric: target object appears within the top 3 results (precision@3). Quality gates required acceptable aggregate performance across all query classes.

The feature is built in accordance with Microsoft's Responsible AI Standard. [Learn more about responsible AI from Microsoft](https://aka.ms/RAI).

## How does Microsoft monitor quality and safety?

Automated and manual evaluation pipelines monitor relevance, stability, and safety. Aggregated telemetry helps detect degradation or anomalous result patterns. User feedback supports iterative improvements.

You can report poor or unexpected results through standard feedback and support channels.

## What are the limitations of Advanced Tell Me and how can I mitigate them?

### Limitations

- Language: Validated and supported in English only; other languages may yield reduced quality.
- Metadata dependence: Sparse or inaccurate captions, additional search terms, or about text lower result quality.
- Scope: Doesn’t search live business data or external sources—only product metadata.
- Ranking variance: The best match might not always appear first.
- Not a data exploration tool: It won’t retrieve specific records by value (use other search or filtering features instead).

### Mitigations

- Use clear, descriptive queries (short phrases or natural language).
- Enrich metadata (captions, Additional Search Terms, About Text) for custom objects.
- Rephrase with distinctive domain terms if results are weak.
- Fall back to the keyword tab for exact label searches.

## What operational factors affect responsible use?

- Feature management: Advanced Tell Me can be turned on/off in **Feature Management**.
- Metadata stewardship: Regularly review and enrich metadata for custom pages, reports, or queries to maintain high-quality results.
- User guidance: Encourage users to review result context before navigating when similarly named objects exist.

If prerequisites (like activation) aren’t met, the **Advanced** tab won’t appear.

## What data does Advanced Tell Me use? Does it train on my data?

It works on product metadata already present in the environment (captions, descriptions, search terms). Query text and interaction signals may be logged for service quality and safety. Microsoft doesn't use your company business data to train foundational AI models for the benefit of others.

Avoid entering sensitive data (passwords, secrets) into search queries.

## What does Advanced Tell Me offer for security and compliance?

- Runs under the signed-in user’s identity and respects existing permissions.
- Surfaces only metadata for accessible objects.
- Doesn’t expose restricted table data or bypass role-based security.
- Doesn’t perform external web searches; processing stays within service boundaries.

## How does Advanced Tell Me handle unsupported languages?

Non-English queries receive best-effort matching, but relevance can degrade. If results are poor:

- Rephrase in English.
- Try more domain-specific terms.
- Use the classic (keyword) tab.

## How do I provide feedback on Advanced Tell Me?

Use normal support or preview feedback channels to report:

- Missing expected results
- Irrelevant matches
- Ranking issues (correct item too low)

Include the exact query and the object you expected.

## Related information

[Finding pages and information](ui-search.md)  
[Responsible AI FAQ for Chat with Copilot](faqs-chat-with-copilot.md)  
[Business Central documentation](index.md)  
