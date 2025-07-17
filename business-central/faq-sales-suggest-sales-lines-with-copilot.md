---
title: FAQ for suggest sales lines with Copilot
description: This FAQ provides information about the AI technology used in Business Central for sales line suggestions.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: jswymer
ms.topic: faq
ms.search.form:
ms.date: 04/01/2025
ms.update-cycle: 180-days
ms.service: dynamics-365-business-central
ms.collection: bap-ai-copilot
ms.custom: responsible-ai-faqs
---

# FAQ for Sales Line Suggestions with Copilot (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

These frequently asked questions (FAQ) describe the AI impact of the sales line suggestions feature in [!INCLUDE [prod_short](includes/prod_short.md)].

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## What is Sales Line Suggestions with Copilot?

Sales line suggestions with Copilot can assist with creating lines on sales documents such as sales quotes, orders, and invoices based on structured input or natural language. The feature isn't a general-purpose chat, but a highly specific and integrated experience that you can use on sales documents. The feature offers two distinct skills that help you find data about individual products or entire documents.

## What are the capabilities of sales line suggestions with Copilot?

* Find products

  Information that describes products is stored in multiple places in [!INCLUDE [prod_short](includes/prod_short.md)]. For example, item numbers and descriptions are stored in the **Item** table, multiple barcodes are stored in the **Item Reference** table, and product properties are stored in the **Item Attributes** table. While you might prompt for *Red bicycle*, the actual product might be *Crimson tourer*, where *Bicycle* is a product category and *red* is an attribute.

* Find a document by reference

  People often repeat a previous order, or at least use it as a starting point. But it might be tricky to find the right order in a stack of orders. You might remember some of the order's ID, which can be a company-assigned number or a reference number received from a customer. Being able to use prompts such as *Need last invoice from April* should help you find an order faster.

* Find a document by reference and then find a product within the document

  Use a combination of the **Find product** and **Find document** capabilities. You can use a prompt such as, *Need red bicycle from last invoice from April*.

* Find products from attachments
  
  If your typical sale contains multiple products, your customer might send you an attachment with details about the products they want to buy. Being able to understand the attachment and generate suggestions based its content makes it faster to create sales lines.

## What is the intended use of sales line suggestions?

* Find products

  Intended to answer user prompts to find products based on vague, incomplete, or inaccurate descriptions.

  Because the average number of items (products/services) for [!INCLUDE [prod_short](includes/prod_short.md)] customers is 10.000, finding the right ones might be tough without prior experience or knowledge. The way data is stored in [!INCLUDE [prod_short](includes/prod_short.md)] doesn’t make things easier, because you need to do multiple searches or filtering exercises on the different pages that store product data.

  Copilot extracts the requested products and quantities and identifies the main search term and attributes, so you can enter your prompt more quickly. Then, Copilot does an advanced search through multiple related tables, applies synonyms, corrects typos, and evaluates the quality of the search output.

* Find a document by reference

  Quickly reply to inquiries by finding sales documents for a customer using partial or approximate information.

  In B2B environments, people often deal with recurring requests, and order processors often need to repeat a past document or at least use it as a starting point. However, finding the right document might be tricky:

  - Through its lifecycle, a sales document can evolve from quote to order to posted invoice or shipment. Documents can also be archived.
  - You might have an ID, but don't know what it represents. For example, is it order number, invoice number, or external reference?
  - Sometimes you have a date or a period, but not an ID for a document.

  To find a source document manually, you need to open multiple pages and use search and filter multiple times. Copilot simplifies this process with a single, natural language query that lets you express what you're looking for in your own way.

  *	*Get products from order 103031*
  *	*Need products from last invoice in August*

* Find products from attachment
  
  Intended to find product suggestions based on the content of a file.
  
  * Copilot analyzes an attached file to understand its format, such as the column separator and data type. It also identifies columns that contain a product, quantity, and unit of measure (optional). You can change review and change the mapping if needed.
  * Copilot passes the contents of columns that contain product details to the **Find product** capability to find the requested items.

## How was sales line suggestions evaluated? What metrics are used to measure performance?

