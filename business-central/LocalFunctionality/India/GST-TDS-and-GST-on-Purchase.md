---
    title: Calculation of Income Tax TDS and GST on Purchase Transactions 
    description: Calculation of Income Tax TDS and GST on Purchase Transactions

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
# Calculation of Income Tax TDS and GST on Purchase Transactions

## Calculation of Income Tax TDS and GST on Purchase Transactions

### Create a Purchase Invoice

1. Choose the ![img](image/search.jpg)icon, enter **Purchase Invoice**, and then choose the related link.
2. Select **Vendor** on **Invoice Header**.
3. Select **G/L Account** for Service purchase on **Purchase Invoice** line. GST Group Code, HSN/SAC Code should not be blank and GST Credit value should be selected as **Availment** if the tax input credit is available or else **Non-Availment** on the Item or G/L Account. For example, there is a purchase invoice for INR 10,000 and 18% GST (i.e. 9% CGST and 9% SGST/UTGST in case of Intra-State or Intra-Union Territory transaction or 18% IGST in case of Inter-State transaction) has to be charged and Income Tax TDS @10% also to be charged.

6. GST calculation will appear in the Fact Box, as following :

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**Transaction Value**|10000|
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|
    |**IGST**|1800|
    |**TDS**|1000|

6. GL Entries for Income Tax TDS and GST in Intra-State purchase transactions, will be as following:
    
    |Particular|Amount|
    |----------------------------------|---------------------------------------|  
    |**Service Account**|10000|  
    |**SGST/UTGST Receivable Account**|900|  
    |**CGST Receivable Account**|900|
    |**TDS Payable Account**|-1000|
    |**Vendor Account**|-10800|

7. GL Entries for Income Tax TDS and GST in Intra-State or Intra-Union Territory purchase transactions (reverse charge) will be as following:
    
    |Particular|Amount|
    |----------------------------------|---------------------------------------|  
    |**Service Account**|10000|  
    |**SGST/UTGST Receivable Account (Interim)**|900|  
    |**CGST Receivable Account (Interim)**|900|
    |**TDS Payable Account**|-1000|
    |**Vendor Account**|-9000|
    |**SGST/UTGST/UTGST Payable (Interim) A/C**|-900|
    |**CGST Payable (Interim) A/C**|-900|

8. GL Entries for Income Tax TDS and GST in Inter-State purchase transactions, will be as following:
   
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Service Account**|10000|
    |**IGST Receivable Account**|1800|
    |**TDS Payable Account**|-1000|
    |**Vendor Account**|-10800|

9. GL Entries for Income Tax TDS and GST in Inter-State purchase transactions (reverse charge), will be as following:
    
    |Particular|Amount|
    |----------------------------------|---------------------------------------|  
    |**Service Account**|10000|
    |**IGST Receivable Account (Interim)**|1800|
    |**TDS Payable Account**|-1000|
    |**Vendor Account**|-9000|
    |**IGST Payable (Interim) A/C**|-1800|






































