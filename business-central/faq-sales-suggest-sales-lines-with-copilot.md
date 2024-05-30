---
title: FAQ for suggest sales lines with Copilot
description: This FAQ provides information about the AI technology used in Business Central.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.form:
ms.date: 02/02/2024
ms.service: dynamics-365-business-central
ms.collection: bap-ai-copilot
ms.custom: responsible-ai-faqs
---

# FAQ for Sales Line Suggestions with Copilot (preview)

[!INCLUDE[preview-banner](includes/preview-banner.md)]

These frequently asked questions (FAQ) describe the AI impact of the sales line suggestions feature in [!INCLUDE [prod_short](includes/prod_short.md)].

[!INCLUDE[production-ready-preview-dynamics365](includes/production-ready-preview-dynamics365.md)]

## What is Sales Line Suggestions with Copilot?

Sales line suggestion with Copilot can assist with creating lines on sales documents such as sales quotes, orders, and invoices based on structured input or natural language. The feature isn't a general-purpose chat, but a highly specific and integrated experience that you can use on sales documents. The feature offers two distinct skills that help you find data about individual products or the entire documents.

## What are capabilities of sales line suggestions with Copilot?

* Find products

  Information that describes products is stored in multiple places in [!INCLUDE [prod_short](includes/prod_short.md)]. For example, item numbers and descriptions are stored in the **Item** table, multiple barcodes are stored in the **Item Reference** table, and product properties are stored in the **Item Attributes** table. While you might prompt for *Red bicycle*, the actual product might be *Crimson tourer*, where *Bicycle* is a product category and *red* is an attribute.

* Find a document by reference

  People often repeat a previous order, or at least use it as a starting point. But it might be tricky to find the right order in a stack of orders. You might remember some of the order's ID, which can be a company assigned number or a reference number received from a customer. Being able to use prompts such as *Need last invoice from April* should help you find an order faster.

## What is the intended use of sales line suggestions with Copilot?

* Find products

  Intended to answer user prompts to find products based on vague, incomplete, or inaccurate descriptions.

  Because the average number of items (products/services) for [!INCLUDE [prod_short](includes/prod_short.md)] customers is 10.000, finding the right ones might be tough without prior experience or knowledge. The way data stored in [!INCLUDE [prod_short](includes/prod_short.md)] doesn’t make things easier, because you need to do multiple searches or filtering exercises on the different pages that store product data.

  Copilot extracts the requested products and quantities and identifies the main search term and attributes, so you can enter your prompt more quickly. Then, Copilot does an advanced search through multiple related tables, applies synonyms, corrects typos, and evaluate the quality of the search output.

* Find a document by reference

  Intended to answer user inquiries to find existing sales documents for a specific customer using partial or approximate information.

  In B2B environments, people often deal with recurring requests, and order processors can get inquiries to repeat a past document or at least use it as a starting point. But it might be tricky to find one for several reasons:

  - Through its lifecycle, a sales document can evolve from quote to order to posted invoice or shipment. Documents can also be archived.
  - You might have an exact identifier, but can't say what it represents. For example, is it order number, invoice number, or external reference?
  - Sometimes you have a date or a period, but not an ID for document.

  To find a source document manually, you'll need to open multiple pages and use search and filter multiple times. However, Copilot can simplify this in a single, natural language query that lets you expresses what you're looking for in your own way. 

  *	*Get products from order 103031*
  *	*Need products from last invoice in August*

## How was sales line suggestions with Copilot evaluated? What metrics are used to measure performance?

The feature underwent extensive testing where numerous prompts in US English representing both typical use and use by bad actors. Testing was based on [!INCLUDE [prod_short](includes/prod_short.md)]'s demonstration data and a large labeled product catalog available as open source.

This feature is built in accordance with Microsoft's Responsible AI Standard. [Learn more about responsible AI from Microsoft](https://aka.ms/RAI).

## What are the limitations of sales line suggestions with Copilot? How can users minimize the impact of the sales line suggestions with Copilot limitations when using the system?

* Find products
  
  Find products works best in English language. While you can use this feature in any of the languages that [!INCLUDE [prod_short](includes/prod_short.md)] supports, item searches in other languages might be less accurate.