The feature underwent extensive testing where numerous prompts in US English representing both typical use and use by bad actors. Testing was based on [!INCLUDE [prod_short](includes/prod_short.md)]'s demonstration data and a large labeled product catalog available as open source.

This feature is built in accordance with Microsoft's Responsible AI Standard. Learn more about responsible AI from Microsoft at [Empowering responsible AI practices](https://aka.ms/RAI).

## What are the limitations of sales line suggestions? How can users minimize the impact of the sales line suggestions limitations when using the system?

* Find products
  
  Find products works best in the English language. While you can use this feature in any of the languages that [!INCLUDE [prod_short](includes/prod_short.md)] supports, item searches in other languages might be less accurate.

If your industry or domain overlaps with what Microsoft considers sensitive topics (such as drugs, violence, adult entertainment, and so on) Copilot might defer to neutral, curated responses, or give inaccurate responses.

Sales line suggestions only populates fields where the **Type** is **Item**, and the **No.**, **Unit of Measure**, and **Quantity**. Other fields, including **Unit Price** and **Location**, use the current logic and are filled in either based on item settings or values from the document header.

The **Variant Code** isn't currently supported. If you can ship a product in two different colors, for example, Copilot finds the product but leaves the **Variant Code** field empty. You need to fill in the field manually.

How you name your items can affect output. For example, using cryptic abbreviations versus friendly names can reduce output quality.

For items, the following table lists the tables and fields that Copilot searches.

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

  Currently, you can start sales line suggestions from sales orders, invoices, and quotes, and search the following documents:

  * Sales orders
  * Sales quotes
  * Sales invoices
  * Posted sales invoices
  * Posted sales shipments
  * Blanket sales order

  Copilot searches the following fields:

  * Document No.
  * External Document No.
  * Your Reference
  * Quote No.
  * Document Date
  * Sell-to Customer No.

  Copilot doesn't return all lines of the type Item. It transfers only item numbers, variant codes, and quantities. Copilot converts quantities from the source document to the **Sales Unit of Measure**.

* Find products from attachment

Currently, this feature supports only CSV files. If you received files in a different format, for example Microsoft Excel, use the **Save As** action to save the worksheet as a CSV.

To safeguard against scenario where a large file is uploaded, the CSV file is limited to 10,000 characters.

## In which geographies and languages is sales line suggestions available?

[!INCLUDE[copilot-geo-and-language-availability-en-only](includes/copilot-geo-and-language-availability-en-only.md)]

## What operational factors and settings allow for effective and responsible use of the feature?

AI-powered suggestions might sometimes be incorrect or incomplete. You should always review the accuracy of Copilot's suggestions before you choose whether to keep them. Copilot’s suggestions aren't saved to the [!INCLUDE [prod_short](includes/prod_short.md)] database until you choose the **Keep it** button and exit the Copilot window. You can edit and correct any suggestions before you choose to keep it, or after they're inserted in a sales document.

### What is expected of administrators and end-users when using Sales lines suggestions?

After an administrator enables the **Sales lines suggestions** feature, each user can choose whether to use it always, sometimes, or never.  

Administrators make the overall decision on whether to use Copilot capabilities in [!INCLUDE [prod_short](includes/prod_short.md)]. If administrators enable Copilot, they should be sure to grant access to the appropriate users.

> [!NOTE]
> * We don't support this feature in [!INCLUDE [prod_short](includes/prod_short.md)] on-premises or private cloud.
> * Partners can't extend this feature. That means partner developers can't modify, replace, or extend it.

## Is Copilot the only means to create sales lines?  

No, use of Copilot is optional. [!INCLUDE [prod_short](includes/prod_short.md)] offers non-AI-powered ways to insert sales lines or copy documents. Organizations can use both approaches at the same time.  

## How do I give feedback about AI-generated content?  

Each time Copilot provides suggestions, you can provide feedback to Microsoft directly from the Copilot window, using the Like and Dislike buttons. Your feedback remains anonymous and we use this data to improve the quality of the service.  

## Related information

[Suggest lines on sales orders with Copilot](sales-suggest-sales-lines-with-copilot.md)  
[Configure Copilot and agent capabilities](enable-ai.md)  
[Responsible AI FAQs for Dynamics 365 Business Central](responsible-ai-overview.md)  
