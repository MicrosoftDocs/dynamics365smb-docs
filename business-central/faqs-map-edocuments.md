---
title: FAQ for mapping e-documents with purchase orders
description: This FAQ provides information about the AI technology used in Business Central, key considerations and details about how AI is used, how it was tested and evaluated, and any specific limitations.
ms.date: 10/13/2025
ms.update-cycle: 180-days
ms.custom: 
  - responsible-ai-faqs
ms.topic: faq
author: brentholtorf
ms.author: bholtorf
ms.reviewer: jswymer
ms.collection:
  - bap-ai-copilot
---

# FAQ for mapping e-documents with purchase orders using Copilot (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

These frequently asked questions (FAQ) describe the AI impact of **E-documents Matching Assistance** feature in [!INCLUDE [prod_short](includes/prod_short.md)].

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## What is E-documents Matching Assistance?

Electronic documents (e-documents) serve as the foundation for modern business transactions. They represent critical paperwork such as invoices and receipts that flow in both directions through delivery and receipt. You can generate and transmit electronic invoices digitally in a structured format that facilitates automated invoice processing. However, handling incoming digital invoices can be more intricate for accounts payable teams.  

In small and medium-sized businesses (SMBs), the accounts payable team plays a pivotal role in accurately tracking vendor obligations. Their primary responsibility is to accurately record incoming invoices. Achieving precision can require effort, particularly when they reconcile external invoices from vendors with existing purchase orders. Discrepancies in codes, descriptions, and units of measurement often present challenges because these elements might not match across different systems and companies. Also, unexpected costs, such as transportation fees, might appear as separate line items that need manual adjustment. Accountants must also include invoice numbers and dates in the documents. Importantly, the relationship between purchase orders and external invoices isn't always one-to-one. You might receive multiple external invoices for the same purchase order.

Historically, [!INCLUDE [prod_short](includes/prod_short.md)] could generate new purchase invoices based on received electronic invoices. However, manually matching invoices with existing purchase orders was a time-consuming and error-prone process.

**E-documents Matching Assistance** uses generative AI to streamline this process by automating the analysis of external electronic invoices. The feature allows accountants to ask Copilot to match lines on incoming electronic invoices with lines on purchase orders in [!INCLUDE [prod_short](includes/prod_short.md)].

## What are capabilities of the E-documents Matching Assistance?

Copilot provides AI-powered assistance to match received digital invoice with existing purchase orders in [!INCLUDE [prod_short](includes/prod_short.md)]. Copilot matches lines based on the information:

- Similarity of descriptions
- Units of measure
- Quantities available for invoicing
- Amounts

Copilot identifies similar descriptions if they have proper unit of measures and the prices, but it can also find matches in more complex cases. For example, it can identify whether an electronic invoice has two lines with a variant of the same item, and just one line in the purchase order. [!INCLUDE [prod_short](includes/prod_short.md)] matches these lines as long as the descriptions are similar and the prices are the same.

Copilot doesn't connect to your e-documents endpoint service to retrieve or send digital vouchers. This task remains fully within your control and is a prerequisite to using Copilot's assistance. This condition is true, regardless of whether the digital documents are added to [!INCLUDE [prod_short](includes/prod_short.md)] using a connection with an endpoint service or entered manually.  

## What is the intended use of the E-documents Matching Assistance?  

The goal of the **E-documents Matching Assistance** feature is to assist the accounts payable team match existing purchase orders with incoming electronic invoices. Much of this activity revolves around string matching. [!INCLUDE [prod_short](includes/prod_short.md)] offers a feature that automates some of this activity. LLMs (large language models) have been identified as an opportunity to supplement that feature and further reduce manual effort.  

## How was E-documents Matching Assistance evaluated? What metrics are used to measure performance?

This feature was tested using combinations of the following information:

- External item descriptions
- Units of measure
- Quantities and amounts
- Standard item descriptions
- Different languages
- Other parameters that cover the typical variations and data limits for each field 

