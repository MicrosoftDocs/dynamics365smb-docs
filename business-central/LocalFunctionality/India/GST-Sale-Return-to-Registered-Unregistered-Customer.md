---
    title: Sales Return of Goods from Registered or Unregistered Customer
    description: Sales Return of Goods from Registered or Unregistered Customer

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
# Sales Return of Goods from Registered or Unregistered Customer

## Create a Sales Return Order or Credit Memo

1. Choose the ![img](image/search.jpg)icon, enter **Sales Return Order** or **Sales Credit Memo**, and then choose the related link. 
2. Select **Customer** on **Sales Return Order** or **Sales Credit Memo** header, GST customer type should be **Registered** or **Unregistered**.
3. Select **Item Code** for goods or **G/L Account** for Service Sale on **Sales Return Order** or **Sales Credit Memo** line. GST Group Code, HSN/SAC Code should not be blank on Item or G/L Account. For example, there is a sales credit memo for INR 10,000 and 18% GST (i.e. 9% CGST and 9% SGST/UTGST in case of Intra-State or Intra-Union Territory transaction or 18% IGST in case of Inter-State transaction) has to be charged on the credit memo amount.
4. GST calculation will appear in the Fact Box, as following:
    
    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900| 

5. GL Entries for Intra-State Sales Return of Goods from Registered or Unregistered Customer, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Sales Account**|10,000|  
    |**SGST/UTGST Payable Account**|900|  
    |**CGST Payable Account**|900|
    |**Customer Account**|-11800|

6. GL Entries for Inter-State Sales Return of Goods from Registered or Unregistered Customer, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Sales Account**|10,000|  
    |**IGST Payable Account**|1800| 
    |**Customer Account**|- 11800|

7. GL Entries for Intra-State Sales Return of Services from Registered or Unregistered Customer, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Service Account**|10,000|  
    |**SGST/UTGST Payable Account**|900|  
    |**CGST Payable Account**|900|
    |**Customer Account**|-11800|

9. GL Entries for Inter-State Sales Return of Services from Registered or Unregistered Customer, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Services Account**|10,000|  
    |**IGST Payable Account**|1800|
    |**Customer Account**|- 11800|







































