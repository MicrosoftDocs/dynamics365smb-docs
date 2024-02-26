---
title: FAQ for suggest sales lines with Copilot
description: This FAQ provides information about the AI technology used in Business Central.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.topic: article
ms.search.form:
ms.date: 02/02/2024
ms.service: dynamics-365-business-central
ms.collection: bap-ai-copilot
ms.custom: responsible-ai-faqs
---

# FAQ for sales line suggestions with Copilot

These frequently asked questions (FAQ) describe the AI impact of the sales line suggestions feature in [!INCLUDE [prod_short](includes/prod_short.md)].

## What is sales line suggestions with Copilot?

Sales line suggestion with Copilot can assist with creating lines on sales documents such as sales quotes, sales orders, and invoices based on structured input or natural language. The Sales lines suggestions is not a general-purpose chat bot, but highly specific and integrated experience available from sales documents and offering two distinct skills. These skills help users find data they are looking for, either individual products or the whole documents.

## What are capabilities of sales line suggestions with Copilot?

* Finding products.
The information describing the product is stored in multiple places within [!INCLUDE [prod_short](includes/prod_short.md)] database, for example item number and item description are stored in the **Item** table, but multiple barcodes are stored in the **Item Reference** table, property of product are stored in the **Item Attributes**. While user may express need in *Red bicycle*, the actual product might be *Crimson tourer*, where *Bicycle* is a product category and *red* is an attribute.

* Finding document by reference
It is common to repeat the past order or at least to have it as a starting point. But it might be tricky to find one if there is a load of orders. Users might remember some id, which can be company assigned number or reference number received from customer. Accepting inquiry inquiries like *Need last invoice from April* should help user to start editing faster.
## What is the intended use of sales line suggestions with Copilot?

### Finding products.
Intended to answer users’ inquiries to find product based on vague, incomplete, or non-accurate description.

As the average number of Items (products/services) for [!INCLUDE [prod_short](includes/prod_short.md)] customers is 10.000, finding right ones might be tough without prior experience or knowledge. The way data stored in [!INCLUDE [prod_short](includes/prod_short.md)] doesn’t make tasks easier, as users need to perform multiple searches or filtering exercises among different pages that store part of the data deifning product. Users expect from [!INCLUDE [prod_short](includes/prod_short.md)] similar or superior experience comparing to what they see in online stores/marketplaces. Also, when creating sales documents there are multiple lines to be added, which makes the task even harder.

Copilot extracts requested products and quantities, identifies main search term and attributes enabling user to enter inquiry quicker. Then Copilot performs advanced search among multiple related tables, apply synonyms, correct typos and evaluate the quality of the search output. 

### Finding documents by reference.

Intended to answer users’ inquiries to find existing sales documents for specific customer using partial or approximate information.

In B2B environments, it is quite common to deal with recurring requests and order processors can get inquiries to repeat the past document or at least to have it as a starting point. But it might be tricky to find one for several reasons:
-	Through lifecycle a sales document can evolve from quote to order to posted invoice or shipment, it also can leave traits as archives.
-	User might have an exact identifier but cannot say what it represents: is it order number or invoice number or external reference. 
-	Sometimes users have a date or period but not identifier of document.

In order to find source document user will need to visit multiple pages and use search and filtering multiple times. [!INCLUDE [prod_short](includes/prod_short.md)] has a fast-growing user base with diverse users across the entire spectrum of expertise: from [!INCLUDE [prod_short](includes/prod_short.md)] newbies to experts, and from intense desktop users to casual users that only log in occasionally throughout the month. No matter their level of expertise, completing this search task requires significant cognitive switching. 

Users benefit from simplifying this task down to a single, natural language query that expresses what they are looking for in their own way. 
*	*Get products from order 103031*
*	*Need products from last invoice in August*


## How was sales line suggestions with Copilot evaluated? What metrics are used to measure performance?

* The feature underwent extensive testing where numerous prompts in US English representing both typical usage and usage by bad actors. Testing was based on [!INCLUDE [prod_short](includes/prod_short.md)]'s demonstration data and large labeled product catalog available as open source.
* This feature is built in accordance with Microsoft's Responsible AI Standard. [Learn more about responsible AI from Microsoft](https://aka.ms/RAI).

## What are the limitations of sales line suggestions with Copilot? How can users minimize the impact of the sales line suggestions with Copilot limitations when using the system?


### Finding products.
Finding product performs best in English language. While this feature can be operated in any of the available [!INCLUDE [prod_short](includes/prod_short.md)] languages, users might experience less accurate item search in other languages.

