---
    title: Purchase of Goods from SEZ Vendor
    description: Purchase of Goods from SEZ Vendor

    author: v-debapd

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: India, local, IN, English
    ms.date: 06/15/2020
    ms.author: v-debapd

---
# Purchase of Goods from SEZ Vendor

## Create a Purchase Invoice

1. Choose the ![img](image/search.jpg)icon, enter **Purchase Invoice**, and then choose the related link.
2. Select **Vendor** in invoice header, GST vendor type should be **SEZ**.
3. Select **Item Code**for goods , **Fixed Asset** for Fixed Asset purchase in invoice line. GST Group Code, HSN/SAC Code should be filled up on Item.
4. IGST is to be calculated on GST Assessable Value + Basic Custom Duty. For example: Purchase Invoice will be issued for INR 10000, Custom Duty INR 1000, GST Assessable Value INR 11000 (IGST @18%), will be charged. Calculation base: (18% on 11,000 GST Assessable Value + 1,000 BCD) (12,000*18%)

5. GST Calculation will appear in the Fact Box, as following:
    
    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|11,000|
    |**Custom Duty (BCD)**|1000|  
    |**IGST**|2160|  


6. GL Entries for import of goods with input tax credit available from SEZ vendor with cover of Bill of Entry, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase Account (Transactional Value+ BCD)**|11000|  
    |**IGST Receivable Account (on GST Assessable Value + BCD)**|2160| 
    |**Customs House Account (GST Amount + BCD)**|-3160|
    |**Vendor Account (Transaction Value)**|-10000|

7. GL Entries for import of goods with input tax credit available from SEZ vendor without cover of Bill of Entry, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase Account (Transactional Value+ BCD)**|11000|  
    |**IGST Receivable Account (on GST Assessable Value + BCD)**|2160| 
    |**Vendor Account (Transaction Value)**|-13160|

8. GL Entries for import of goods without input tax credit available from SEZ vendor with cover of Bill of Entry, will be as following:

    |Particular|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase Account**|13160|  
    |**Custom House Account**|3160| 
    |**Vendor Account (Transaction Value)**|-10000|

9. GL Entries for import of goods without input tax credit available from SEZ vendor without cover of Bill of Entry, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase Account**|13160|  
    |**Vendor Account (Transaction Value)**|-13160|


10. GL Entries for import of fixed asset with input tax credit available from SEZ vendor with cover of Bill of Entry, will be as following:

    |Particular|Amount|
    |----------------------------------|---------------------------------------|  
    |**Fixed Asset Increased During the Year Account (Transactional Value+ BCD)**|11000|  
    |**IGST Receivable Account (on GST Assessable Value + BCD)**|2160| 
    |**Customs House Account (GST Amount + BCD)**|-3160|
    |**Vendor Account (Transaction Value)**|-10000|

11. GL Entries for import of fixed assets with input tax credit available from SEZ vendor without cover of Bill of Entry, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Fixed Asset Increased During the Year Account  (Transactional Value+ BCD)**|11000|  
    |**IGST Receivable Account (on GST Assessable Value + BCD)**|2160| 
    |**Vendor Account (Transaction Value)**|-13160|

12. GL Entries for import of fixed asset without input tax credit available from SEZ vendor with cover of Bill of Entry, will be as following:

    |Particular|Amount|
    |----------------------------------|---------------------------------------|  
    |**Fixed Asset Increased During the Year Account**|13160|  
    |**Custom House Account**|3160| 
    |**Vendor Account (Transaction Value)**|-10000|

13. GL Entries for import of fixed asset without input tax credit available from SEZ vendor without cover of Bill of Entry, will be as following:

    |Particular|Amount|
    |----------------------------------|---------------------------------------|  
    |**Fixed Asset Increased During the Year Account**|13160|  
    |**Vendor Account (Transaction Value)**|-13160|

> [!NOTE]
> The GST calculation process for SEZ vendor is same as Import vendor.

> [!NOTE]
>
> All GST attributes to be stored along with the transaction for GST Settlement and generating GST returns for government authorities.





































