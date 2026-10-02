---
title: Shopify Tax Matching FAQ for Business Central
description: Get answers about how Shopify Tax Matching uses data, suggests tax setup, handles review, and protects customer information.
ms.date: 09/30/2026
ms.update-cycle: 180-days
ms.custom:
  - responsible-ai-faqs
ms.topic: faq
author: andreipa
ms.author: andreipa
ms.reviewer: jswymer
ms.collection:
  - bap-ai-copilot
ai-usage: ai-assisted
---

# FAQ for Shopify Tax Matching

These frequently asked questions (FAQ) describe the AI impact of Shopify Tax Matching in [!INCLUDE [prod_short](includes/prod_short.md)].

## What is Shopify Tax Matching?

Shopify provides tax details for an order as tax lines that include a free-text title and a tax rate. To calculate tax when it creates a sales document, [!INCLUDE [prod_short](includes/prod_short.md)] needs a Tax Area and structured Tax Jurisdictions. Shopify Tax Matching suggests Tax Jurisdictions for tax lines on imported Shopify Orders.

Before AI matching runs, the Shopify connector uses its standard tax setup. Depending on the **Tax Area Priority** setting, the connector either uses the customer's Tax Area Code or uses address information from the Shopify Order to find a mapping on the **Shopify Tax Areas** page. If the Shopify Order still doesn't have a Tax Area, Shopify Tax Matching can suggest how to map its tax lines.

Shopify Tax Matching is available only in the US version of Business Central in the current release. Like the Shopify connector, the feature is supported only in Business Central online.

## What are the capabilities of Shopify Tax Matching?

Shopify Tax Matching runs only when all the following conditions apply:

- **Tax Matching Agent Enabled** is turned on for the Shopify shop.
- The **Shopify Tax Matching Agent** capability is active for the company.
- The Shopify Order isn't tax exempt.
- The Shopify Order doesn't have a Tax Area assigned or selected.
- One or more tax lines on the Shopify Order have a blank **Tax Jurisdiction Code**.

Shopify Tax Matching uses generative AI to compare the title of each tax line with the Tax Jurisdictions configured in [!INCLUDE [prod_short](includes/prod_short.md)]. It uses the tax rate and limited location information to help identify the best match. It returns a suggested Tax Jurisdiction Code, a confidence level, and a short explanation. [!INCLUDE [prod_short](includes/prod_short.md)] checks each suggestion against the Tax Jurisdictions in the company before it uses the suggestion.

If AI matching isn't available, the connector continues with its standard tax processing. You can use the **Shopify Tax Areas** setup or complete the tax mapping manually.

To suggest matches, Shopify Tax Matching sends the following information to the AI service:

- A tax-line identifier, title, rate, and channel-liable status for each tax line that has a blank **Tax Jurisdiction Code**.
- The codes and descriptions of all existing Tax Jurisdictions.
- The ship-to country or region, state or county, and city.
- The **Auto Create Tax Jurisdictions** setting.

Shopify Tax Matching doesn't send customer names, email addresses, phone numbers, street addresses, postal codes, item details, order numbers, tax amounts, or other customer details.

After Shopify Tax Matching suggests matches, [!INCLUDE [prod_short](includes/prod_short.md)]:

- Fills in the **Tax Jurisdiction Code** on the tax lines when the suggested jurisdiction exists.
- Uses an existing Tax Area that contains the same combination of Tax Jurisdictions. If no such Tax Area exists, the feature can create one when **Auto Create Tax Areas** is turned on.
- Creates a missing Tax Detail rate for the Tax Jurisdiction and Tax Group, effective on the Shopify Order date. For tax lines for shipping charges, the feature uses the Tax Group from the shop's Shipping Charges Account.
- Compares the Shopify rate with the rate in [!INCLUDE [prod_short](includes/prod_short.md)]. If the rates differ, the feature keeps the existing rate and holds the Shopify Order for review.

**Auto Create Tax Jurisdictions** is off by default. When you turn it on, the feature can create a Tax Jurisdiction if it can't find a match. The feature marks a new jurisdiction as **Created by Agent** and not verified. Approving the tax match for a Shopify Order also verifies the new jurisdictions used by that order. **Auto Create Tax Areas** is on by default.

## How does review and approval work?

You configure review by using **Tax Match Review Mode**. The default setting is **Always**. The available options are:

- **Always**: Review every AI-assisted match.
- **Low Confidence Only**: Review matches with medium or low confidence. The feature treats newly created Tax Jurisdictions as low-confidence matches.
- **Never**: Don't require review based only on confidence. Newly created Tax Jurisdictions can remain unverified unless another condition holds the Shopify Order for review.

Regardless of the selected review mode, the feature holds the Shopify Order when AI matching can't identify a Tax Jurisdiction for a tax line or the Shopify rate differs from the rate in [!INCLUDE [prod_short](includes/prod_short.md)]. You can't create a sales document until you resolve these issues.

The **Tax Match Review** page shows the tax lines, suggested Tax Jurisdictions, confidence levels, explanations, Shopify rates, and rates from [!INCLUDE [prod_short](includes/prod_short.md)]. You can change a suggested Tax Jurisdiction before you approve the match.

When the Shopify Order is held for review, choose **Approve** to approve its tax match and allow sales document creation. Approval also verifies Tax Jurisdictions that Shopify Tax Matching created and used for the Shopify Order. Choose **Undo Approval** to return the Shopify Order to review and mark those jurisdictions as not verified again.

To resolve a rate conflict, you can choose the **Use Shopify Rate** action. The action creates or updates the Tax Detail for the selected Tax Jurisdiction and Tax Group, effective on the Shopify Order date. Tax Details are shared tax setup, so the change can affect other documents that use the same Tax Jurisdiction and Tax Group on or after that date.