For customers that operate in industries/domains that overlap with what Microsoft considers sensitive topics (such as drugs, violence, sexual, etc.) Copilot may defer to neutral, curated responses, or give inaccurate responses. 

The Sales lines suggestions only populates fields **Type** as *Item*, **No.** and **Quantity** as described. Other fields, including **Unit of Measure**, **Unit Price**, **Location** will be populated using current business logic and will be populated either based on item settings or inherrited from the header of the document.
The **Variant Code** is not currently supported. If some product can be shipped in two different colors, the Copilot will find the needed product, but will leave the **Variant Code** field empty. You will need to populate field manually.

How customers name their products have impact on quality of output. Using cryptic abbreviations versus highly verbose names will reduce the likelihood of proper output.

For product search following is the list of tables and field on which search relies on:
*	**Items**
*   No.
*   Description
*   Description 2
*   Search Description
*   GTIN 
*   Vendor Item Number 
* **Item Variant** 
*   Code
*   Description
*   Description 2	
* **Item Reference**
*   Reference No.
*   Description
*   Description 2	
* **Item Attributes**
*   Name
*   Value	
* **Item Category**
*   Code
*   Description
*   Parent Category - 1 Level	
* **Item Translation**
*   Language
*   Description
*   Description 2	
* **Item Identifier**
*   Code	
* **Extended text Line**
*   Text
  
### Finding documents by reference.
Currently Sales lines suggestion can be launched for following sales documents: Sales Order, Sales Invoice, Sales Quote. 

Finding documents be reference searches Sales Order, Sales Quote, Sales Invoice, Posted Sales Invoice, Posted Sales Shipment; it uses fields **Document No.**, **External Document No.**, **Your Reference**, **Quote No.**, **Document Date**, **Sell-to Cusotmer No.**.

Finding document doesn't perform product search and returns all lines of type Item from the found document. Only items numbers, variant code and quantities are transfered. Quantities from the source document will be converted to the **Sales Unit of Measure**.

## In which geographies and languages is Sales lines suggestions available? 

This capability is available to any environment country/region localization and in any user language with the exception of Canada. Due to limited language support, the system will not be available initially to Canadian customers due to regulatory language compliance. For customer environments located in countries/regions where Azure OpenAI Service isn't deployed, administrators must first consent to allowing movement of data across boundaries for [!INCLUDE [prod_short](includes/prod_short.md)] to connect to Azure OpenAI service and for this capability to be available.  

## What operational factors and settings allow for effective and responsible use of the feature?

AI-powered suggestions might sometimes be incorrect or incomplete. Users of the **Sales lines suggestions** must review the accuracy of suggestions provided by Copilot before choosing to keep them. Copilot’s and suggestions aren't saved to the [!INCLUDE [prod_short](includes/prod_short.md)] database until you choose the **Keep it** button and exiting the Copilot window. You can also edit and correct any suggestions before choosing to keep it. You can also edit and correct any suggestions after they were inserted in the sales document.

### What is expected of administrators and end-users when using Sales lines suggestions?

Each individual users chooses whether or not to use the **Sales lines suggestions**. Even when the **Sales lines suggestions** is enabled by administrators and available, the accountant can still choose to use it always, sometimes or never.  

Administrators make the overall decisions to use or not use Copilot capabilities in [!INCLUDE [prod_short](includes/prod_short.md)] across lines of business. If administrators enable Copilot, they should ensure the appropriate users have been granted access to this capability.   

> [NOTE!]
> - We do not support the feature being used in [!INCLUDE [prod_short](includes/prod_short.md)] deployed to on premises or private cloud.
> - Partner extensibility is not supported. That means partner developers will not be able to modify, replace or extend this functionality in [!INCLUDE [prod_short](includes/prod_short.md)].

## Is Copilot the only means to create sales lines?  

No – use of Copilot is optional. [!INCLUDE [prod_short](includes/prod_short.md)] offers traditional, non-AI-powered means of inserting sales lines or copying documents in [!INCLUDE [prod_short](includes/prod_short.md)]. Both the traditional approach and Copilot can be used simultaneously within an organization.  

## How do I give feedback about AI-generated content?  

Each time Copilot provides suggestions, you can provide feedback to Microsoft directly from the Copilot window, using the like and dislike controls. Your feedback remains anonymous and we use this data to improve the quality of the service.  

## See also

[Suggest lines on sales orders with Copilot](sales-suggest-sales-lines-with-copilot.md)  
[Configure Copilot and AI capabilities](enable-ai.md)  
[Responsible AI FAQs for Dynamics 365 Business Central](responsible-ai-overview.md)  
