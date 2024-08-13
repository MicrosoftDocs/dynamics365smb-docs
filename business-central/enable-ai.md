---
title: Configure Copilot and AI capabilities
description: This article explains how to enable Copilot in an environment.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to
ms.date: 08/13/2024
ms.custom: bap-template
ms.search.form: 7775
ms.collection:
  - bap-ai-copilot
---

# Configure Copilot and AI capabilities

This article explains how to control Microsoft Copilot and other AI capabilities in Dynamics 365 Business Central. An administrator must complete these tasks.

Copilot is a system feature and an integral part of Business Central. As is true of most system features, you don't grant access to individual users, and you can't turn Copilot on or off. However, Copilot offers data governance controls and the option to deactivate individual Copilot and AI capabilities for each environment. There are different levels of access control for AI capabilities, depending on the feature:

- Allow data movement across geographical regions.

    This task is required only if your Business Central environment is in a different geography than the Azure OpenAI Service that it uses. [Learn more about this task](#allow-data-movement-across-geographies).

- Activate the feature on the **Copilot & AI capabilities** page. [Learn more about this task](#activate-features).

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

## Activate features

All Copilot and AI capabilities are active by default when they are made available in preview or become generally available. On the **Copilot & AI capabilities** page, you can turn individual features off or on again for all users.

1. In Business Central, search for and open the **Copilot & AI capabilities** page.
1. The page lists all available Copilot and AI-related features and their current status. (The status can be either *Active* or *Inactive*.) The features are divided into two sections: one for features that are in preview and one for features that are generally available.

    - To turn on a feature, select it in the list, and then select **Activate**.
    - To turn off a feature, select it in the list, and then select **Deactivate**.

    [![Screenshot that shows the Activate and Deactivate buttons for the feature lists on the Copilot & AI capabilities page.](media/copilot-and-ai-capabilties-page.svg)](media/copilot-and-ai-capabilties-page.svg#lightbox)

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

- Delegated Admin agent - Partner
- Delegated Helpdesk agent - Partner
- Internal Admin
- Internal BC Administrator
- Dynamics 365 Administrator

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
