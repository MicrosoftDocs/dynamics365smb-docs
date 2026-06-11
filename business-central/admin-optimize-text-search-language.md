---
title: Configure text search language for multilingual environments
description: Learn how to optimize modern search performance by configuring the text search language for your Business Central environment.
author: jswymer
ms.topic: how-to
ms.search.keywords: search, modern search, full-text search, indexing, language, multilingual
ms.search.form: Primary_9234, 9202, 9235
ms.date: 06/09/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---
# Configure text search language for multilingual environments

By default, modern search in [!INCLUDE [prod_short](includes/prod_short.md)] uses a neutral language setting for indexing and searching. This setting works well for most environments. However, if your organization operates in a multilingual country/region like Belgium, Switzerland, or Canada, you can optimize search performance by configuring the text search language to match your primary data language.

## Why configure the text search language

When you set a text search language, the search index is optimized for that language. This optimization improves the relevance of search results for users who search in that language. For example, if most of your data is in German, setting German as the text search language helps the search engine better understand German word forms and deliver more relevant results.

Configuring the text search language is important for:

- **Multilingual environments** where data is primarily in one language but the user interface might be in another.
- **AI agents** like [Sales Order Agent](sales-order-agent.md) that rely on accurate item lookups. In multilingual countries/regions, the agent's item search accuracy depends on the text search language setting.

## Configure the text search language

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Advanced Settings**, and then select the related link.
1. Select **Text Search Language**.
1. On the **Text Search Language Optimizer** page, select the **Language** field.
1. Choose a language from the list of supported languages.
1. When prompted, confirm that you want to proceed with reindexing.

> [!IMPORTANT]
> Changing the text search language triggers a complete reindexing of all searchable data. Depending on the size of your database, this process can take a significant amount of time. We recommend that you make this change outside of business hours to minimize the impact on users.

## Considerations

- The text search language setting applies to the entire environment so it affects all users.
- After changing the language, new and updated data is indexed using the new language setting immediately. However, the full reindex of existing data runs as a background process.
- If modern search results seem incomplete immediately after the change, wait for the reindexing process to complete.

## Related information

[Searching and filtering](ui-enter-criteria-filters.md)  
[Sales Order Agent overview](sales-order-agent.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
