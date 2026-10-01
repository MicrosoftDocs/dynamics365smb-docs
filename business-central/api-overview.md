---
title: API Overview Page in Business Central
description: Learn how the API Overview page helps administrators discover available APIs, review endpoint metadata, and prepare integrations.
author: SusanneWindfeldPedersen
ms.author: solsen
ms.reviewer: solsen
ms.topic: overview
ms.search.form: 812
ms.date: 09/23/2026
ai-usage: ai-assisted
---

# Discover APIs with the API Overview page

[!INCLUDE [2026-releasewave-2](includes/2026-releasewave-2.md)]

The **API Overview** page gives administrators one place to explore the APIs that are available in the current [!INCLUDE[prod_short](includes/prod_short.md)] environment. Use the page to identify integration endpoints, understand which solution provides an API, and review API metadata before you connect an external system.

The page lists published API pages, API queries, and API codeunits that are available in the current environment. These APIs come from Microsoft and from publishers of installed extensions.

## Open the API Overview page

1. [!INCLUDE [open-search](includes/open-search.md)], enter **API Overview**, and then select the related link.
2. Select a view, such as **API Pages**, **API Queries**, **API Codeunits**, **API v2.0**, **Microsoft APIs**, or **Custom APIs**, to narrow the list.
3. Filter the list by API publisher, API group, or API version as needed.
4. Review the API details. When an **API URL** is available, select it to open the endpoint.

## Review the available API details

The **API Overview** page provides the following information:

| Column | Description |
|--------|-------------|
| **Name** | Specifies the name of the API page, query, or codeunit. |
| **Type** | Specifies whether the API is a page, query, or codeunit. API pages support read and write operations, API queries provide read-only data, and API codeunits expose procedures as unbound actions. |
| **ID** | Specifies the object ID of the underlying API page, query, or codeunit. |
| **API Publisher** | Specifies the publisher segment of the API URL and identifies who owns the API. |
| **API Group** | Specifies the group segment of the API URL. |
| **Entity** | Specifies the entity name that the API exposes. |
| **API Version** | Specifies the version segment of the API URL. |
| **API URL** | Specifies the full endpoint URL for an API page or query. |

The page doesn't configure an API or grant access. For API pages and queries, use **API URL** to open the endpoint and inspect its metadata or test a request. The field is blank for API codeunits because each procedure exposes a separate unbound action. Learn more about constructing an endpoint in [API endpoint structure](/dynamics365/business-central/dev-itpro/webservices/api-endpoint-structure). Learn more about authenticating an integration in [Web services authentication](/dynamics365/business-central/dev-itpro/webservices/web-services-authentication).

## Related information

[REST API web services](/dynamics365/business-central/dev-itpro/webservices/api-overview)  
[Business Central API v2.0](/dynamics365/business-central/dev-itpro/api-reference/v2.0/)  
[Developing a custom API](/dynamics365/business-central/dev-itpro/developer/devenv-develop-custom-api)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
