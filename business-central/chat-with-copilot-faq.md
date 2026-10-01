---
title: Microsoft Copilot in Business Central FAQ
description: Find answers to common questions about Microsoft Copilot in Business Central, including access, licensing, capabilities, settings, and limitations.
author: jswymer
ms.author: jswymer
ms.reviewer: solsen
ms.topic: faq
ai-usage: ai-assisted
ms.collection:
- bap-ai-copilot
ms.date: 09/16/2026
ms.update-cycle: 180-days
ms.custom: bap-template jswymer
---

# Microsoft Copilot in Business Central FAQ

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

This article answers common questions about Microsoft Copilot in [!INCLUDE[prod_short](includes/prod_short.md)]. For information about capabilities, limitations, data handling, and responsible AI, see [Application card: Microsoft Copilot in Business Central](microsoft-copilot-in-business-central-application-card.md).

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Versions and licensing

### What happened to Chat with Copilot?

<!--TBD: Confirm the version 29 replacement and upgrade behavior -->

Starting with Business Central version 29.0, Microsoft Copilot in Business Central replaces the previous **Chat with Copilot** experience.

If you're using Business Central version 28, you continue to use Chat with Copilot until your environment is updated to version 29. After your environment is updated to version 29, you use Microsoft Copilot in Business Central and can't switch back to Chat with Copilot.

Learn more about the previous experience in [Chat with Copilot (legacy)](chat-with-copilot-legacy.md).

### Why can't Microsoft Copilot access my emails, meetings, and other work data?

To access your Microsoft 365 work data through Work IQ, your account must be assigned a Microsoft Copilot license. Learn more in [License options for Microsoft Copilot](/microsoft-365/copilot/microsoft-365-copilot-licensing).

### Why can't I open Microsoft Copilot from Business Central?

Check the following:

- Make sure your browser allows pop-ups from Business Central. Learn more in [Set up your browser](across-browser-settings.md).
- Don't use InPrivate or private browsing mode.
- Microsoft Copilot might not be available when you sign in with a guest or delegated admin account.
- Your account must be eligible for Microsoft Copilot Chat, and your organization must allow you to access it. An admin can restrict access for all users or for selected users and groups. Learn more in [Manage Microsoft Copilot Chat](/copilot/manage).
- The **Chat** capability must be active in your Business Central environment, and you must have permission to use it. Learn more in [Configure Copilot and agent capabilities](enable-ai.md).

### Can I control access to Microsoft Copilot as an admin?

Yes. You can control access at both the organization and Business Central levels:

