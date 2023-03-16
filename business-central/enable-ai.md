---
title: Configure AI-powered item marketing text (preview) with Copilot
description: This article explains how to get a Copilot trial version of Business Central and enable Copilot on an environment
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to
ms.date: 03/16/2023
ms.custom: bap-template
---

# Configure AI-powered item marketing text (preview) with Copilot

[!INCLUDE[ai-preview](includes/ai-preview.md)]

This article explains how you can control the ability to create AI-powered item marketing text with Copilot for your organization. This task is done by an admin. There are two requirements that you must fulfill to make the feature available to users:

- Enable the **Create AI-powered product descriptions with Copilot** feature.
- Consent to the terms and conditions of [preview](https://dynamics.microsoft.com/legaldocs/supp-dynamics365-preview/) and [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=521839) on behalf of the organization.

If either of these requirements isn't fulfilled, the feature won't be available for use.

<!--
> [!IMPORTANT]
> To enable the feature, the privacy notice must be agreed upon and the feature switch must be on.-->

## Enable or disable the "Create AI-powered product descriptions with Copilot" feature

1. In Business Central, search for and open the **Feature Management** page.
2. Set the **Enabled for** column for **Feature preview: Create AI-powered product descriptions with Copilot** feature to **All users** to enable the feature or **None** to disable it.

   For more information about feature management in general, go to [Feature Management](/dynamics365/business-central/dev-itpro/administration/feature-management).

## Consent to or reject the preview and privacy terms and conditions for all users

<!--Before users can use Copilot, You enable or disable Copilot and Azure OpenAI Services by agreeing or disagreeing to the terms and conditions on behalf of the organization. Complete the following steps. --> 

1. In Business Central, search for and open the **Privacy Notices Status** page.
2. In the **Integration Name** column, select **Azure OpenAI**, then read the terms and conditions that are presented to you.
3. In the **Azure OpenAI** row, select the **Agree for everyone** check box to consent or the **Disagree for everyone** check box to reject.

<!--
> [IMPORTANT]
> As an admin, you can also agree to the terms and conditions 

1. Open an item card
2. Select Create with Copilot
3. Select Agree or Disagree.-->

## Next steps

Once you have a sandbox or trial environment, you ready to try out Copilot on items in Business Central. Go to [Add marketing text to items](item-marketing-text.md).  

## See also

[Overview of AI-powered item marketing text with Copilot](ai-overview.md)  
[Create marketing text to items using Copilot](item-marketing-text.md)  
[AI-powered item marketing text with Copilot FAQ](ai-faq.md)  