---
title: Import from Foreign Vendor
description: Import from Foreign Vendor

author: v-debapd

    
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Import from Foreign Vendor


Purchasing goods in India from a place outside India is import of goods. For services, if the supplier is located outside India, the recipient is located in India and the place of supply is in India, then it is called Import of services. Purchase of goods and/or services from a foreign vendor is subject to reverse charge i.e. the person importing goods or services has to remit tax to the government. 

Process for purchase from a foreign vendor has been explained in this document.

## Create a purchase invoice

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Purchase Invoice**, and then choose the related link.
2. Select **Vendor** on **Purchase Invoice** header, GST vendor type should be **Import**.
3. Select **Item Code** for goods, **G/L Account** for Service purchase and **Fixed Asset** for Fixed Asset purchase on **Purchase Invoice** line. GST Group Code, HSN/SAC Code and GST Credit value should be selected as **Availment** if the tax input credit is available or else **Non-Availment** on the Item or G/L Account.
4. GST Credit option can be changed in document line.

- In case of import of goods from foreign vendor, IGST is to be calculated on GST Assessable Value + Basic Custom Duty. 

For example, purchase invoice is issued INR 10000, Custom Duty is INR 1000. Therefore, on GST Assessable Value INR 11000,(IGST @18%) has to be charged. Calculation base: (18% on 11,000 GST Assessable Value + 1,000 BCD) (12,000*18%).

  - GST calculation will appear in the Fact Box, as following:
    
      |Component|Amount|
      |----------------------------------|---------------------------------------|  
      |**Transaction Value**|10000|
      |**GST Base Amount**|11,000|
      |**Custom Duty (BCD)**|1000|  
      |**IGST**|2160 (18% on 11,000 GST Assessable Value + 1,000 BCD) (12,000*18%)|  


  - GL Entries for import of goods from foreign vendor where input tax credit is available, will be as following:
    
      |Particulars|Amount|
      |----------------------------------|---------------------------------------|  
      |**Purchase Account (Transactional Value+ BCD)**|11000|  
      |**IGST Receivable Account (GST on GST Assessable Value + BCD)**|2160| 
      |**Customs House Account (GST Amount + BCD)**|-3160|
      |**Vendor Account (Transaction Value)**|-10000|

  - GL Entries for import of goods from foreign vendor where input tax credit is not available, will be as following:
    
      |Particulars|Amount|
      |----------------------------------|---------------------------------------|  
      |**Purchase Account (Transactional Value+ BCD + IGST Amount)**|13160|  
      |**Customs House Account (GST Amount + BCD)**|-3160|
      |**Vendor Account (Transaction Value)**|-10000|


- Import of Fixed Asset from foreign vendor, IGST is to be calculated on GST Assessable Value + Basic Custom Duty. 

For example, purchase invoice is issued for INR 10000, Custom Duty INR 1000, GST Assessable Value INR 11000,(IGST @18%) has to be charged. Calculation base: (18% on 11,000 GST Assessable Value + 1,000 BCD) (12,000*18%).

  - GST Calculation will appear in the Fact Box, as following:
    
      |Component|Amount|
      |----------------------------------|---------------------------------------|  
      |**Transaction Value**|10000|
      |**GST Base Amount**|11,000|
      |**Custom Duty (BCD)**|1000|  
      |**IGST**|2160 (18% on 11,000 GST Assessable Value + 1,000 BCD) (12,000*18%)|  

  - GL Entries for import of goods from foreign vendor where input tax credit is available, will be as following:
    
      |Particulars|Amount|
      |----------------------------------|---------------------------------------|  
      |**Fixed Asset Increase During the Year Account (Transactional Value+ BCD)**|11000|  
      |**IGST Receivable Account (GST on GST Assessable Value + BCD)**|2160| 
      |**Customs House Account (GST Amount + BCD)**|-3160|
      |**Vendor Account (Transaction Value)**|-10000|

  - GL Entries for import of goods from foreign vendor where input tax credit is not available, will be as following:
    
     |Particulars|Amount|
     |----------------------------------|---------------------------------------|  
     |**Fixed Asset Increase During the Year Account (Transactional Value+ BCD + IGST Amount)**|13160|  
     |**Customs House Account (GST Amount + BCD)**|-3160|
     |**Vendor Account (Transaction Value)**|-10000|


- Import of services from foreign vendor. 

For example, purchase invoice is issued for INR 10000, (IGST @18%) has to be charged.

  - GST Calculation will appear in the Fact Box, as following:
    
     |Component|Amount|
     |----------------------------------|---------------------------------------|  
     |**GST Base Amount**|10000|
     |**IGST**|1800|  

  - GL Entries for import of services from foreign vendor where input tax credit is available, will be as following:
    
     |Particulars|Amount|
     |----------------------------------|---------------------------------------|  
     |**Services Account**|10000|  
     |**IGST Receivable (Interim) Account**|1800|
     |**IGST Payable (Interim) Account**|-1800|
     |**Vendor Account (Transaction Value)**|-10000|

  - GL Entries for import of services from foreign vendor where input tax credit is not available, will be as following:
    
      |Particulars|Amount|
      |----------------------------------|---------------------------------------|  
      |**Services Account**|11800|  
      |**IGST Payable (Interim) Account**|-1800|
      |**Vendor Account**|-10000|


- Import of Services from Import Associate Vendor. 

For example, purchase invoice is issued for INR 10000, (IGST @18%) has to be charged.

  - GST Calculation will appear in the Fact Box, as following:
    
      |Component|Amount|
      |----------------------------------|---------------------------------------|  
      |**GST Base Amount**|10000|
      |**IGST**|1800|

  - GL Entries for import of services from import associate vendor where input tax credit is available,will be as following:
    
      |Particular|Amount|
      |----------------------------------|---------------------------------------|  
      |**Services Account**|10000|  
      |**IGST Receivable Account**|1800|
      |**IGST Payable Account**|-1800|
      |**Vendor Account**|-10000|

  - GL Entries for import of services from import associate vendor where input tax credit is not available, will be as following :
    
      |Particular|Amount|
      |----------------------------------|---------------------------------------|  
      |**Services Account**|11800|  
      |**IGST Payable Account**|-1800|
      |**Vendor Account**|-10000|

> [!NOTE]
>
> Import Transaction should be in Foreign Currency.




## Related information 
[Purchase from Vendor with Overseas Place of Supply](GST-Service-Purchase-for-Overseas-Place-of-supply-Registered-Vendor.md)







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
