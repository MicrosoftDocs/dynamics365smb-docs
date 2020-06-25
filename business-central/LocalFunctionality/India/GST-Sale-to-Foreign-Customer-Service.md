---
    title: Export of Goods and/or Services to Foreign Customer
    description: Export of Goods and Services to Foreign Customer

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
# Export of Goods and Services to Foreign Customer

## Create a Sales Invoice

1. Choose the ![img](image/search.jpg)icon, enter **Sales Invoice**, and then choose the related link.
2. Select **Customer** on **Sales Invoice** header, GST customer type should be **Export** or **Deemed Export** or **SEZ Development** or **SEZ Unit**.
3. Select **G/L Account** or **Item Code** on **Sales Invoice** line. GST Group Code, HSN/SAC Code should not be blank on the G/L Account or Item Card. For example, there is a sales invoice for INR 10,000 and 18% IGST has to be charged on the invoice amount.
5. GST calculation will appear in the Fact Box, as following:
    
    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**IGST**|1800|  
    
6. GL Entries for export of goods and/or services with payment of duty to Foreign Customer, SEZ Unit, SEZ Development Customer will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|10,000|  
    |**IGST Refund Account**|1800|
    |**IGST Payable Account**|-1800|
    |**Sales Account**|-10000|

7. GL Entries for export of goods and/or services without payment of duty to Foreign Customer, SEZ Unit, SEZ Development Customer will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|10,000|  
    |**Sales Account**|-10000|


> [!NOTE]
> Export or Deemed export will have same treatment, as it is treated as interstate transaction and only IGST is applicable irrespective of location of receiver. There is no scenario of deemed export without payment of Duty, as company has to pay IGST and claim refund. Refund can be claimed either by seller or recipient.

> [!NOTE]
>
> Relevant GST attributes are stored along with the GST transactions for GST Settlement and generating GST returns for government authorities.





































