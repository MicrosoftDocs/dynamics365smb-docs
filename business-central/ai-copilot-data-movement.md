---
title: Copilot data movement across geographies
description: Learn how data that's used in copilot features in Dynamics 365 Business Central moves across geographies where Azure OpenAI Service isn't available by default.
author: jswymer #
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: conceptual
ms.collection: get-started #Required; If this isn't a getting started article, don't remove the attribute, but leave the value blank. The values for this attribute will be updated over time.
ms.date: 11/09/2023
ms.custom: bap-template 
---

# Copilot data movement across geographies 

Copilot is available in all supported [Business Central geographic regions](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations). However, Copilot uses Microsoft Azure OpenAI Service, which is available only in Australia, Sweden, Switzerland, United Kingdom, and United States. This means that if your environment is located elsewhere, data from the Copilot and generative AI features (like data in prompts or returned in completions) must be transmitted outside of your geographical region.  In this case, you must opt in to allow data movement to an Azure OpenAI Service in another geography. For a list of geographies, refer to the [Azure OpenAI Service geographies](#azure-openai-service-geographies) section that follows.

If your environment is located in one of the regions listed previously, it automatically connects to Azure OpenAI Service, so no extra action is required.

### Azure OpenAI Service geographies

The following table shows the Azure OpenAI Service's geography used by Copilot, based on the Business Central environment's geography. This information is important when deciding whether to opt in for data movement across geographies.

| Business Central environment geography | Azure OpenAI Service geography|
| - | - |
|Asia Pacific|United States|
|Australia| Australia |
|Brazil (South America) |United States|
|Canada|United States|
|Europe|Sweden or Switzerland |
|France|Sweden or Switzerland |
|Germany|Sweden or Switzerland |
|France|Sweden or Switzerland |
|India|United States|
|Japan|United States|
|(South) Korea|United States|
|Norway|Sweden or Switzerland |
|Singapore|United States|
|South Africa|United States|
|Switzerland |Switzerland|
|United Arab Emirates|United States|
|United Kingdom|United Kingdom|
|United States|United States|


## Next steps

You opt in to allow data movement across geographies from the [Copilot & AI Capabilities] page. To learn more, go to [Allow data movement across geographies](enable-ai.md#allow-data-movement-across-geographies).
