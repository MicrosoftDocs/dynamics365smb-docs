---
title: GST TCS on Vendor Payment
description: GST TCS on Vendor Payment

author: v-debapd

    
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# GST TCS on Vendor Payment


GST TCS can be applicable for Registered Vendor. On posting of GST TCS transaction against Vendor, system updates 'Liable to Pay' field in GST TDS/TCS Entry table as 'TRUE'. The GST TCS entries that have 'Liable to Pay' field 'TRUE' will be shown on settlement page. The GST TCS Liability can only be paid through Cash or Bank. It cannot be set off against any available credit.

For example, INR 1000 paid to the vendor and 1% GST TCS (0.50% CGST, 0.50% SGST for Intra-State or Intra-Union Territory and 1% IGST for Inter State) has to be calculated on payment amount.

1. GST calculation will appear in the Fact Box on Bank or Cash Payment Voucher, as following:
    
    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**Payment Amount**|1000|
    |**GST Transactional Value**|1,000|
    |**CGST Amount**|5|
    |**SGST Amount**|5|
    |**IGST Amount**|10|

## GST TCS on vendor payment entry process
 
1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Bank Payment Voucher** or **Cash Payment Voucher**, and then choose the related link.
2. Fill in the fields as described on **Bank Payment Voucher** or **Cash Payment Voucher**.
    
    |Field|Description| 
    |---------------------------------|  ---------------------------------------| 
    |**Posting Date**|Specify the posting date of the document.|
    |**Document Type**|Specify as 'Payment'|
    |**Account Type**|Specify as 'Vendor'|
    |**Account No.**|Select the relevant vendor code.|
    |**Amount**|Specify the amount.|
    |**Bal. Account Type**|Specify G/L Account or Bank Account.|
    |**Location Code**|Specify the relevant location code.|
    |**GST TCS State Code**|Specify the relevant state code.|
    |**GST TDS/TCS Base Amount**|Specify the GST TCS calculation base amount.|
    |**GST TCS**|Mark this field as True.|

    
3. GL Entries for GST TCS - Intrastate Transaction, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Vendor Account**|1000|  
    |**CGST TCS Payable Account**|-5|  
    |**SGST/UTGST TCS Payable Account**|-5| 
    |**Bank Account**|-990| 
    
3. GL Entries for GST TCS - Interstate Transaction, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Vendor Account**|1000|  
    |**IGST TCS Payable Account**|-10|  
    |**Bank Account**|-990| 


## Related information 
[GST TDS TCS on Receipt](GST-TDS-TCS-on-Receipt.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