Test data represents both typical use and use by bad actors. Performance was measured compared to manual matching the same data in electronic invoices and purchase orders.

## What are the limitations of E-documents Matching Assistance? How can users minimize the impact of the E-documents Matching Assistance limitations when using the system?

**E-documents Matching Assistance** performs best when external (e-invoice) and internal ([!INCLUDE [prod_short](includes/prod_short.md)]) item descriptions, and unit of measures are all in the same language. Mixed languages or mixed language of item descriptions often result in fewer matches and suggestions.  

Suggested matching of items from e-invoices with items in purchase orders performs best in English language. Although you can use this feature in any language that [!INCLUDE [prod_short](includes/prod_short.md)] supports, you might experience fewer item matches in other languages. Learn more in the section [In which geographies and languages is E-documents Matching Assistance available?](#in-which-geographies-and-languages-is-e-documents-matching-assistance-available).

## In which geographies and languages is E-documents Matching Assistance available?

[!INCLUDE[copilot-geo-and-language-availability-en-only](includes/copilot-geo-and-language-availability-en-only.md)]

## What operational factors and settings allow for effective and responsible use of the feature?

Copilot supplements the mapping algorithm that [!INCLUDE [prod_short](includes/prod_short.md)] already provides and maps the lines that the algorithm didn't.

### What is expected of users while using E-Documents Matching Assistance?

<!--Not sure that this is the right content for this section. Seems like it belongs more in the overview article because it's more related to how to use the feature-->

After you map incoming electronic invoices with purchase orders, you must map the lines on the documents.

The **Purchase Order Mapping** page shows all lines from both of documents. Here, you can do the mapping manually, which can be difficult if there are many lines.

You can use **E-Documents Matching Assistance** to map lines based on the following criteria:

- Similarity in their descriptions
- Units of measure
- Quantities available for invoicing
- Amounts

Copilot's matches might be incorrect or incomplete. You should always review their accuracy before you choose to keep them. Copilot’s matches and suggestions are saved in [!INCLUDE [prod_short](includes/prod_short.md)] when you choose **Keep it** and exit Copilot. You can edit and correct any matches or suggestions before you choose to keep them. 

### What is expected of administrators and users when operating E-Documents Matching Assistance?

Users, such as accountants or others who receive e-invoices, should always review the accuracy of matches and suggestions provided by Copilot before choosing to keep them. We recommend that you review the purchase order lines to verify their accuracy and find any discrepancies. You decide whether to use the **E-Documents Matching Assistance**. Even when the **E-Documents Matching Assistance** is enabled by administrators and available, you can still choose to use it always, sometimes, or never.  

Administrators make the overall decision on whether to use Copilot in [!INCLUDE [prod_short](includes/prod_short.md)]. If they enable Copilot, administrators should ensure they grant access to the appropriate.

> [!NOTE]
> - We don't support the feature for [!INCLUDE [prod_short](includes/prod_short.md)] on-premises or in private clouds.
> - Partners can't extend this feature. Partner developers can't modify, replace, or extend this feature. 

## Is Copilot the only way to match e-documents to purchase orders?  

No, whether you use Copilot is up to you. [!INCLUDE [prod_short](includes/prod_short.md)] offers non-AI-powered ways to match items from received electronic invoice with items on purchase orders in [!INCLUDE [prod_short](includes/prod_short.md)]. Organizations can also use both approaches at the same time.  

## How do I give feedback about AI-generated content?  

Each time Copilot provides matches or suggestions, you can provide feedback to Microsoft directly from the Copilot window, using the **Like** and **Dislike** controls. Your feedback remains anonymous, and we use this data to improve the quality of the service.  

[!INCLUDE[ai-data-collection](includes/ai-data-collection.md)]

## Related information

[E-Documents overview](finance-edocuments-overview.md)  
[Map e-documents to purchase order lines with Copilot](map-edocuments-with-copilot.md)  
[Copilot data movement across geographies](ai-copilot-data-movement.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