- In Microsoft 365, you can restrict access to Microsoft Copilot Chat for all users or for selected users and groups. Learn more in [Manage Microsoft Copilot Chat](/copilot/manage).
- In Business Central, you can activate or deactivate the **Chat** capability for an environment and control which users have permission to use it. Learn more in [Configure Copilot and agent capabilities](enable-ai.md#granting-user-access).

## Business Central data and capabilities

### What Business Central data can Microsoft Copilot use?

When you use Microsoft Copilot in Business Central, you can ask Copilot questions about Business Central records and pages, such as customers, vendors, items, and sales orders. Copilot can also use context from the Business Central page or record you're viewing.

Copilot works on your behalf and can access only Business Central data that you have permission to access. Business Central security, privacy, and compliance controls continue to apply when you use Copilot.

### Does a Microsoft Copilot license give me access to more Business Central data?

No. A Microsoft Copilot license doesn't change which Business Central data you can access.

Copilot can access only Business Central data that you're already permitted to access. A Microsoft Copilot license provides additional Microsoft Copilot capabilities, such as access to work data through Work IQ, but doesn't grant additional permissions in Business Central.

### Can Microsoft Copilot change Business Central data?

No. In the experience described in this article, Microsoft Copilot has read-only access to Business Central data. Copilot can retrieve and explain information, but it doesn't create, modify, or delete Business Central records.

### How do I open a Business Central record referenced by Copilot?

When a response uses Business Central data, Copilot can include citations or links to the Business Central records used to generate the response.

Select a citation or link to open the referenced record in Business Central.

### Can I use Business Central agents from Microsoft Copilot?

<!-- TBD: Confirm that Business Central first-party agents and third-party agents built by using the Business Central agent framework can't currently be invoked from Microsoft Copilot. -->

Not currently. You can't invoke Microsoft agents for Business Central or non-Microsoft agents built by using the Business Central agent framework from Microsoft Copilot.

### Can I use Business Central data in Microsoft Copilot outside Business Central?

Not currently. Microsoft Copilot gets access to Business Central context and data when you use Copilot from within Business Central.

If you continue the same Copilot conversation outside Business Central, such as from the standalone Microsoft Copilot experience, Copilot can use Business Central context that was already retrieved in that conversation, but it can't retrieve more Business Central data.

### Can Microsoft Copilot analyze Business Central data?

<!-- TBD: Removed analysis tabs support for now. Confirm supported grouping, ranking, aggregation, totals, averages, calculations, currency conversion, long-list, and large-result-set behavior and limitations. -->

Copilot can answer questions that involve comparing, summarizing, or reasoning over Business Central data. However, aggregation, complex analysis, and advanced summarization can have limitations.

Review the cited Business Central records and verify important totals, comparisons, or conclusions before using a response to make a business decision.

### Why can Copilot give different answers to the same question?

Microsoft Copilot uses generative AI, so responses can vary even when you ask the same or similar questions. Responses can also be incomplete or incorrect.

Review important answers and verify them against cited Business Central records or other authoritative sources.

Learn more about the capabilities and limitations of Microsoft Copilot in [Application card: Microsoft Copilot in Business Central](microsoft-copilot-in-business-central-application-card.md).

## Microsoft Copilot and other sources

### Can Microsoft Copilot use information other than Business Central data?

Yes. Microsoft Copilot can use information from sources other than Business Central, such as information from the web.

If you have a Microsoft Copilot license, Copilot can also use work data available through Work IQ, such as information from emails, chats, meetings, and files, subject to your permissions.

### Can Microsoft Copilot use agents?

Microsoft Copilot can provide access to agents depending on your Microsoft Copilot license and configuration.

However, you can't currently invoke Business Central first-party agents and third-party agents built by using the Business Central agent framework from Microsoft Copilot in Business Central.

## Availability and languages

### In which countries or regions is Microsoft Copilot available?

The availability of Microsoft Copilot in Business Central can depend on the country or region where your Business Central environment is located.

Learn more about current availability in [Copilot and agents country/region availability and supported languages](copilot-agents-region-language-availability.md).

### Which languages can I use with Microsoft Copilot?

Microsoft Copilot supports prompts and responses in multiple languages.

Learn more about languages supported by Microsoft Copilot in [Supported languages for Microsoft Copilot](https://support.microsoft.com/microsoft-365-copilot/supported-languages-for-microsoft-365-copilot).

Business Central feature availability can also depend on your Business Central country or region and language. Learn more in [Copilot and agents country/region availability and supported languages](copilot-agents-region-language-availability.md).

## Privacy and responsible AI

### Where can I learn about data handling, privacy, and responsible AI?

For information specific to Microsoft Copilot in Business Central, including its capabilities, intended uses, limitations, permissions, and use of Business Central data, see [Application card: Microsoft Copilot in Business Central](microsoft-copilot-in-business-central-application-card.md).

For information that applies to Microsoft Copilot generally, see [Application card: Microsoft Copilot for organizations](/microsoft-365/copilot/microsoft-365-copilot-application-card).

## Troubleshooting

### What can I do if the Copilot pane doesn't open?

Check the following conditions:

- Your environment runs a version of Business Central that supports Microsoft Copilot in Business Central.
- **Chat** is active on the **Copilot & agent capabilities** page.
- You have permission to use the capability.

If you don't administer Business Central, contact your administrator.

Learn more about setup and access in [Configure Copilot and agent capabilities](enable-ai.md).

## Related information

- [Use Microsoft Copilot in Business Central (preview)](chat-with-copilot.md)  
- [Application card: Microsoft Copilot in Business Central](microsoft-copilot-in-business-central-application-card.md)  
- [Configure Copilot and agent capabilities](enable-ai.md)  
- [Copilot and agents country/region availability and supported languages](copilot-agents-region-language-availability.md)  