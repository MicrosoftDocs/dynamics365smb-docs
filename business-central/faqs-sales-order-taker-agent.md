---
title: FAQ for sales order taker agent
description: This FAQ provides information about the AI technology used in Business Central, along with key considerations and details about how AI is used, how it was tested and evaluated, and any specific limitations.
ms.date: 07/03/2024
ms.custom: 
  - responsible-ai-faqs
ms.topic: article
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
---
# FAQ for sales order taker agent 

These frequently asked questions (FAQ) describe the AI impact of sales order taker agent feature in Business Central.

## What is the sales order taker agent?

The sales order taker agent is an integrated copilot that automates the task of taking sales orders. This agent handles the end-to-end sales order capturing process from taking the customer's order by e-mail, preparing the quote with requested items, checking the availability of the items, sending the quote to the customer for approval, and finally converting the quote to a sales order after receiving customer confirmation. 

## What are capabilities of the sales order taker agent?

The sales order taker agent offers various capabilities that help manage heavy, mundane, and repetitive workloads:

- **Process sales orders:** Receives item requests from customers via email, identifies customers in Business Central, drafts and sends sales quotes, and converts approved quotes into sales orders.
- **User directives:** Operates based on user directives, utilizing AI to complete necessary steps within the Business Central environment and seeking user intervention when specific situations arise.
- **Predefined permissions and roles:** Comes with predefined permissions and UI roles that can be assigned by the configuring user.
- **Configuration experience:** Users can define the list of delegators, channels for receiving orders (for example, email), and select which steps to include or exclude in the process.
- **External Orchestrator:** Invoked by an external orchestrator, Copilot Studio, which monitors the company mailbox and hands over emails to the agent.
- **Transparency and control:** Maintains full transparency and control over changes made by the agent, providing notifications, a task context and history view, and detailed review options.
- **Performance monitoring:** Offers an overview of the agent's KPIs, summarizing the impact of the agent's work.

## What is the intended use of the sales order taker agent?

- **Increase the speed of sales order data entry by finding product:** Intended to answer users' inquiries to find a product based on vague, incomplete, or inaccurate description.
- **Increase the speed of Sales Order data entry by Finding document by reference:** Intended to answer users' inquiries to find existing sales documents for a specific customer by using partial or approximate information.

## How was sales order taker agent evaluated? What metrics are used to measure performance?

[Provide evidence of system or feature accuracy and performance, and, when applicable, a description of the extent to which these results are generalizable across use cases that were not part of the evaluation.]

## What are the limitations of sales order taker agent? How can users minimize the impact of the sales order taker agent limitations when using the system?

- The system has been tested with item names and item descriptions that are both in English. Mixed language inputs may result in lesser-quality output, 
- as the system will still work based on pure string similarity, but semantic part of the matching may or may not work.

- Due to limited language support, the system will not be available initially to Canadian customers due to regulatory language compliance as both English and French languages as mandatory.

- Sales Lines Suggestions has following limitations regarding complete BC functionality:

  - It populates only lines of type “Item” (excluding lines of type Comment, G/L Account, Fixed Asset, Resource, Charges (Item). 
  - Works with two columns in sales line table: Item No and Quantity (out of ~100).  
    - Related fields like Unit of Measure,  Price, Discount, Location, Financial dimensions, Shipping date are populated based on master data defined in the Item or inherited from header of the document defined by user 
    - Variant Code is not currency supported. If product, like Bicycle can be shipped in “Red” or “Blue” color, system will find the item Bicycle using “Red bike”, but will leave Item Variant Code empty. 

- Supported sales documents:

  - Creation: Sales Order, Sales Invoice, Sales Quote 
  - Search: Sales Order, Sales Quote, Sales Invoice, Posted Sales Invoice, Posted Sales Shipment 

- The user input is limited to the number of tokens that can be processed in one request. There is no pagination. Users will be asked to adjust (reduce) input.

## What operational factors and settings allow for effective and responsible use of the feature?

[Describe the operational factors and ranges within which the system is expected to perform reliably and safely. List the choices that end users can make (e.g., customization, settings, etc.), with a description of how those choices may impact system behavior in the real world.]

## See also

- [Feature page]([Link])

[!INCLUDE[footer-include](../includes/footer-banner.md)]
