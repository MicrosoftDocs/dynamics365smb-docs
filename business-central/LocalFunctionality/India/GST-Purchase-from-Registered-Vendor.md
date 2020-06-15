---
    title: Purchase from Registered Vendors
    description: Purchase from Registered Vendors

    
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
# Purchase from Registered Vendors

## Create a Purchase Invoice

1. Choose the ![img](image/search.jpg)icon, enter **Purchase Invoice**, and then choose the related link. 
2. Select **Vendor** in invoice header, GST vendor type should be **Registered**.
3. Select **Item Code** for goods, **G/L Account** for Service purchase, **Fixed Asset** for Fixed Asset purchase and **Charge (Item)** for Item Charge in invoice line. GST Group Code, HSN/SAC Code and GST Credit value should be selected as **Availment** if the tax input credit is available or else **Non-Availment** in the Item or G/L Account.
For example, invoice will be issued for INR 10,000 on which 18% GST (9% CGST and 9% SGST/UTGST in case of Intra-State/Intra-Union Territory transaction or 18% IGST in case of Inter-State transaction),will be charged.
5. GST Credit option can be changed in invoice line.
6. GST Calculation will appear in the Fact Box, as following:
    
    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|
    |**IGST**|1800|

7. G/L Entries for Intra-State/Intra-Union Territory purchase of goods from registered vendor where input tax credit is available, will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase Account**|10,000|  
    |**SGST/UTGST/Receivable Account**|900|  
    |**CGST Receivable Account**|900|
    |**Vendor Account**|-11800|

8. G/L Entries for Intra-State/Intra-Union Territory purchase of goods from registered vendor where input tax credit is not available, will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase Account**|11,800|  
    |**Vendor Account**|-11800|

9. G/L Entries for Intra-State/Intra-Union Territory purchase of services from registered vendor where input tax credit is available, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Services Account**|10,000|  
    |**SGST/UTGST/Receivable Account**|900|  
    |**CGST Receivable Account**|900| 
    |**Vendor Account**|-11800|

10. G/L Entries for Intra-State/Intra-Union Territory purchase of services from registered vendor where input tax credit is not available, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Services Account**|11,800|  
    |**Vendor Account**|-11800|

11. G/L Entries for Inter-State purchase of goods from registered vendor where input tax credit is available, will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase Account**|10,000|  
    |**IGST Receivable Account**|1800| 
    |**Vendor Account**|-11800|

12. G/L Entries for Inter-State purchase of goods from registered vendor where input tax credit is not available, will be as following:
    
    |Particular|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase Account**|11800|  
    |**Vendor Account**|-11800|

13. G/L Entries for Inter-State purchase of services from registered vendor where input tax credit is available, will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Services Account**|10,000|  
    |**IGST Receivable Account**|1800|
    |**Vendor Account**|-11800|

14. G/L Entries for Inter-State purchase of services from registered vendor where input tax credit is not available, will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Services Account**|11800|  
    |**Vendor Account**|-11800|

15. G/L Entries for the Intra-State purchase from registered vendor (reverse charge), will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase/Services Account**|10000|  
    |**CGST Receivable Account (Interim)**|900|
    |**SGST Receivable Account (Interim)**|900|
    |**CGST Payable Account (Interim)**|-900|
    |**SGST Payable Account (Interim)**|-900|
    |**Vendor Account**|-10000|

16. G/L Entries for the Inter-State purchase from registered vendor (reverse charge) if time of supply is considered on the basis of payment, will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase/Services Account**|10000|  
    |**IGST Receivable Account (Interim)**|1800|
    |**IGST Payable Account (Interim)**|-1800|
    |**Vendor Account**|-10000|

17. G/L Entries on payment to registered vendor (reverse charge) against Intra-State purchase invoice, will be following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Vendor Account**|10000|
    |**CGST Payable Account (Interim)**|900|
    |**SGST Payable Account (Interim)**|900|
    |**CGST Payable Account**|-900|
    |**SGST Payable Account**|-900|
    |**Bank Account**|-10000|  

18. G/L Entries on payment to registered vendor (reverse charge) against Inter-State purchase invoice, will be following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Vendor Account**|10000|
    |**IGST Payable Account (Interim)**|1800|
    |**IGST Payable Account**|-1800|
    |**Bank Account**|-10000|


19. G/L Entries for Intra-State/Intra-Union Territory purchase of fixed asset from registered vendor where input tax credit is available, will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Fixed Asset Increases during the Year**|10000|
    |**SGST Receivable Account**|900|
    |**CGST Receivable Account**|900|
    |**Vendor Account**|-11800|

20. G/L Entries for Intra-State/Intra-Union Territory purchase of fixed asset from registered vendor where input tax credit is not available, will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Fixed Asset Increases during the Year**|11800|
    |**Vendor Account**|-11800|

> [!TIP]
> In case of Inter-State purchase, IGST will be calculated.

21. G/L Entries for Charge Item in case of Intra-State/Intra-Union Territory in purchase transaction from registered vendor where input tax credit is available, will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Purchase Account**|10000|
    |**SGST Receivable Account**|900|
    |**CGST Receivable Account**|900|
    |**Vendor Account**|-11800|

22. G/L Entries for Charge Item in case of Intra-State/Intra-Union Territory in purchase transaction from registered vendor where input tax credit is not available, will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Purchase Account**|11800|
    |**Vendor Account**|-11800|

> [!TIP]
> In case of Inter-State purchase, IGST will be calculated.

> [!NOTE]
>
> All GST attributes to be stored along with the transaction for GST Settlement and generating GST returns for government authorities.





































