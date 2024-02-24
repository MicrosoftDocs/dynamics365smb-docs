---
title: FAQ for Mapping E-Documents with Purchase Orders
description: This FAQ provides information about the AI technology used in Business Central, along with key considerations and details about how AI is used, how it was tested and evaluated, and any specific limitations.
ms.date: 02/23/2024
ms.custom: 
  - responsible-ai-faqs
ms.topic: article
author: brentholtorf
ms.author: bholtorf
ms.reviewer: altotovi
ms.collection:
  - bap-ai-copilot
---

# FAQ for mapping e-documents with purchase orders using Copilot

These frequently asked questions (FAQ) describe the AI impact of [Feature] feature in [Product].

## What is E-documents Matching Assistance? 

Electronic documents (e-documents) serve as the foundation for modern business transactions. They encompass critical paperwork, including invoices and receipts, flowing in both directions (delivery and receipt). This means that electronic invoices can be generated and transmitted as digital invoices in a structured format, facilitating automated invoice processing. However, handling incoming digital invoices can be more intricate for accounts payable teams.  

Within small and medium-sized businesses (SMBs), the accounts payable team plays a pivotal role in accurately tracking vendor obligations. Their primary responsibility lies in meticulously recording incoming invoices. Achieving this precision involves significant effort, particularly when reconciling external invoices from vendors with existing purchase orders. Discrepancies in codes, descriptions, and units of measurement often present challenges, as these elements may not align across different systems and companies. Additionally, unexpected costs—such as transportation fees—may appear as separate line items, necessitating manual adjustments. Accountants must also include invoice numbers and proper dates in the documents. Importantly, the relationship between purchase orders and external invoices is not always one-to-one; users in Business Central (BC) often receive multiple external invoices for the same purchase order. 

In the past, Business Central could effortlessly generate new purchase invoices based on received electronic invoices. However, manually matching this data with existing purchase orders was a time-consuming process prone to potential errors. However, **E-documents Matching Assistance** using generative AI streamlines this process by automating the analysis of external electronic invoices. Accountants can now efficiently and accurately record these invoices in BC. The feature allows for requesting matching lines from incoming electronic invoices to align with lines in existing purchase orders within Business Central. 

## What are capabilities of the E-documents Matching Assistance? 

Copilot provides AI-powered assistance with the following task:

### Matching received digital invoice with existing purchase order  

Instead of a time-consuming and not-fault-tolerant process, Business Central now uses **E-documents Matching Assistance** with generative AI to match lines, based on:  
- Similarity of descriptions, 
- Unit of measures,   
- Quantities available for invoicing, and 
- Amounts.  

That means Business Central will easily identify similar description if they have proper unit of measures and the prices, but it can identify even more complex cases. For example, it would be identified if an electronic invoice has two lines with a variant of the same item, and just one line in the purchase order; Business Central will connect these lines as long as descriptions are similar, and the prices are the same. 

Copilot doesn't connect to your e-documents endpoint service to retrieve or send digital vouchers. This task remains fully within your control and is a prerequisite to begin using Copilot's assistance, whether those digital documents are added to Business Central using a connection with endpoint service, or entered manually.  

## What is the intended use of the E-documents Matching Assistance?  

The goal of the **E-documents Matching Assistance** usage is to assist the account payable team in what is recurring, and tedious activity known as matching existing purchase orders with incoming electronic invoices. Much of this activity revolves around string matching. Busines Central offers a feature that automates some of this activity, and LLMs have been identified as an opportunity to supplement that feature and further reduce manual effort.  

## How was E-documents Matching Assistance evaluated? What metrics are used to measure performance? 

This functionality was tested using combinations of different external item descriptions, unit of measure, quantities, and amounts and standard item descriptions and with other parameters in Business Central that cover the typical variations and data limits for each field and in different languages. Test data represents both typical usage and usage by bad actors. Performance was measured in comparison to manual matching of the same data in electronic invoices and purchase orders.   

## What are the limitations of E-documents Matching Assistance? How can users minimize the impact of the E-documents Matching Assistance limitations when using the system? 

**E-documents Matching Assistance** performs best when external (e-invoice) and internal (Business Central) item descriptions, and unit of measures are all in the same language. Mixed languages or mixed language of item descriptions often result in fewer matches and suggestions.  

Suggested matching of items from e-invoices with items in purchase orders performs best in English language. While this feature can be operated in any of the available Business Central languages, users might experience fewer item matches in other languages.    

## In which geographies and languages is E-documents Matching Assistance available? 

This capability is available to any environment country/region localization and in any user language with the exception of Canada. Due to limited language support, the system will not be available initially to Canadian customers due to regulatory language compliance. For customer environments located in countries/regions where Azure OpenAI Service isn't deployed, administrators must first consent to allowing movement of data across boundaries for Business Central to connect to Azure OpenAI service and for this capability to be available.  

For more information on language, see previous question about limitations.   

## What operational factors and settings allow for effective and responsible use of the feature?

[Describe the operational factors and ranges within which the system is expected to perform reliably and safely. List the choices that end users can make (e.g., customization, settings, etc.), with a description of how those choices may impact system behavior in the real world.]

## Is Copilot the only means to completing E-documents Matching?  

No – use of Copilot is optional. Business Central offers traditional, non-AI-powered means of matching items from received electronic invoice with items in existing purchase order in Business central. Both the traditional approach and Copilot can be used simultaneously within an organization.  

## How do I give feedback about AI-generated content?  

Each time Copilot provides matches or suggestions, you can provide feedback to Microsoft directly from the Copilot window, using the like and dislike controls. Your feedback remains anonymous and we use this data to improve the quality of the service.  

## See also

[E-Documents overview](finance-edocuments-overview.md)
[Map e-documents to purchase order lines with Copilot](map-edocuments-with-copilot.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
