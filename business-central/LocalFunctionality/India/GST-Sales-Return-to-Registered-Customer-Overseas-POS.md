---
    title: Return or Credit Note of Services for Overseas Place of Supply to Registered Customer
    description: Return or Credit Note of Services for Overseas Place of Supply to Registered Customer

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
# Return or Credit Note of Services for Overseas Place of Supply to Registered Customer

## Create a Sales Return Order or Credit Memo

1. Choose the ![img](image/search.jpg)icon, enter **Sales Return Order** or **Sales Credit Memo**, and then choose the related link. 
2. Select **Customer** on **Sales Return Order** or **Sales Credit Memo** header, GST customer type should be **Registered**.
3. Select **G/L Account** on **Sales Return Order** or **Sales Credit Memo** line. GST Group Code, HSN/SAC Code should not be blank on the G/L Account.
4. **POS Out of India** field on **Sales Return Order** or **Sales Credit Memo** header should be marked as True. For example, there is a sales credit memo for INR 10,000 and 18% IGST has to be charged on the credit memo amount.
6. GST calculation will appear in the Fact Box, as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**IGST**|1800|  
  
6. GL Entries for Intra-State Return or Credit Note of services for overseas place of supply to registered customer, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Service Account**|10000|  
    |**IGST Payable Account**|1800|
    |**Customer Account**|-11800|






































