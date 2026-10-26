---
title: Sale of Services to Overseas Place of Supply to Registered Customer
description: Explains how to process sales of services to registered customers when the place of supply is overseas, under GST regulations in India.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, sale of services, overseas place of supply
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Sale of services to overseas place of supply to registered customer

GST is destination based tax, that is, consumption tax, which means tax is levied where goods and services are consumed and accrued to that state. The supply of goods or services or both when the supplier is located in India and the place of supply is outside India shall be treated to be a supply of goods or services or both in the course of inter-state trade or commerce.

Process of sale to a registered customer with overseas place of supply  has been explained in this document.

## Create a sales invoice

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Sales Invoices**, and then choose the related link.
1. Select **Customer** on **Sales Invoice** header, GST customer type should be **Registered**.
1. Select **G/L Account** on **Sales Invoice** line. GST Group Code, HSN/SAC Code shouldn't be blank on the G/L Account Card.
1. **POS Out of India** field on **Sales Invoice** header should be marked as True.

The document must be open and marked as a **GST Invoice**. The location state and the customer's place-of-supply state must match for this option. **GST Place Of Supply** on the lines can't be **Location Address**.

For example, there's a sales invoice for INR 10,000 and 18% IGST has to be charged on the invoice amount.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**IGST**|1800|  

- G/L entries for this sale of services with an overseas place of supply are as follows:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|11800|  
    |**IGST Payable Account**|- 1800|
    |**Services Account**|- 10000|

## Related information

[GST and TCS on Sales Transaction](GST-TCS-and-GST-on-Sales-Transaction.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
