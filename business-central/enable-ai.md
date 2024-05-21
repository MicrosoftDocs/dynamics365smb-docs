---
title: Configure Copilot and AI capabilities
description: This article explains how to enable Copilot in an environment.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to
ms.date: 04/16/2024
ms.custom: bap-template
ms.search.form: 7775
ms.collection:
  - bap-ai-copilot
---

# Configure Copilot and AI capabilities

<!--[!INCLUDE[ai-preview](includes/ai-preview.md)]-->

<!--This article explains how you can control the ability to create AI-powered item marketing text with Copilot for your organization. This task is done by an admin. There are two requirements that you must fulfill to make the feature available to users:-->

This article explains how to control Microsoft Copilot and other AI capabilities in Dynamics 365 Business Central. An administrator must complete these tasks.

Copilot is a system feature and an integral part of Business Central. As is true of most system features, you don't grant access to individual users, and you can't turn Copilot on or off. However, Copilot offers data governance controls and the option to deactivate individual Copilot and AI capabilities for each environment. There are different levels of access control for AI capabilities, depending on the feature:

- Allow data movement across geographical regions.

    This task is required only if your Business Central environment is in a different geography than the Azure OpenAI Service that it uses. [Learn more about this task](#allow-data-movement-across-geographies).

- Activate the feature on the **Copilot & AI capabilities** page. [Learn more about this task](#activate-features).

<!-- For 2024 there are no AI features governed by **Feature Management**, so this section is not shown
- Enable the specific feature if it's governed by **Feature Management**.

  Check whether  of 2024 release wave 1, chat with Copilot, marketing text suggestions, and bank account reconciliation assist features are included under **Feature Management**. [Learn more](#enable-feature-in-feature-management)
<!-- 
- Enable the specific feature, if it's still governed by **Feature Management**.

  In 2023 release wave 2, both the marketing text suggestions and bank account reconciliation assist features are included under **Feature Management**. [Learn more](#enable-feature-in-feature-management)-->

If any of these requirements aren't met, the feature isn't available for use.

## Prerequisites

- You're using Business Central online.
- You're an [administrator](#requirements-for-being-an-administrator) in Business Central.

## Allow data movement across geographies

This task applies only if the **Allow data movement** option appears near the top of the **Copilot & AI capabilities** page. If the **How do I govern my copilot data?** link appears instead of the **Allow data movement** option, skip this task.

![Screenshot that shows the Allow data movement option on the Copilot & AI capabilities page.](media/allow-data-movement-v2.png)

The presence of the **Allow data movement** option indicates that the location of your Business Central environment (that is, the geography where data is processed and stored) differs from the Azure OpenAI Service geography that Copilot uses. To enable Copilot, you must allow data movement between geographies. [Learn more about data movement](ai-copilot-data-movement.md).

To allow data movement outside your geographical region, follow these steps:

1. In Business Central, search for and open the **Copilot & AI capabilities** page.
1. Turn on the **Allow data movement** option.

    > [!NOTE]
    > For environments in the West Europe and North Europe Azure regions, the **Allow data movement** option is turned on by default.

To opt out of data movement, turn off the **Allow data movement** option.

After an Azure OpenAI Service becomes available in the geography of your Business Central environment, your environment is automatically connected to it. At that point, the **Allow data movement** option no longer appears on the **Copilot & AI capabilities** page.

<!-- Don't review
| Australia, United Kingdom, United States | Within the respective geographical region |
| Europe, France, Germany, Norway, Switzerland  | Sweden or Switzerland |
| Asia Pacific, Brazil, Canada, India, Japan, Singapore, South Africa, South Korea, United Arab Emirates  | United States |-->



<!--Note

If your environment is hosted in North America, Copilot will use an Azure OpenAI endpoint in North America to process your data.
If your environment is hosted in Europe, Copilot will use an Azure OpenAI endpoint in Europe to process your data.
If your environment is hosted anywhere else, Copilot will use an Azure OpenAI endpoint outside of the region in which the environment is hosted.
To opt in 

Copilot and other AI capabilities use Azure OpenAI Service.  and are provided by default to only those customers with environments that have United States as their geography for data processing and storage. While the Azure OpenAI Service is available in multiple geographies including Australia, Canada, United States, France, Japan and UK, Copilot does not follow the same regional rollout schedule.

Meanwhile, customers with environments outside the United States can use Copilot AI features by opting in to share relevant data with the Azure OpenAI Service in United States or Switzerland.

The information in the following table outlines the Azure OpenAI service that's used by the Copilot services based on the geography of their Dynamics 365 environment when they opt-in to share data.-->

## Activate features

All Copilot and AI capabilities are active by default when they are made available in preview or become generally available. On the **Copilot & AI capabilities** page, you can turn individual features off or on again for all users.

1. In Business Central, search for and open the **Copilot & AI capabilities** page.
1. The page lists all available Copilot and AI-related features and their current status. (The status can be either *Active* or *Inactive*.) The features are divided into two sections: one for features that are in preview and one for features that are generally available.

    - To turn on a feature, select it in the list, and then select **Activate**.
    - To turn off a feature, select it in the list, and then select **Deactivate**.

    [![Screenshot that shows the Activate and Deactivate buttons for the feature lists on the Copilot & AI capabilities page.](media/copilot-and-ai-capabilties-page.svg)](media/copilot-and-ai-capabilties-page.svg#lightbox)

<!-- don't review 

<!-- For 2024 there are no AI features governed by **Feature Management**, so this section is not shown
## Enable feature in Feature Management

When individual Copilot capabilities are released in Business Central minor updates, these capabilities are optional until the next major update. **Feature Management** is used to turn on or off features that are in preview, like bank reconciliation, and some features that are generally available, like marketing text suggestions. [Learn more about feature management](/dynamics365/business-central/dev-itpro/administration/feature-management).

1. In Business Central, search for and open the **Feature Management** page.
2. To enable a feature, set the **Enabled for** column to **All users**. To disable a feature, set the **Enabled for** column to **None**. Use the following table to help you determine the switch that applies to the Copilot and AI capability you want to enable:

   - **Feature Preview: Bank account reconciliation with Copilot** enables the bank account reconciliation assist feature.
   - **Feature Preview: Chat with Copilot** enables the chat with Copilot feature.
   - **Feature preview: Create AI-powered product descriptions with Copilot** enables the marketing text suggestions feature.

   For more information about feature management in general, go to [Feature Management](/dynamics365/business-central/dev-itpro/administration/feature-management).-->

## Granting user access

Copilot and AI capabilities can offer functionality that is intended for any users across your organization or for specific user roles. Most Copilot and AI capabilities offer access control through permissions and permission sets in Business Central's permission management system. [Learn more about permissions and permission sets](ui-define-granular-permissions.md).

The following table lists the permissions that are required to use the Copilot features that Business Central provides.

| Copilot feature | Required permissions |
|---|---|
| Analysis assist | The **DATA ANALYSIS - EXEC** permission set or execute permission on system object 9640, **Allow Data Analysis mode**. These permissions are the same permissions that are required to access the analysis mode. |
| Bank reconciliation assist | Permission on page 7250, **Bank Acc. Rec. AI Proposal**, and page 7252, **Trans. To GL Acc. AI Proposal**. |
| Chat | There are no permissions or permission sets that control access to chat on a per-user basis. If chat is activated, it's available to all users. |
| Map e-documents | Permission on page 6166, **E-Doc. PO Copilot Prop**. |
| Marketing text suggestions | Permission on page 5836, **Copilot Marketing Text**. |
| Sales line suggestions | Permission on page 7275, **Sales Line AI Suggestions**, and page 7276, **Sales Line AI Suggestions Sub**. |

To grant or deny access to specific non-Microsoft copilot and AI capabilities, consult the feature's documentation or publisher to identify the required permissions.

## Requirements for being an administrator

You must have either SUPER permissions in your Business Central user account or one of the following Business Central licenses:

- Delegated Admin
- Delegated Helpdesk
- Global Admin
- BC Admin
- D365 Admin

Business Central doesn't yet offer granular, object-level permissions so that only specific administrators can configure Copilot.

## Next steps

After you enable and consent to the features, you're ready to try them out. Go to the following articles:

- [Add marketing text to items with Copilot](item-marketing-text.md)
- [Analyze list data with help of Copilot](analysis-assist.md)
- [Chat with Copilot](chat-with-copilot.md)
- [Map e-documents to purchase order lines with Copilot](map-edocuments-with-copilot.md)
- [Reconcile bank accounts with Copilot](bank-reconciliation-with-copilot.md)
- [Suggest lines on sales orders with Copilot](sales-suggest-sales-lines-with-copilot.md)

## See also

[Troubleshoot Copilot and AI capabilities](ai-copilot-troubleshooting.md)  
[FAQ for analysis assist](faqs-analysis-assist.md)  
[FAQ for bank reconciliation assist](faqs-bank-reconciliation.md)  
[FAQ for chat with Copilot](faqs-chat-with-copilot.md)  
[FAQ for mapping e-documents with purchase orders](faqs-map-edocuments.md)  
[FAQ for marketing text suggestions](faqs-marketing-text.md)  
[FAQ for sales line suggestions](faq-sales-suggest-sales-lines-with-copilot.md)  
[Marketing text suggestions overview](ai-overview.md)
