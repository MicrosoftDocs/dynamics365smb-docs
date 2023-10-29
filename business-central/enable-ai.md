---
title: Configure AI-powered item marketing text (preview) with Copilot
description: This article explains how to get a Copilot trial version of Business Central and enable Copilot on an environment.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to
ms.date: 03/22/2023
ms.custom: bap-template
---

# Configure Copilot and AI capabilities 

<!--[!INCLUDE[ai-preview](includes/ai-preview.md)]-->

<!--This article explains how you can control the ability to create AI-powered item marketing text with Copilot for your organization. This task is done by an admin. There are two requirements that you must fulfill to make the feature available to users:-->


This article explains how to control users' access to Copilot and other AI capabilities in Business Central. This task is done by an admin. There are three levels of access control to Copolit and AI capabilities, depending on the feature:

- Consent to the Azure OpenAI [preview](https://dynamics.microsoft.com/legaldocs/supp-dynamics365-preview/) and [privacy](https://go.microsoft.com/fwlink/?LinkId=521839) terms and conditions.

   This consent is required for any Copilot or AI capability to work for users. The consent is global for all users and applies to all Copilot and AI features.

- Enable the specific feature if it's  still governed under **Feature Management**.

- Activate the feature on the **Copilot & AI Capabilities** page.   

If any of these requirements aren't fulfilled, the feature won't be available for use.

## Prerequisites

- You're using Business Central online, version 23.1 or later. <!--[preview version](ai-preview-getstarted.md) of Business Central that's enabled for Copilot.-->
- You have admin or super permissions in Business Central.  <!--For more information, go to [Configure AI-powered item marketing text with Copilot](enable-ai.md).-->

## Consent to or reject preview and privacy terms

Consent to the terms and conditions of [preview](https://dynamics.microsoft.com/legaldocs/supp-dynamics365-preview/) and [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=521839) on behalf of the organization.

1. In Business Central, search for and open the **Privacy Notices Status** page.
2. In the **Integration Name** column, select **Azure OpenAI**, then read the terms and conditions that are presented to you.
3. In the **Azure OpenAI** row, select the **Agree for everyone** checkbox to consent or the **Disagree for everyone** checkbox to reject.


## Enable or disable feature in Feature Management

**Feature Management** is used to turn on or off features that are in preview, like bank reconciliation, and some features that are generally available, like item marketing suggestion. [Learn more about feature management](/dynamics365/business-central/dev-itpro/administration/feature-management).

1. In Business Central, search for and open the **Feature Management** page.
2. Set the **Enabled for** column for **Feature preview: Create AI-powered product descriptions with Copilot** to **All users** to enable the feature or **None** to disable it.

   For more information about feature management in general, go to [Feature Management](/dynamics365/business-central/dev-itpro/administration/feature-management).

## Activate or deactivate the feature

Using the **Copilot & AI Capabilities** page, you can turn individual features on or off for all users.

1. In Business Central, search for and open the **Copilot & AI Capabilities** page.

1. The page lists all available Copilot and AI related features and their current status, which can be either active or inactive. The features are divided into two sections&mdash;one section for features in preview and another for features that are generally available. 

   [![Shows the Business Central role center and the checklist for Copilot](media/copilot-and-ai-capabilties-page.svg)](media/copilot-and-ai-capabilties-page.svg#lightbox)

   - To turn on a feature, select it in the list, then select the **Activate** in the ribbon.
   - To turn a feature off, select it, and then select **Deactivate** in the ribbon. 


## Next steps

After you enable and consent to the feature, you're ready to try out Copilot on items in Business Central. Go to [Add marketing text to items](item-marketing-text.md).  

## See also

[Overview of AI-powered item marketing text with Copilot](ai-overview.md)  
[Create marketing text to items using Copilot](item-marketing-text.md)  
[AI-powered item marketing text with Copilot FAQ](ai-faq.md)  
