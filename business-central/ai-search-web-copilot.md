---
title: Searching the web with Copilot
description: Get an overview of how you enable searching the web with Copilot in Business Central.  
author: SusanneWindfeldPedersen
ms.author: solsen
ms.reviewer: solsen
ms.search.keywords: bing, browsing, search engine, web-enabled AI, web-aware AI
ms.topic: overview 
ms.date: 07/02/2025
ms.custom: bap-template 
ms.collection:
  - bap-ai-copilot
---

# Searching the web with Copilot

Some Copilot features in [!INCLUDE [prod_short](includes/prod_short.md)] can search the web for additional information. Allowing Copilot to search the web improves the quality of Copilot responses by grounding them in the latest information from public website content, and saves you time from having to switch apps to manually find things yourself. Copilot is powered by Microsoft Bing, and connecting Copilot to Bing search is optional. 

> [!IMPORTANT]
> Bing Search is available from update 26.3, initially in Sandbox environments only. Because it's intended for use with AI features, Bing Search isn't available for [!INCLUDE [prod_short](includes/prod_short.md)] on premises.

## What is Bing Search? 

Microsoft Bing is an online service operated by Microsoft that allows apps to search the web and return web results, similar to when you open up your browser and search the web with Microsoft Bing or with other search engines. Bing Search enables safe, ad-free search results, surfacing relevant information from billions of websites. 

Microsoft Bing is a separate product that operates differently from Dynamics 365 and has different data-handling practices covered by the Microsoft Services Agreement between each user and Microsoft, together with the Microsoft Privacy Statement. Microsoft acts as an independent data controller responsible for complying with all applicable laws and controller obligations.

## Which Copilot features can search the web? 

The following table describes the list of Copilot capabilities that currently use Bing Search. 

| Feature | How Bing Search is used | What happens if Bing Search isn't enabled |
| --- | --- | --- |
| Copilot Chat | From Update 26.3 | Copilot uses Bing Search to read publicly-available documentation that matches the add-on apps that you have installed to your environment, providing more accurate answers that are tailored to how your organization uses Business Central. This documentation is owned and hosted by the third-party publisher of each app. <br><br> **Example:** <br>You install an add-on to manage customer loyalty schemes that includes a new Customer Tier field added to the customer card. Copilot will now be able to explain how this field works, or why you get an error when setting this field.| You can continue to chat with Copilot, but responses will be of lower quality.<br> Copilot will respond only based on content from Microsoft’s documentation that has no information about how you have customized Business Central. |


## Related information