If your industry or domain overlaps with what Microsoft considers sensitive topics (such as drugs, violence, adult entertainment, and so on) Copilot might defer to neutral, curated responses, or give inaccurate responses.

Sales lines suggestions only populates fields **Type** as **Item**, **No.**, and **Quantity** as described. Other fields, including **Unit of Measure**, **Unit Price**, and **Location** use the current logic and are populated either based on item settings or inherited values from the document header.

The **Variant Code** is not currently supported. If you can ship a product in two different colors, for example, Copilot will find the needed product but will leave the **Variant Code** field empty. You'll need to fill in the field manually.

How you name your products can affect output. For example, using cryptic abbreviations versus friendly names can reduce output quality.

For products, the following table lists the tables and fields that Copilot searches.

|Table  |Fields  |
|---------|---------|
|**Items**     |  * No.<br>* Description<br>* Description 2<br>* Search Description<br>* GTIN<br>* Vendor Item Number       |
|**Item Variant**     | * Code<br>* Description<br>* Description 2	        |
|**Item Reference**     | * Reference No.<br>* Description<br>* Description 2        |
|**Item Attributes**     | * Name<br>* Value        |
|**Item Category**     |  * Code<br>* Description<br>* Parent Category - 1 Level	       |
|**Item Translation**     | * Language<br>* Description<br>* Description 2	        |
|**Item Identifier**     |  * Code       |
|**Extended text Line**     |  * Text      |

* Find documents by reference

  Currently, you can start Sales lines suggestion from sales orders, invoices, and quotes, and search the following documents:

  * Sales orders
  * Sales quotes
  * Sales invoices
  * Posted sales invoices
  * Posted sales shipments

  Copilot searches the following fields

  * Document No.
  * External Document No.
  * Your Reference
  * Quote No.
  * Document Date
  * Sell-to Customer No.

  Copilot doesn't return all lines of the type Item. Only items numbers, variant codes, and quantities are transferred. Quantities from the source document are converted to the **Sales Unit of Measure**.

## In which geographies and languages is Sales lines suggestions available?

With the exception of Canada, this feature is available to all environment country/region localization and in all supported languages. Due to limited language support, the feature won't initially be available to Canadian customers due to regulatory language compliance. For this capability to be available for customer environments located in countries/regions where Azure OpenAI Service isn't deployed, administrators must first consent to allowing their data to move across boundaries for [!INCLUDE [prod_short](includes/prod_short.md)] to connect to Azure OpenAI service.  

## What operational factors and settings allow for effective and responsible use of the feature?

AI-powered suggestions might sometimes be incorrect or incomplete. You should always review the accuracy of Copilot's suggestions before you choose whether to keep them. Copilot’s suggestions aren't saved to the [!INCLUDE [prod_short](includes/prod_short.md)] database until you choose the **Keep it** button and exit the Copilot window. You can edit and correct any suggestions before you choose to keep it, or after they're inserted in a sales document.

### What is expected of administrators and end-users when using Sales lines suggestions?

Each individual users chooses whether or not to use **Sales lines suggestions**. Even when the feature is enabled by administrators and available, you can choose to use it always, sometimes, or never.  

Administrators make the overall decision on whether to use Copilot capabilities in [!INCLUDE [prod_short](includes/prod_short.md)]. If administrators enable Copilot, they should be sure to grant access to the appropriate users.   

> [NOTE!]
> - We don't support this feature in [!INCLUDE [prod_short](includes/prod_short.md)] on-premises or private cloud.
> - Partner's can't extend this feature. That means partner developers can't modify, replace, or extend it.

## Is Copilot the only means to create sales lines?  

No, use of Copilot is optional. [!INCLUDE [prod_short](includes/prod_short.md)] offers non-AI-powered ways to insert sales lines or copy documents. Organizations can use both approaches at the same time.  

## How do I give feedback about AI-generated content?  

Each time Copilot provides suggestions, you can provide feedback to Microsoft directly from the Copilot window, using the Like and Dislike buttons. Your feedback remains anonymous and we use this data to improve the quality of the service.  

## See also

[Suggest lines on sales orders with Copilot](sales-suggest-sales-lines-with-copilot.md)  
[Configure Copilot and AI capabilities](enable-ai.md)  
[Responsible AI FAQs for Dynamics 365 Business Central](responsible-ai-overview.md)  
