---
    title: Purchase of Goods from an Unregistered Vendor (Reverse Charge)
    description: Purchase of Goods from an Unregistered Vendor (Reverse Charge)

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
# Purchase of Goods from an Unregistered Vendor (Reverse Charge)

## Create a Purchase Invoice


1. Choose the ![img](image/search.jpg)icon, enter **Purchase Invoice**, and then choose the related link. 
2. Select Vendor in invoice header, GST vendor type should be **Unregistered**.
3. Select **Item Code** for goods, **G/L Account** for Service purchase, **Fixed Asset** for Fixed Asset purchase and **Charge (Item)** for Item Charge in invoice line. GST Group Code, HSN/SAC Code and GST Credit value should be selected as **Availment** if the tax input credit is available or else **Non-Availment** on the Item or G/L Account. For example, invoice will be issued for INR 10,000 on which 18% GST (9% CGST and 9% SGST/UTGST in case of Intra-State/Intra-Union Territory transaction or 18% IGST in case of Inter-State transaction), will be charged.
5. GST Credit option can be changed in invoice line.
6. GST Calculation will appear in the Fact Box, as following:
    
    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|
    |**IGST**|1800|

7. GL Entries for Intra-State purchase of goods and services from an unregistered vendor where input tax credit is available (reverse charge), will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Service Account**|10000|  
    |**SGST/UTGST Receivable (Interim) Account**|900|
    |**CGST Receivable (Interim) Account**|900|
    |**SGST/UTGST Payable (Interim) Account**|-900|
    |**CGST Payable (Interim) Account**|-900|
    |**Vendor Account**|-10000|

8. GL Entries for Intra-State purchase of goods and services from an unregistered vendor where input tax credit is not available (reverse charge), will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase/Services Account**|11800|  
    |**SGST/UTGST Payable Account**|-900|
    |**CGST Payable Account**|-900|
    |**Vendor Account**|-10000|

9. GL Entries for purchase of goods and services from an unregistered vendor with reverse charge exempt, will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase/Services Account**|10000|  
    |**Vendor Account**|-10000|

10. GL Entries for Intra-State purchase of fixed asset from an unregistered vendor where input tax credit is available (reverse charge), will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Fixed Asset Increases during the Year**|10000|
    |**SGST Receivable Account (Interim)**|900|
    |**CGST Receivable Account (Interim)**|900|
    |**SGST Payable Account (Interim)**|-900|
    |**CGST Payable Account (Interim)**|-900|
    |**Vendor**|10000|

11. GL Entries for Intra-State purchase of fixed asset from an unregistered vendor where input tax credit is not available (reverse charge), will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Fixed Asset Increases during the Year**|11800|
    |**SGST Payable Account (Interim)**|-900|
    |**CGST Payable Account (Interim)**|-900|
    |**Vendor**|10000|

12. GL Entries for Item Charge in case of Intra-State purchase of fixed asset from an unregistered vendor where input tax credit is available (reverse charge), will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------| 
    |**Purchase Account**|10000|
    |**SGST Receivable Account (Interim)**|900|
    |**CGST Receivable Account (Interim)**|900|
    |**SGST Payable Account (Interim)**|-900|
    |**CGST Payable Account (Interim)**|-900|
    |**Vendor**|10000|

13. GL Entries for Item Charge in case of Intra-State purchase of fixed asset from an unregistered vendor where input tax credit is not available (reverse charge),will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------| 
    |**Purchase Account**|10000|
    |**SGST Payable Account (Interim)**|-900|
    |**CGST Payable Account (Interim)**|-900|
    |**Vendor**|10000|


> [!NOTE]
>
> All GST attributes to be stored along with the transaction for GST Settlement and generating GST returns for government authorities.





































