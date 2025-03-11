---
title: Configure Copilot and AI capabilities
description: This article explains how to enable Copilot in an environment.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to
ms.date: 01/14/2025
ms.custom: bap-template
ms.collection:
  - bap-ai-copilot
ms.search.form: 7771,7772_Primary,7775_Primary
---
# Configure Copilot and AI capabilities

This article explains how to control Microsoft Copilot and other AI capabilities in Dynamics 365 Business Central. An administrator must complete these tasks.

Copilot is a system feature and an integral part of Business Central. Like most system features, you don't grant access to individual users, and you can't turn Copilot on or off. However, Copilot offers data governance controls and the option to deactivate individual Copilot and AI capabilities for each environment. There are different levels of access control for AI capabilities, depending on the feature:

- Allow data movement across geographical regions.

    This task is required only if your Business Central environment is in a different geography than the Azure OpenAI Service it uses. [Learn more about this task](#allow-data-movement-across-geographies).

- Activate the feature on the **Copilot & AI capabilities** page. [Learn more about this task](#activate-features).

If any of these requirements aren't met, the feature isn't available for use.

> [!NOTE]
> By default, starting with update 25.0, data movement across geographies is enabled, and all features are activated. This setup means Copilot is ready to use without any configuration unless you choose to deactivate specific features.

## Prerequisites

- You use Business Central online.
- You're an [administrator](#requirements-for-being-an-administrator) in Business Central.

## Allow data movement across geographies

This section applies only if the **Allow data movement** toggle switch appears near the top of the **Copilot & AI capabilities** page. If the **How do I govern my copilot data?** link appears instead of the **Allow data movement** option, skip this task.

![Screenshot that shows the Allow data movement option on the Copilot & AI capabilities page.](media/allow-data-movement-v2.png)

The presence of the **Allow data movement** toggle indicates that the location of your Business Central environment (where data is processed and stored) differs from the Azure OpenAI Service geography that Copilot uses. To enable Copilot, you must allow data movement between geographies. Learn more in [Copilot data movement across geographies](ai-copilot-data-movement.md).

You can choose to disallow data movement, which deactivates Copilot and all features. To allow or disallow data movement across geographies:

1. In Business Central, search for and open the **Copilot & AI capabilities** page.
1. Switch the **Allow data movement** toggle on or off as desired.

After an Azure OpenAI Service becomes available in the geography of your Business Central environment, your environment is automatically connected to it. At that point, the **Allow data movement** toggle no longer appears on the **Copilot & AI capabilities** page.

## Activate features

Copilot and AI capabilities are active by default when they're made available in preview or become generally available. On the **Copilot & AI capabilities** page, you can turn individual features off or on again for all users.

1. In Business Central, search for and open the **Copilot & AI capabilities** page.
1. The page lists all available Copilot and AI-related features and their status (*Active* or *Inactive*). The features are divided into two sections: preview and generally available.

    - To turn on a feature, select it in the list, and then select **Activate**.
    - To turn off a feature, select it in the list, and then select **Deactivate**.

    [![Screenshot that shows the Activate and Deactivate buttons for the feature lists on the Copilot & AI capabilities page.](media/copilot-and-ai-capabilties-page.svg)](media/copilot-and-ai-capabilties-page.svg#lightbox)

## Granting user access

Copilot and AI capabilities can offer functionality that is intended for any users across your organization or for specific user roles. Most Copilot and AI capabilities offer access control through permissions and permission sets in Business Central's permission management system. Learn more about permissions and permission sets in [Assign permissions to users and groups](ui-define-granular-permissions.md).

The following table lists the permissions that are required to use the Copilot features that Business Central provides.

| Copilot feature | Required permissions |
|---|---|
| Analysis assist | **DATA ANALYSIS - EXEC** permission set or execute permission on system object 9640 **Allow Data Analysis mode**. These permissions are the same permissions that are required to access the analysis mode. |
| Autofill | **Copilot Sys Features** permission set or execute permission on system object 9700 **Allow Copilot Autofill**. |
| Bank reconciliation assist | Permission on page 7250 **Bank Acc. Rec. AI Proposal** and page 7252 **Trans. To GL Acc. AI Proposal**. |
| Chat | There are no permissions or permission sets that control access to chat on a per-user basis. If chat is activated, it's available to all users. |
| Suggest substitute items| Permission on page 7410 **Item Subst. Suggestion** and page 7411 **Item Subst. Suggestion Sub**.|
| Map e-documents | Permission on page 6166 **E-Doc. PO Copilot Prop**. |
| Marketing text suggestions | Permission on page 5836 **Copilot Marketing Text**. |
| Sales line suggestions | Permission on page 7275 **Sales Line AI Suggestions** and page 7276 **Sales Line AI Suggestions Sub**. |
|Sales Order Agent|Learn more in [Manage agent permissions and user access](sales-order-agent-setup.md#manage-agent-permissions-to-objects-data-and-ui-elements).|

To grant or deny access to specific non-Microsoft Copilot and AI capabilities, consult the feature's documentation or publisher for the required permissions.

## Requirements for being an administrator

You need SUPER permission in your Business Central user account or one of the following Business Central licenses:

- Delegated Admin agent - Partner
- Delegated Helpdesk agent - Partner
- Internal Admin
- Internal BC Administrator
- Dynamics 365 Administrator

Business Central doesn't yet offer granular, object-level permissions so that only specific administrators can configure Copilot.

## Next steps

For the Sales Order Agent, there are a few more steps you must complete before the agent is ready for use. Learn more in [Set up Sales Order Agent](sales-order-agent-setup.md#configure-and-activate-sales-order-agent).

For other Copilot features, you're ready to try them out. Learn more in the following articles:

- [Add marketing text to items with Copilot](item-marketing-text.md)
- [Analyze list data with Copilot](analysis-assist.md)
- [Autofill fields with Copilot](autofill-fields-with-copilot.md)
- [Chat with Copilot](chat-with-copilot.md)
- [Map e-documents to purchase order lines with Copilot](map-edocuments-with-copilot.md)
- [Process sales quotes and orders with Sales Order Agent](sales-order-agent-process.md)
- [Reconcile bank accounts with Copilot](bank-reconciliation-with-copilot.md)
- [Suggest lines on sales orders with Copilot](sales-suggest-sales-lines-with-copilot.md)
- [Suggest substitute items with Copilot](suggest-item-substitutions-copilot.md)
- [Suggest number series with Copilot](suggest-number-series-copilot.md)

## Related information

[Troubleshoot Copilot and AI capabilities](ai-copilot-troubleshooting.md)  
[FAQ for analysis assist](faqs-analysis-assist.md)  
[FAQ for autofill with Copilot](faqs-autofill.md)  
[FAQ for bank reconciliation assist](faqs-bank-reconciliation.md)  
[FAQ for chat with Copilot](faqs-chat-with-copilot.md)  
[FAQ for mapping e-documents with purchase orders](faqs-map-edocuments.md)  
[FAQ for marketing text suggestions](faqs-marketing-text.md)  
[FAQ for sales line suggestions](faq-sales-suggest-sales-lines-with-copilot.md)  
[FAQ for suggest substitute items](faq-suggest-item-substitutions-with-copilot.md)  
[Marketing text suggestions overview](ai-overview.md)
