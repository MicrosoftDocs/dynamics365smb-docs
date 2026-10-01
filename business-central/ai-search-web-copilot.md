---
title: Bing Search for Copilot features in Business Central (preview)
description: Learn which Business Central Copilot features use Bing Search and how administrators enable the integration.
author: SusanneWindfeldPedersen
ms.author: mikebc
ms.reviewer: solsen
ms.search.keywords: bing, browsing, search engine, web-enabled AI, web-aware AI
ms.topic: article
ms.date: 09/16/2026
ms.update-cycle: 180-days
ms.custom: bap-template
ms.collection:
- bap-ai-copilot
---

# Bing Search for Copilot features in Business Central (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Some Copilot capabilities provided by [!INCLUDE[prod_short](includes/prod_short.md)] use Microsoft Bing Search to retrieve information from public websites. Administrators control this integration by using the **Enable Bing Search** setting on the **Copilot & agent capabilities** page.

> [!IMPORTANT]
> The **Enable Bing Search** setting applies only to the Business Central capabilities described in this article. It doesn't control web search in **Microsoft Copilot in Business Central** in version 29.0 and later.
>
> Microsoft Copilot has separate controls for web search. When Microsoft Copilot uses web search, it generates a short search query based on the user's prompt and sends the query to Bing. For more information, see [How web search works in Microsoft Copilot Chat and agents](https://support.microsoft.com/microsoft-365-copilot/how-web-search-works-in-microsoft-365-copilot-chat-and-agents) and [Data, privacy, and security for web search in Microsoft Copilot and Microsoft Copilot Chat](/microsoft-365/copilot/manage-public-web-access).

Bing Search is available from update 26.3 in sandbox environments. Starting in update 27.0, it's also available in production environments. Bing Search isn't available for on-premises deployments of [!INCLUDE[prod_short](includes/prod_short.md)] because it's intended for use with AI features in online environments.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Which Business Central capabilities use Bing Search?

The following table lists the Business Central capabilities controlled by the **Enable Bing Search** setting.

| Capability | How Bing Search is used | If Bing Search is turned off |
|------------|-------------------------|------------------------------|
| **Chat with Copilot (legacy)** | Starting in update 26.3, Chat with Copilot uses Bing Search to find publicly available documentation for add-on apps installed in your environment. Using Bing Search provides answers that are tailored to the apps your organization uses. The third-party publisher of each app owns and hosts the documentation. | You can continue to use Chat with Copilot, but answers about installed apps might be unavailable or less complete. |
| **Autofill with Copilot** | Autofill uses Bing Search to find information from public websites that can help suggest values for fields. | Autofill continues to work, but suggestions that depend on information from public websites might be unavailable or less complete. |

> [!NOTE]
> **Chat with Copilot** in this table refers to the legacy Business Central chat experience. Starting with Business Central version 29.0, **Microsoft Copilot in Business Central** replaces Chat with Copilot. The **Enable Bing Search** setting doesn't control web search in Microsoft Copilot in Business Central.

## How does Bing Search work?

The information in this section applies to search requests initiated by the Business Central capabilities listed in the preceding table. It doesn't describe web search in Microsoft Copilot in Business Central.

When a Business Central capability uses Bing Search, Business Central sends a search query to the Bing Search service. Bing returns information from publicly available websites that the capability can use when generating a response or suggestion.

For example, Chat with Copilot can use Bing Search to find documentation published by the provider of an add-on app. This information can help Copilot answer questions about functionality that isn't part of the base Business Central application.

The Bing Search service is hosted in the United States geographic region. When a Business Central capability connects to this service, the web search query and search results are temporarily processed by the service.

For information about how **Microsoft Copilot** uses web search instead, see [How web search works in Microsoft Copilot Chat and agents](https://support.microsoft.com/microsoft-365-copilot/how-web-search-works-in-microsoft-365-copilot-chat-and-agents).

## Is it safe to enable Bing Search?

The information in this section applies to the Business Central Bing Search integration controlled by the **Enable Bing Search** setting. It doesn't describe the privacy, security, or data-handling behavior of web search in Microsoft Copilot.

For information about privacy, security, and data handling for web search in Microsoft Copilot, see [Data, privacy, and security for web search in Microsoft Copilot and Microsoft Copilot Chat](/microsoft-365/copilot/manage-public-web-access).

When a Business Central capability uses Bing Search, only the information needed to perform the web search is sent to the Bing Search service. Business Central data isn't made publicly available through Bing Search.

Before you enable Bing Search, review your organization's privacy, compliance, and data-residency requirements.

## How can administrators enable Bing Search?

Administrators control access to the Business Central Bing Search integration from the **Copilot & agent capabilities** page.

To enable Bing Search:

1. In [!INCLUDE[prod_short](includes/prod_short.md)], choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Copilot & agent capabilities**, and then choose the related link.
2. Turn on **Enable Bing Search**.

When the setting is turned on, Business Central capabilities that support Bing Search can connect to the Bing Search service.

When the setting is turned off, these capabilities don't send search requests to Bing.

> [!IMPORTANT]
> This setting doesn't enable or disable web search in **Microsoft Copilot in Business Central**. Microsoft Copilot settings and organizational policies separately control web search in Microsoft Copilot.

Learn about controlling web search in Microsoft Copilot in [Data, privacy, and security for web search in Microsoft Copilot and Microsoft Copilot Chat](/microsoft-365/copilot/manage-public-web-access).

## How much does it cost to use Bing Search?

There's no additional charge from Business Central for using the Bing Search integration with supported Business Central Copilot capabilities.

## What happens if Bing Search is turned off?

Turning off **Enable Bing Search** prevents the Business Central capabilities listed in this article from using Bing Search.

The capabilities themselves can remain available, but functionality that depends on information from public websites might be unavailable or provide less complete results.

Turning off **Enable Bing Search** doesn't turn off web search in Microsoft Copilot in Business Central. Microsoft Copilot web search is managed separately.

## How is Bing Search different from web search in Microsoft Copilot?

Business Central and Microsoft Copilot can both use Bing, but they're separate integrations with separate controls.

- **Business Central Bing Search** is used by specific Business Central Copilot capabilities. Administrators control this integration with the **Enable Bing Search** setting on the **Copilot & agent capabilities** page.
- **Microsoft Copilot web search** is a Microsoft Copilot capability. Microsoft Copilot can generate a web search query from a user's prompt and send the query to Bing to help ground its response in current public information. Microsoft Copilot settings and organizational policies control this behavior.

The **Enable Bing Search** setting in Business Central doesn't affect Microsoft Copilot web search.

For more information about Microsoft Copilot web search, see:

- [How web search works in Microsoft Copilot Chat and agents](https://support.microsoft.com/microsoft-365-copilot/how-web-search-works-in-microsoft-365-copilot-chat-and-agents)
- [Data, privacy, and security for web search in Microsoft Copilot and Microsoft Copilot Chat](/microsoft-365/copilot/manage-public-web-access)

## Related information

- [Configure Copilot and agent capabilities](enable-ai.md)  
- [Use Microsoft Copilot in Business Central (preview)](chat-with-copilot.md)  
- [Microsoft Copilot in Business Central FAQ](chat-with-copilot-faq.md)  
- [Application card: Microsoft Copilot in Business Central](microsoft-copilot-in-business-central-application-card.md)  