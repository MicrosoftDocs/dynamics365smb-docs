---
    title: Sale of Services to Overseas Place of Supply to registered customer
    description: Sale of Services to Overseas Place of Supply to registered customer

    author: v-debapd

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: India, local, IN, English
    ms.date: 06/24/2020
    ms.author: v-debapd


---
# Sale of Services to Overseas Place of Supply to registered customer

## Create a Sales Invoice

1. Choose the ![img](image/search.jpg)icon, enter **Sales Invoice**, and then choose the related link.

2. Select **Customer** on **Sales Invoice** header, GST customer type should be **Registered**.

3. Select **G/L Account** on **Sales Invoice** line. GST Group Code, HSN/SAC Code should not be blank on the G/L Account Card.

4. **POS Out of India** field on **Sales Invoice** header should be marked as True. For example, there is a sales invoice for INR 10,000 and 18% IGST has to be charged on the invoice amount.

6. GST calculation will appear in the Fact Box, as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**IGST**|1800|  
   

6. GL Entries for Intra-State Sale of services to overseas place of supply to registered customer, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|11800|  
    |**IGST Payable Account**|- 1800|
    |**Services Account**|- 10000|

> [!NOTE]
>
> Relevant GST attributes are stored along with the GST transactions for GST Settlement and generating GST returns for government authorities.





