Notifications and indicators on the Shopify Order and sales document show whether a tax match requires review. On the **Tax Match Review** page, you can also review the confidence and explanation for each suggestion and open the related tax setup.

## What is the intended use of Shopify Tax Matching?

Shopify Tax Matching is intended to:

- Suggest how to map free-text Shopify tax descriptions to Tax Jurisdictions configured in [!INCLUDE [prod_short](includes/prod_short.md)].
- Reduce repetitive work for customers who use the US version of Business Central and process Shopify Orders with multiple tax jurisdictions.
- Help create missing Tax Jurisdictions when you turn on automatic creation.

You can instead maintain Tax Areas and Tax Jurisdictions manually, use the standard **Tax Area Priority** and **Shopify Tax Areas** setup, or use a third-party tax service.

Shopify Tax Matching doesn't calculate tax, determine tax liability, file tax returns, or replace tax or compliance advice. It maps imported tax descriptions to tax setup in [!INCLUDE [prod_short](includes/prod_short.md)].

## How was Shopify Tax Matching evaluated? What metrics measure its performance?

The evaluation coverage includes AI Test Toolkit accuracy suites for tax jurisdiction matching and creation, tax detail setup, shipping tax, tax area construction, eligibility checks, and the end-to-end flow. Automated tests also cover review modes, rate conflicts, and tax-liable and tax-exempt behavior.

Responsible AI testing covers prompt injection, harmful content, jailbreaks, and red-team scenarios. The evaluation checks whether the feature produces the expected tax jurisdiction mapping, tax area, rate-conflict handling, and review outcome. This test coverage doesn't imply a production accuracy percentage or volume metric.

## What are the limitations of Shopify Tax Matching? How can users minimize their impact?

- **Suggestions can be wrong or incomplete.** When you first enable Shopify Tax Matching for a shop, keep **Tax Match Review Mode** set to **Always**. Review the confidence level, explanation, Tax Jurisdiction, and rates before you approve a match.
- **Version support is limited.** The current release is available only in the US version of Business Central.
- **Tax title quality affects results.** Ambiguous, abbreviated, malformed, or unusual tax titles can reduce match quality. Missing or unclear Tax Jurisdiction descriptions can also reduce match quality.
- **Location information might not identify every jurisdiction.** Shopify Tax Matching uses the ship-to city, state or county, and country or region to distinguish jurisdictions with similar names. It doesn't use a street address or postal code, so it might not identify some special tax districts.
- **Automatically created Tax Jurisdictions require attention.** Use **Always** or **Low Confidence Only** if you want to review and verify every Tax Jurisdiction that Shopify Tax Matching creates.
- **Existing rates require review.** The feature doesn't replace an existing rate when the Shopify rate differs. Review the difference before you create a sales document. The **Use Shopify Rate** action changes shared Tax Details and can affect other documents.
- **The feature has a narrow tax purpose.** Shopify Tax Matching maps imported descriptions. It doesn't calculate taxes, establish liability, file returns, or provide tax or compliance advice.

## What operational factors and settings allow for effective and responsible use?

- Activate the **Shopify Tax Matching Agent** capability for the company, and then turn on **Tax Matching Agent Enabled** for each Shopify shop where you want to use the feature.
- Maintain clear Tax Jurisdiction codes and descriptions, and keep your Tax Areas, Tax Groups, and Tax Details up to date.
- Choose the **Tax Match Review Mode**, **Auto Create Tax Jurisdictions**, and **Auto Create Tax Areas** settings that fit your review requirements.
- Attend to notifications. On the **Tax Match Review** page, fill in any blank **Tax Jurisdiction Code** and review differences between the Shopify rate and the rate in [!INCLUDE [prod_short](includes/prod_short.md)].
- Before you choose **Use Shopify Rate**, understand that the action creates or updates the Tax Detail for the selected Tax Jurisdiction and Tax Group, effective on the Shopify Order date. The change can affect other documents that use the same tax setup.

## What data does Shopify Tax Matching collect?

To perform matching, the feature sends the AI service each unmatched tax line's technical identifier, title, rate, and channel-liable status; the codes and descriptions of existing Tax Jurisdictions; the ship-to country or region, state or county, and city; and the **Auto Create Tax Jurisdictions** setting. It doesn't send customer identity or contact details, street or postal address, item details, the Shopify order number, tax amounts, or order totals.

Separately, [!INCLUDE [prod_short](includes/prod_short.md)] records feature-specific telemetry about whether matching ran, succeeded, required review, or encountered an error. Some telemetry events include the Shopify order ID or the tax line's technical identifier. For rate differences, feature-specific telemetry can include the Tax Jurisdiction, Tax Group, Shopify rate, and the rate in [!INCLUDE [prod_short](includes/prod_short.md)]. This telemetry doesn't include the complete prompt or AI response.

For review and auditability, [!INCLUDE [prod_short](includes/prod_short.md)] stores matching decisions in the Activity Log. These records can include the tax-line title and rate, selected Tax Jurisdiction, confidence, explanation, and rate-conflict information. If Shopify Tax Matching creates a Tax Jurisdiction, the audit log records its code, country or region, and Shopify order ID.

[!INCLUDE[ai-data-collection](includes/ai-data-collection.md)]

## Is Shopify Tax Matching extensible?

Shopify Tax Matching doesn't currently expose public feature-specific extension points.

## Related information

[Set up and use Shopify Tax Matching](shopify/shopify-tax-matching.md)

[Configure Copilot and agent capabilities](enable-ai.md)

[Responsible AI FAQs](responsible-ai-overview.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
