---
title: Set up and use Shopify Tax Matching
description: Learn how to set up Shopify Tax Matching, review suggested tax jurisdiction matches, and approve tax setup for imported orders.
ms.date: 09/30/2026
ms.topic: how-to
author: andreipa
ms.author: andreipa
ms.reviewer: jswymer
ms.service: dynamics-365-business-central
ms.custom: bap-template
ai-usage: ai-assisted
---

# Set up and use Shopify Tax Matching (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Shopify Tax Matching suggests tax jurisdictions for unmatched tax lines on orders in the US version of Business Central. AI matching uses the tax-line title and rate, existing tax jurisdictions, and limited ship-to location information. It doesn't calculate tax, determine tax liability, file tax returns, or replace professional tax advice. For more information, see [Application card for Shopify Tax Matching](../shopify-tax-matching-application-card.md).

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Prerequisites

Before you enable Shopify Tax Matching, complete the following prerequisites:

- Use Business Central online. The Shopify connector isn't supported on-premises.
- Install the Shopify Connector NA extension. In the US version, the **Shopify Shops** page provides an installation notification when the extension isn't installed.
- On the **Copilot & agent capabilities** page, activate the **Shopify Tax Matching Agent** capability. For more information, see [Configure Copilot and agent capabilities](../enable-ai.md).
- Assign the **Shopify Tax Matching Agent** permission set to people who set up or review tax matches.
- Review your tax jurisdictions, tax areas, tax groups, and tax details. Clear codes and descriptions help AI matching suggest useful matches.

## Set up Shopify Tax Matching

Set up Shopify Tax Matching separately for each Shopify shop:

1. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, and then select the related link.
1. Select the shop where you want to use Shopify Tax Matching.
1. On the **Shopify Shop Card** page, turn on **Tax Matching Agent Enabled**.
1. In the **Tax Matching Agent** group, configure the remaining settings as needed.

The following table describes the settings:

|Field|Description|
|-|-|
|**Tax Matching Agent Enabled**|Turns on assisted matching for eligible imported orders. The setting is off by default.|
|**Auto Create Tax Jurisdictions**|Allows Shopify Tax Matching to create a tax jurisdiction when it can't find a suitable existing jurisdiction. The setting is off by default.|
|**Auto Create Tax Areas**|Allows the connector to create a tax area from the matched jurisdictions. The setting is on by default.|
|**Tax Area Naming Pattern**|Specifies the prefix for tax areas that the connector creates. The default prefix is `SHPFY-`.|
|**Tax Match Review Mode**|Specifies which AI-assisted matches require review. The default is **Always**.|

The review modes have the following effects:

- **Always** requires review of every AI-assisted match.
- **Low Confidence Only** requires review for medium- and low-confidence suggestions and newly created tax jurisdictions.
- **Never** doesn't require review based only on confidence.

## When Shopify Tax Matching processes an order

Shopify Tax Matching processes an imported order when all the following conditions are met:

- You use the US version of Business Central.
- The **Shopify Tax Matching Agent** capability is active for the company, and **Tax Matching Agent Enabled** is turned on for the shop.
- The order isn't tax exempt.
- The **Tax Area Code** on the order is blank.
- At least one tax line doesn't have a tax jurisdiction.

An unidentified tax jurisdiction or a difference between the Shopify rate and an existing tax detail rate always holds the order for review, regardless of the review mode.

## Review and approve a tax match

1. On the **Shopify Order** page, choose **Review and Approve Tax Match** or **Review Tax Match**.
1. On the **Tax Match Review** page, review the suggested **Tax Jurisdiction Code**, confidence, explanation, Shopify rate, and [!INCLUDE[prod_short](../includes/prod_short.md)] rate for each tax line.
1. Change any incorrect or incomplete **Tax Jurisdiction Code**. You can also open the related tax setup from the page.
1. If a Shopify rate differs from the existing rate, investigate the difference. To apply the Shopify rate, choose **Use Shopify Rate**.
1. Choose **Approve**. Approval requires a tax jurisdiction for every tax line, rebuilds the tax area from the final assignments, and verifies tax jurisdictions that Shopify Tax Matching created for the order.
1. Create the sales document after the order no longer requires tax review.

> [!IMPORTANT]
> **Use Shopify Rate** creates or updates a shared tax detail that takes effect on the Shopify order date. The change can affect other documents that use the same tax jurisdiction and tax group on or after that date. Review the effective date and downstream impact before you use the action.

Before you create a sales order or sales invoice, you can choose **Undo Approval** to return the Shopify order to a held state. The action also marks tax jurisdictions created for the match as not verified. Refunds inherit tax setup from the related Shopify order and don't run tax matching again.

## Related information

[Taxes in imported Shopify orders](synchronize-orders.md#taxes-in-imported-shopify-orders)

[Application card for Shopify Tax Matching](../shopify-tax-matching-application-card.md)

