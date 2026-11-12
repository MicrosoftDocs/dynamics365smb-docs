---
title: Trial Features That Connect to Other Microsoft Services
description: Understand which Microsoft services Business Central trial features connect to, how privacy approvals work, and where to manage each integration.
author: jswymer
ms.topic: overview
ms.service: dynamics-365-business-central
ms.search.keywords: privacy, trial, Microsoft services
ms.date: 11/12/2026
ms.author: jswymer
ms.reviewer: jswymer
ai-usage: ai-assisted
---
# Trial features that connect to other Microsoft services

[!INCLUDE[prod_long](includes/prod_long.md)] is a comprehensive business management solution that's deeply integrated with Microsoft 365 productivity apps, Power Platform, and AI services. Your free trial can connect to other Microsoft services. You might need to purchase these services separately unless you already have them.

In evaluation companies, Business Central can accept some connected-service privacy notices automatically. An administrator's decision to decline a notice takes precedence. Privacy approval doesn't provision a service, grant a license, or guarantee that a feature is available. You might still need to configure the integration and sign in to the connected service.

To review and manage organization-wide privacy decisions, use the **Privacy Notices Status** page. Learn more in [Privacy notices status in Business Central](privacy-notices-status.md).

The following table lists services used by connected trial features and where to manage the integrations.

|Service name|Connection is automatically enabled|Service is contacted when signing in to Business Central|Example feature that uses this service|Learn how to manage the connection and features that use it|
|------------|-------------|--------|------------|-------------|
|Microsoft Teams|Yes|No|**Share to Teams** action on the **Item** card|[Managing Teams integration with Business Central](admin-teams-integration.md)|
|Microsoft OneDrive|Yes|No|**Open in OneDrive** action on **Item** attachments|[Managing OneDrive integration with Business Central](admin-onedrive-integration.md#configure-onedrive-using-onedrive-setup)|
|Microsoft Power Automate|Yes|No|**Automate** actions on the **Item** card|[Set up Power Automate integration](/dynamics365/business-central/dev-itpro/powerplatform/power-automate-setup)|
|Microsoft Azure OpenAI Service|Yes|No|Copilot|[Configure AI-powered item marketing text with Copilot](enable-ai.md)|
|Microsoft Bing|Yes|No|Autofill with Copilot|[Searching the web with Copilot](ai-search-web-copilot.md)|
|Microsoft Learn|Yes|No|Chat with Copilot, Help pane|[Chat with Copilot FAQ](chat-with-copilot-faq.md)|

> [!NOTE]
> By using features that connect to these services:
>
> - You consent to your data being shared with that Microsoft service. If your organization deployed these services in a different country or region, connecting to the service might result in your data crossing data residency boundaries. Make sure to confirm your organization’s policies and government compliance requirements for data residency before proceeding to use these features.
> - You might affect services that aren't trials. If your organization uses these services in production and aren't being evaluated together with Business Central, other users of these services who aren't participating in this trial of [!INCLUDE[prod_short](includes/prod_short.md)] might be affected.
> - [!INCLUDE[prod_short](includes/prod_short.md)] might also connect to Microsoft services or third-party services depending on the customizations and extensions that you or your administrator installed in your [!INCLUDE[prod_short](includes/prod_short.md)] trial. For information about how your extensions process your data, contact the extension developer or follow the privacy link for the extension on Marketplace.
> - For features in preview, you consent to the [preview terms](https://go.microsoft.com/fwlink/?linkid=2189520).

Your privacy is important to us. Learn more in the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).

## Start your Business Central trial

[!INCLUDE[prod_short](includes/free_trial_md.md)]

## Related information

[Connect Business Central to Microsoft apps and services](across-setup-connections.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
