---
title: Sale of Services to Overseas Place of Supply to registered customer
description: Sale of Services to Overseas Place of Supply to registered customer

author: v-debapd

    
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf


ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Sale of Services to Overseas Place of Supply to Registered Customer


GST is destination based tax i.e consumption tax, which means tax will be levied where goods and services are consumed and will accrue to that state.  The supply of goods or services or both when the supplier is located in India and the place of supply is outside India shall be treated to be a supply of goods or services or both in the course of inter-state trade or commerce.

Process of sale to a registered customer with overseas place of supply  has been explained in this document.

## Create a sales invoice

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Sales Invoice**, and then choose the related link.

2. Select **Customer** on **Sales Invoice** header, GST customer type should be **Registered**.

3. Select **G/L Account** on **Sales Invoice** line. GST Group Code, HSN/SAC Code should not be blank on the G/L Account Card.

4. **POS Out of India** field on **Sales Invoice** header should be marked as True. 

For example, there is a sales invoice for INR 10,000 and 18% IGST has to be charged on the invoice amount.

- GST calculation will appear in the Fact Box, as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**IGST**|1800|  
   

- GL Entries for Intra-State Sale of services to overseas place of supply to registered customer, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|11800|  
    |**IGST Payable Account**|- 1800|
    |**Services Account**|- 10000|


















## Related information 
[GST and TCS on Sales Transaction](GST-TCS-and-GST-on-Sales-Transaction.md)






















[!INCLUDE[footer-include](../../includes/footer-banner.md)]
