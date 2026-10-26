---
title: Sales Returns from Registered Customers for Goods with an Overseas Place of Supply
description: Process for handling sales returns or issuing credit notes for services supplied overseas to registered customers in India.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, sales returns, registered customers, overseas place of supply
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Sales returns from registered customers for goods with an overseas place of supply

GST is destination based tax, that is, consumption tax, which means tax is levied where goods and services are consumed and accrue to that state. The supply of goods or services or both when the supplier is located in India and the place of supply is outside India shall be treated as a supply of goods or services or both in the course of inter-state trade or commerce.

A customer can require to return the goods or issue credit note due to various reasons like damaged goods, quality issues etc.

The following procedure illustrates a credit for services to a registered customer with an overseas place of supply.

## Create a sales return order or credit memo

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Sales Return Orders** or **Sales Credit Memos**, and then choose the related link.
1. Select **Customer** on **Sales Return Order** or **Sales Credit Memo** header, GST customer type should be **Registered**.
1. Select **G/L Account** on **Sales Return Order** or **Sales Credit Memo** line. **GST Group Code**, **HSN/SAC Code** shouldn't be blank on the **G/L Account**.
1. **POS Out of India** field on **Sales Return Order** or **Sales Credit Memo** header should be marked as True.

The document must be open and marked as a **GST Invoice**. The location state and the customer's place-of-supply state must match. **GST Place Of Supply** on the lines can't be **Location Address**.

For example, there's a sales credit memo for INR 10,000 and 18% IGST has to be charged on the credit memo amount.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**IGST**|1800|  
  
- G/L entries for the credit note for services with an overseas place of supply are as follows:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Service Account**|10000|  
    |**IGST Payable Account**|1800|
    |**Customer Account**|-11800|

## Related information

[Sale Return from Registered and Unregistered Customer](GST-Sale-Return-to-Registered-Unregistered-Customer.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
