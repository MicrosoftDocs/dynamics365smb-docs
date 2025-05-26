---
title: GST Credit and GST Liability adjustment for open Reverse Charge Goods and Services Invoices
description: GST Credit and GST Liability adjustment for open Reverse Charge Services Invoices

author: v-debapd

    
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# GST Credit and GST Liability Adjustment for Open Reverse Charge Goods and Services Invoices


This topic explains the process of adjusting GST Credit and GST Liability for open reverse charge goods and services invoices.

- For reverse charge invoices of goods, GST Liability and Credit shall be generated immediately, or in next 30 days from date of issue of supplier invoice, if payment to supplier is not made against it.

- For reverse charge for service invoices, GST Liability and Credit shall be generated immediately, or 60 days from date of issue of supplier invoice, if payment to supplier is not made against it.

- User can generate GST liability and credit for open reverse charge service invoice through GST Liability Adjustment.

  1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **GST Liability Adjustment**, and then choose the related link.
  2. Select the following in the request page

      |Field Name|Description|
      |----------------------------------|---------------------------------------|  
      |**Adjustment Document No.**|System will generate number from number series assigned in Purchases & Payable Setup|
      |**GST Registration No.**|System will list only transactions posted with selected GST Registration No.|  
      |**Posting Date**|Adjustment posting date|  
      |**Liability Date Formula**|Enter 0D, 30D or 60D. For example, if 60D is mentioned, the system will reverse count 60 days from posting date for arriving Liability Filter Date|
      |**Liability Filter Date**|System will update automatically (Posting date – Liability Date Formula, Ex: 01-Jan-18- 60D= 02-Nov-17), System will consider all open Reverse Charge service invoices posted before date updated in this field. (Ex: 02-Nov-17)|
      |**Vendor No.**|System will list invoice from this vendor only|
     **Document No.**|System will verify only for this document|
      |**External Document No.**|System will verify only for this document|
      |**Nature of Adjustment**|User need to select the option, available options: Generate, Reverse|
    
For example, vendor issued invoice for INR 10000, in an Intra-State or Intra-Union Territory transaction, and GST 18% (9% CGST and 9% SGST), has to be charged.

- GL Entries at the time of posting invoice where Input Tax Credit is available, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase Account**|10000|
    |**CGST Receivable (Interim) Account**|900|
    |**SGST/UTGST Receivable (Interim) Account**|900|
    |**CGST Payable (Interim) Account**|-900|
    |**SGST/UTGST Payable (Interim) Account**|-900|
    |**Vendor Account**|10000|

- GL Entries at the time of posting invoice where Input Tax Credit is not available, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase Account**|11800|
    |**SGST Payable Acc(Interim)**|-900|
    |**CGST Payable Acc(Interim)**|-900|
    |**Vendor Account**|10000|


- GL Entries for Generating GST Liability and GST Credit where Input Tax Credit is available, will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**CGST Receivable Account**|900|
    |**SGST/UTGST Receivable Account**|900|
    |**CGST Receivable (Interim) Account**|-900|
    |**SGST/UTGST Receivable (Interim) Account**|-900|
    |**CGST Payable (Interim) Account**|900|
    |**SGST/UTGST Payable (Interim) Account**|900|
    |**CGST Payable Account**|-900|
    |**SGST/UTGST Payable Account**|-900|

- GL Entries for Generating GST Liability and GST Credit where Input Tax Credit is not available, will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**CGST Payable (Interim) Account**|900|
    |**SGST/UTGST Payable (Interim) Account**|900|
    |**CGST Payable Account**|-900|
    |**SGST/UTGST Payable Account**|-900|

- GL Entries for Reversing GST Liability and GST Credit where Input Tax Credit is available, will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**CGST Receivable Account**|-900|
    |**SGST/UTGST Receivable Account**|-900|
    |**CGST Receivable (Interim) Account**|900|
    |**SGST/UTGST Receivable (Interim) Account**|900|
    |**CGST Payable (Interim) Account**|-900|
    |**SGST/UTGST Payable (Interim) Account**|-900|
    |**CGST Payable Account**|900|
    |**SGST/UTGST Payable Account**|900|

- GL Entries for Reversing GST Liability and GST Credit where Input Tax Credit is not available, will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**CGST Payable (Interim) Account**|-900|
    |**SGST/UTGST Payable (Interim) Account**|-900|
    |**CGST Payable Account**|900|
    |**SGST/UTGST Payable Account**|900|

> [!TIP]
> In case of Inter-state Reverse Charge Service purchase, IGST Liability and IGST Credit will get generated.





## Related information 
[GST TDS TCS Overview](GST-TDS-TCS-Overview.md)

































[!INCLUDE[footer-include](../../includes/footer-banner.md)]
