---
    title: Sales to Registered or Unregistered Customer
    description: Sales to Registered or Unregistered Customer

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
# Sales to Registered or Unregistered Customer

## Create a Sales Invoice


1. Choose the ![img](image/search.jpg)icon, enter **Sales Invoice**, and then choose the related link.

2. Select **Customer** on **Sales Invoice** header, GST customer type should be **Registered** or **Unregistered**.

3. Select **Item Code** for goods or **G/L Account** for service sales on **Sales Invoice** line. GST Group Code, HSN/SAC Code should not be blank on the item or G/L account. For example, there is a sales invoice for INR 10,000 and 18% GST (i.e. 9% CGST and 9% SGST/UTGST in case of Intra-State/Intra-Union Territory transaction or 18% IGST in case of Inter-State transaction) has to be charged on the invoice amount.

6. GST calculation will appear in the Fact Box, as following:
    
    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|
    |**IGST**|1800|

6. GL Entries for Intra-State/Intra-Union Territory sale of goods to registered or unregistered customer, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|11,800|  
    |**SGST/UTGST/Payable Account**|- 900|  
    |**CGST Payable Account**|- 900|
    |**Sales Account**|- 10000|

7. GL Entries for Inter-State sale of goods to registered or unregistered customer, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|11,800|  
    |**IGST Payable Account**|- 1800| 
    |**Sales Account**|- 10000|

8. GL Entries for Intra-State/Intra-Union Territory sale of services to registered or unregistered customer, will be as following:

    |Particular|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|11,800|  
    |**SGST/UTGST/Payable Account**|- 900|  
    |**CGST Payable Account**|- 900|
    |**Sales Account**|- 10000|

9. GL Entries for Inter-State sale of services to registered or unregistered customer, will be as following :

    |Particular|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|11,800|  
    |**IGST Payable Account**|- 1800|
    |**Services Account**|- 10000|

> [!TIP]
> System will automatically update 'Nature of Supply' for Registered customer as B2B and for Unregistered customer as B2C.

> [!NOTE]
>
> Relevant GST attributes are stored along with the GST transactions for GST Settlement and generating GST returns for government authorities.





































