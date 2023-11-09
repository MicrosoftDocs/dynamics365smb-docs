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

Copilot is available in all supported [Business Central geographic regions](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations). However, Copilot uses Microsoft Azure OpenAI Service, which is currently available for Business Central in the United States and Switzerland only. This means that if your environment is located elsewhere, data from the Copilot and generative AI features (like data in prompts or returned in completions) must be transmitted outside of your geographical region. In this case, you must opt in to allow data movement to an Azure OpenAI Service in another geography. <!--For a list of geographies, refer to the [Azure OpenAI Service geographies](#azure-openai-service-geographies) section that follows.-->

If your environment is located in United Sates and Switzerland, it automatically connects to Azure OpenAI Service and you have no choice to opt in or out.

### Azure OpenAI Service geographies

The following table shows the Azure OpenAI Service's geography used by Copilot, based on the Business Central environment's geography. This information is important when deciding whether to opt in for data movement across geographies.

| Business Central environment geography | Azure OpenAI Service geography|
| - | - |
|Asia Pacific|United States|
|Australia| United States |
|Brazil |United States|
|Canada|United States|
|Europe| Switzerland |
|France|Switzerland |
|Germany|Switzerland |
|France|Switzerland |
|India|United States|
|Japan|United States|
|Korea|United States|
|Norway|Switzerland |
|Singapore|United States|
|South Africa|United States|
|Switzerland |Switzerland|
|United Arab Emirates|United States|
|United Kingdom|United States|
|United States|United States|

> [!NOTE]
> Except for Business Central environments in the United Sates and Switzerland, the actual Azure OpenAI Service geography used for your environment can vary based on current availability. Once an Azure OpenAI Service becomes available in your  Business Central geography, your environment will automatically transition to use the Azure OpenAI Service and opting in isn't required or even possible.  
<!--

BC geos base on https://dynamics.microsoft.com/en-us/availability-reports/georeport/
case "AUSTRALIAEAST":
            case "AUSTRALIASOUTHEAST":
                return new CapiRegion("au", 2);
            case "BRAZILSOUTH":
                return new CapiRegion("br", 2);
            case "CANADACENTRAL":
            case "CANADAEAST":
                return new CapiRegion("ca", 2);
            case "CENTRALINDIA":
            case "SOUTHINDIA":
                return new CapiRegion("in", 1);
            case "EASTASIA":
                return new CapiRegion("as", 2);
            case "EASTUS":
            case "EASTUS2":
            case "SOUTHCENTRALUS":
            case "CENTRALUS":
            case "NORTHCENTRALUS":
            case "WESTUS":
            case "US":
                return new CapiRegion("us", 9, HasGpt4InGeo: true, HasTurboInGeo: true);
            case "FRANCECENTRAL":
            case "FRANCESOUTH":
                return new CapiRegion("fr", 1);
            case "GERMANYNORTH":
            case "GERMANYWESTCENTRAL":
                return new CapiRegion("de", 1);
            case "JAPANEAST":
            case "JAPANWEST":
                return new CapiRegion("jp", 1);
            case "KOREACENTRAL":
            case "KOREASOUTH":
                return new CapiRegion("kr", 1);
            case "NORWAYEAST":
            case "NORWAYWEST":
                return new CapiRegion("no", 1);
            case "SOUTHAFRICANORTH":
            case "SOUTHWESTAFRICA":
                return new CapiRegion("za", 1);
            case "SOUTHEASTASIA":
                return new CapiRegion("sg", 1);
            case "SWITZERLANDNORTH":
            case "SWITZERLANDWEST":
                return new CapiRegion("ch", 1, HasTurboInGeo: true);
            case "UKSOUTH":
            case "UKWEST":
                return new CapiRegion("uk", 2);
            case "NORTHEUROPE":
            case "WESTEUROPE":
                return new CapiRegion("eu", 10);
            case "UAENORTH":
            case "UAECENTRAL":
                return new CapiRegion("ae", 1);

-->

## Next steps

You opt in to allow data movement across geographies from the [Copilot & AI Capabilities](https://businesscentral.dynamics.com/?page=7775) page. To learn more, go to [Allow data movement across geographies](enable-ai.md#allow-data-movement-across-geographies).
