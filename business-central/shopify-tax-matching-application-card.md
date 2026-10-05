---
title: Application card for Shopify Tax Matching
description: Learn how Shopify Tax Matching uses AI, how Microsoft evaluated the feature, its limitations, and how to use it responsibly.
ms.date: 10/02/2026
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

# Application card for Shopify Tax Matching (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

## What is an Application or Platform card?

Microsoft’s Application and Platform Cards are intended to help you understand how our AI technology works, the choices application owners can make that influence application performance and behavior, and the importance of considering the whole application, including the technology, the people, and the environment. Application Cards are created for AI applications and Platform Cards are created for AI platform services. These resources can support the development or deployment of your own applications and can be shared with users or stakeholders impacted by them.

As part of its commitment to responsible AI, Microsoft adheres to [six core principles](https://www.microsoft.com/ai/principles-and-approach/?msockid=3da790040c776d6f2b5485e40de56c06#ai-principles): fairness, reliability and safety, privacy and security, inclusiveness, transparency, and accountability. These principles are embedded in the [Responsible AI Standard](https://cdn-dynmedia-1.microsoft.com/is/content/microsoftcorp/microsoft/final/en-us/microsoft-brand/documents/Microsoft-Responsible-AI-Standard-General-Requirements.pdf), which guides teams in designing, building, and testing AI applications. Application and Platform Cards play a key role in operationalizing these principles by offering transparency around capabilities, intended uses, and limitations. For further insight, readers are encouraged to explore Microsoft’s [Responsible AI Transparency Report](https://cdn-dynmedia-1.microsoft.com/is/content/microsoftcorp/microsoft/msc/documents/presentations/CSR/Responsible-AI-Transparency-Report-2025.pdf). Customers are required to use services in compliance with the [Microsoft Enterprise AI Services Code of Conduct](/legal/ai-code-of-conduct) for organizations, which outlines how to engage with AI responsibly.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Overview

Shopify Tax Matching helps organizations map tax information from imported Shopify orders to tax setup in the US version of [!INCLUDE [prod_short](includes/prod_short.md)]. Shopify provides tax details as tax lines with free-text titles and rates, while [!INCLUDE [prod_short](includes/prod_short.md)] requires structured Tax Jurisdictions and Tax Areas to create sales documents. The feature uses generative AI to compare each unmatched tax-line title with the organization's configured Tax Jurisdictions. It uses the tax rate and limited location information to help identify the best match. Like the Shopify connector, the feature is supported only in Business Central online.

The feature is intended for organizations that use the Shopify connector and process orders that can contain multiple United States tax jurisdictions. It reduces repetitive mapping work by suggesting Tax Jurisdiction Codes, reporting confidence levels and explanations, and optionally creating missing Tax Jurisdictions and Tax Areas. Users remain responsible for reviewing matches and resolving missing jurisdictions or rate differences before creating a sales document. For setup and workflow information, go to [Set up and use Shopify Tax Matching](shopify/shopify-tax-matching.md).

## Key terms

The following list provides a glossary of key terms related to Shopify Tax Matching:

| Term                      | Description                                                                                                                                                                                                                                        |
| ------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Confidence level**      | An indication of how strongly AI analysis supports a suggested Tax Jurisdiction match. The review mode can use the confidence level to determine whether an order requires review.                                                                   |
| **Shopify Order**         | An order imported from Shopify by using the Shopify connector. Shopify Tax Matching evaluates unmatched tax lines on eligible Shopify Orders.                                                                                                      |
| **Tax Area**              | A combination of Tax Jurisdictions used to calculate tax for a location. The feature can use an existing Tax Area or create one with the same combination of matched Tax Jurisdictions when automatic creation is enabled.                         |
| **Tax Detail**            | Tax setup that specifies a rate for a Tax Jurisdiction and Tax Group from an effective date. The feature can create a missing Tax Detail or identify a difference between the Shopify rate and an existing rate.                                   |
| **Tax Jurisdiction**      | A structured tax authority configured in [!INCLUDE [prod_short](includes/prod_short.md)]. Shopify Tax Matching suggests a Tax Jurisdiction Code for each unmatched Shopify tax line and can create a missing jurisdiction when automatic creation is enabled. |
| **Tax line**              | Tax information supplied by Shopify for an order. A tax line includes a free-text title and tax rate that the feature uses as inputs for matching.                                                                                                |
| **Tax Match Review Mode** | A setting that controls whether AI-assisted matches require review based on confidence. Available modes are **Always**, **Low Confidence Only**, and **Never**.                                                                                    |

## Key features or capabilities

The key features and capabilities outlined here describe what Shopify Tax Matching is designed to do and how it performs across supported tasks.

- **Tax Jurisdiction matching**: Shopify Tax Matching compares the title of each unmatched Shopify tax line with existing Tax Jurisdictions. It uses the tax rate and ship-to country or region, state or county, and city to help select a match, then returns a suggested code, confidence level, and explanation.
- **Validated suggestions**: Before AI matching runs, the Shopify connector uses the configured **Tax Area Priority** to select the customer's Tax Area Code or find an address mapping on the **Shopify Tax Areas** page. AI matching runs only if the order still doesn't have a Tax Area. [!INCLUDE [prod_short](includes/prod_short.md)] validates each suggested Tax Jurisdiction against company data before using it. If AI matching isn't available, standard tax processing continues, and users can complete the mapping manually.
- **Tax setup assistance**: The feature can use an existing Tax Area that contains the same combination of matched Tax Jurisdictions or create one when **Auto Create Tax Areas** is enabled. It can create a missing Tax Detail rate effective on the Shopify Order date. For shipping-charge tax lines, it uses the Tax Group from the shop's Shipping Charges Account. When **Auto Create Tax Jurisdictions** is enabled, it can also create a missing Tax Jurisdiction, which remains not verified until approved.
- **Rate-conflict detection**: The feature compares the Shopify rate with the rate in [!INCLUDE [prod_short](includes/prod_short.md)]. If they differ, it keeps the existing rate and holds the Shopify Order for review instead of silently replacing shared tax setup.
- **Review and approval**: Notifications and indicators on the Shopify Order and sales document show when a tax match requires review. On the **Tax Match Review** page, users can inspect tax lines, suggestions, confidence levels, explanations, and rates; open the related tax setup; change a suggested jurisdiction; approve or undo approval; and resolve a rate conflict by choosing **Use Shopify Rate**.
- **Feature-specific extensibility**: Shopify Tax Matching doesn't currently expose public feature-specific extension points.

## Intended uses

Shopify Tax Matching can be used in tax-mapping scenarios for organizations that use the US version of Business Central and import orders through the Shopify connector. Some examples of use cases include:

- **Map tax descriptions to existing tax setup**: An organization can use Shopify Tax Matching to suggest Tax Jurisdictions for free-text Shopify tax descriptions that don't already have a Tax Jurisdiction Code. This can reduce repetitive manual mapping when orders contain multiple jurisdictions. Users can review the suggestion, confidence, explanation, and rates before approval.
- **Complete missing tax setup**: The feature creates a missing Tax Detail for the matched Tax Jurisdiction and Tax Group. An organization can also allow it to create a missing Tax Jurisdiction or Tax Area by enabling the corresponding automatic-creation setting. Newly created Tax Jurisdictions are marked as not verified, and the configured review process can require a user to verify them. This use case helps organizations process new jurisdiction combinations while retaining human oversight.
- **Identify and resolve rate differences**: The feature can flag a Shopify rate that differs from the existing rate in [!INCLUDE [prod_short](includes/prod_short.md)] and hold the order for review. A user can investigate the difference and, when appropriate, use the Shopify rate. Because this action changes shared Tax Details, users should assess its effect on other documents.

Shopify Tax Matching has a defined and narrow action space. It maps imported tax descriptions to configured tax setup; it doesn't calculate tax, determine tax liability, file tax returns, or provide tax or compliance advice.

## Models and training data

Shopify Tax Matching uses generative AI models to power the matching experience that users see. The feature documentation doesn't identify specific foundation models. For more information about AI capabilities and the data used by Copilot features in [!INCLUDE [prod_short](includes/prod_short.md)], see [Configure Copilot and agent capabilities](enable-ai.md) and [Responsible AI FAQs](responsible-ai-overview.md).

## Performance

Shopify Tax Matching is designed for eligible, non-tax-exempt Shopify Orders in the US version of Business Central that don't have a Tax Area assigned or selected and have at least one tax line with a blank **Tax Jurisdiction Code**. The **Shopify Tax Matching Agent** capability must be active for the company, and **Tax Matching Agent Enabled** must be turned on for the Shopify shop.

The intended inputs are structured text and numeric data from unmatched tax lines, including a technical identifier, title, rate, and channel-liable status. Shopify Tax Matching also receives the codes and descriptions of existing Tax Jurisdictions, limited ship-to location information, and the **Auto Create Tax Jurisdictions** setting. It doesn't receive customer identity or contact information, street or postal addresses, item details, order numbers, tax amounts, or order totals.

The expected output for each unmatched tax line is a suggested Tax Jurisdiction Code, confidence level, and short explanation. [!INCLUDE [prod_short](includes/prod_short.md)] validates the suggestion against company data, constructs or selects related tax setup, and determines whether the Shopify Order requires review. When AI matching can't identify a jurisdiction or detects a rate difference, the feature holds the order for user review.

Performance is strongest when Shopify tax titles and Tax Jurisdiction descriptions are clear and when the relevant tax setup is current. The current release is available only in the US version of Business Central.

## Limitations

Understanding the limitations of Shopify Tax Matching is crucial for using it within safe and effective boundaries. While we encourage customers to leverage AI in their innovative solutions or applications, it's important to note that Shopify Tax Matching wasn't designed for every possible scenario. We encourage users to refer to either the Microsoft Enterprise [AI Services Code of Conduct](/legal/ai-code-of-conduct) (for organizations) or the Code of Conduct section in the [Microsoft Services Agreement](https://www.microsoft.com/en-ca/servicesagreement#3_codeOfConduct) (for individuals) as well as the following considerations when choosing a use case:

- **Suggestions can be wrong or incomplete**: Generative AI matching doesn't guarantee that a suggestion is correct. When first enabling Shopify Tax Matching, keep **Tax Match Review Mode** set to **Always** and review the confidence, explanation, jurisdiction, and rates. Users remain accountable for approving the tax mapping.
- **Geographic support is limited**: The current release is available only in the US version of [!INCLUDE [prod_short](includes/prod_short.md)]. Don't rely on the feature for tax jurisdictions outside its supported geography. Continue to use standard Shopify tax setup, manual mapping, or an appropriate third-party tax service for unsupported scenarios.
- **Input quality affects matching**: Ambiguous, abbreviated, malformed, or unusual Shopify tax titles can reduce match quality. Missing or unclear Tax Jurisdiction descriptions can have the same effect because Shopify Tax Matching compares the available text. Maintain clear jurisdiction descriptions and review uncertain matches.
- **Location data is limited**: Shopify Tax Matching uses the ship-to city, state or county, and country or region, but it doesn't use a street address or postal code. This limitation can make it difficult to distinguish special tax districts or jurisdictions with similar names. Users should verify matches when limited location information isn't enough to establish the correct jurisdiction.
- **Automatically created setup requires oversight**: A Tax Jurisdiction created by Shopify Tax Matching is marked as not verified. Select **Always** or **Low Confidence Only** when the review process must verify every new jurisdiction. Without review, an automatically created jurisdiction can remain unverified.
- **Existing rates aren't replaced automatically**: When the Shopify rate differs from the existing rate, the feature keeps the existing rate and holds the order for review. Choosing **Use Shopify Rate** creates or updates a shared Tax Detail that can affect other documents using the same Tax Jurisdiction and Tax Group. Review the effective date and downstream impact before making this change.
- **The feature has a narrow tax purpose**: Shopify Tax Matching maps imported tax descriptions to tax setup. It doesn't calculate taxes, determine tax liability, file returns, or replace professional tax or compliance advice. Don't use its output as a determination of legal or tax obligations.

## Evaluations

Performance and safety evaluations assess whether AI applications are operating reliably and securely by examining factors like groundedness, relevance, and coherence while identifying the risks of generating harmful content. The following evaluations were conducted with safety components already in place, which are also described in the **Safety components and mitigations** section.

### Evaluation data for quality and safety

Our evaluation data is custom-built to assess AI application performance across key areas of safety and quality, simulating real-world scenarios and risks. We begin by identifying relevant evaluation aspects of concern based on multi-disciplinary research and expert input. These concerns are translated into targeted evaluation objectives and guide formulation of evaluation metrics. For safety, we create adversarial prompts to elicit undesirable or edge-case responses, which are then scored using AI-assisted annotators trained to assess alignment with Microsoft’s safety standards. For quality, we craft rubric-based prompts relevant to scenarios including evaluating retrieval-augmented generation (RAG) applications and agents. Datasets are curated from diverse sources including synthetic and public datasets to simulate real-world user scenarios. Using the curated datasets, both evaluations undergo iterative refinement and human alignment to improve metric efficacy and reliability. This methodology forms the foundation of repeatable, rigorous assessments that reflect how customers use evaluations to build better and safer AI.

### Custom evaluations

Custom evaluations use text and structured tax data to assess whether the feature produces the expected Tax Jurisdiction mapping, Tax Area, rate-conflict handling, and review outcome. AI Test Toolkit accuracy suites cover Tax Jurisdiction matching and creation, Tax Detail setup, shipping tax, Tax Area construction, eligibility checks, and the end-to-end flow. Automated tests also cover review modes, rate conflicts, and tax-liable and tax-exempt behavior.

An ideal result maps each eligible tax line to the expected Tax Jurisdiction, produces the correct supporting tax setup, and routes the Shopify Order to the appropriate review outcome. A suboptimal result includes an incorrect or missing jurisdiction, incorrect Tax Area or Tax Detail setup, or a failure to require review when a conflict exists. This coverage assesses expected behavior across test scenarios; it doesn't imply a production accuracy percentage or volume metric.

Responsible AI testing covers prompt injection, harmful content, jailbreaks, and red-team scenarios. These tests evaluate whether adversarial or unsafe text can cause the feature to depart from its narrow tax-matching purpose or produce an unsafe result.

## Safety components and mitigations

- **Eligibility controls**: Shopify Tax Matching runs only when the capability is active for the company and enabled for the Shopify shop. It doesn't run for tax-exempt orders, orders that already have a Tax Area, or orders without unmatched tax lines. These checks constrain the feature to its intended workflow.
- **Suggestion validation**: [!INCLUDE [prod_short](includes/prod_short.md)] checks every suggested code against Tax Jurisdictions in the company before using it. If AI matching isn't available, standard Shopify tax processing continues and users can map the tax information manually. This validation prevents the system from treating an unsupported code as configured tax setup.
- **Configurable human review**: **Tax Match Review Mode** defaults to **Always**, which requires review of every AI-assisted match. **Low Confidence Only** requires review for medium- and low-confidence matches and treats newly created Tax Jurisdictions as low confidence. **Never** doesn't require review based only on confidence, so a newly created jurisdiction can remain unverified. Regardless of the selected mode, an unidentified Tax Jurisdiction or rate difference holds the Shopify Order for review.
- **Controls for automatically created records**: **Auto Create Tax Jurisdictions** is off by default, and jurisdictions created by Shopify Tax Matching are marked as not verified. Approval verifies new jurisdictions used by the order, while undoing approval marks them as not verified again. **Auto Create Tax Areas** is separately configurable and is on by default.
- **Rate-change safeguards**: The feature doesn't automatically replace an existing tax rate when it differs from Shopify. It holds the order and requires a user to choose whether to use the Shopify rate. This safeguard makes the user aware that changing a shared Tax Detail can affect other documents.
- **Data minimization and auditability**: Matching excludes customer identity and contact details, street and postal addresses, item details, order numbers, tax amounts, and totals. Feature-specific telemetry can record whether matching ran, succeeded, required review, or encountered an error. Some events include the Shopify order ID or tax line's technical identifier; rate-difference events can include the Tax Jurisdiction, Tax Group, Shopify rate, and the rate in [!INCLUDE [prod_short](includes/prod_short.md)]. Telemetry doesn't include the complete prompt or AI response. The Activity Log can contain the tax-line title and rate, selected Tax Jurisdiction, confidence, explanation, and rate-conflict information. For a Tax Jurisdiction created by Shopify Tax Matching, it records the code, country or region, and Shopify order ID.

## Best practices for deploying and adopting Shopify Tax Matching

Responsible AI is a shared commitment between Microsoft and its customers. While Microsoft builds AI applications and platform services with safety, fairness, and transparency at the core, customers play a critical role in deploying and using these technologies responsibly within their own contexts. To support this partnership, we offer the following best practices for deployers and end users to help customers implement responsible AI effectively.

Deployers and end-users should:

Exercise caution and evaluate outcomes when using Shopify Tax Matching for consequential decisions or in sensitive domains: Consequential decisions are those that might have a legal or significant impact on a person’s access to education, employment, financial platforms, government benefits, healthcare, housing, insurance, legal platforms, or that could result in physical, psychological, or financial harm. Sensitive domains, such as financial platforms, healthcare, and housing, require particular care due to the potential for disproportionate impact on different groups of people. When using AI for decisions in these areas, ensure that impacted stakeholders can understand how decisions are made, appeal decisions, and update any relevant input data.

Evaluate legal and regulatory considerations: Customers need to evaluate potential specific legal and regulatory obligations when using any AI platforms and solutions, which may not be appropriate for use in every industry or scenario. Additionally, AI platforms or solutions are not designed for and may not be used in ways prohibited in applicable terms of service and relevant codes of conduct.

**End-users should:**

- **Begin with full review**: Keep **Tax Match Review Mode** set to **Always** when first enabling Shopify Tax Matching for a shop. Review the confidence, explanation, Tax Jurisdiction, and rates before approving each match. After assessing performance with your organization's data, choose a different review mode only if it meets your oversight requirements.
- **Maintain accurate tax setup**: Use clear Tax Jurisdiction codes and descriptions, and keep Tax Areas, Tax Groups, and Tax Details current. Clear source data improves matching and makes suggestions easier to evaluate.
- **Review automatically created jurisdictions**: Use **Always** or **Low Confidence Only** when you must review and verify every Tax Jurisdiction that Shopify Tax Matching creates. Check that the jurisdiction and related Tax Area reflect the organization's intended tax setup. Undoing approval marks the affected jurisdictions as not verified again.
- **Assess rate changes carefully**: Investigate differences between the Shopify rate and the rate in [!INCLUDE [prod_short](includes/prod_short.md)] before choosing **Use Shopify Rate**. The action creates or updates the Tax Detail for the selected Tax Jurisdiction and Tax Group from the Shopify Order date. Because Tax Details are shared, the change can affect other documents on or after that date.

## Related information

[Set up and use Shopify Tax Matching](shopify/shopify-tax-matching.md)

[Configure Copilot and agent capabilities](enable-ai.md)

[Responsible AI FAQs](responsible-ai-overview.md)
