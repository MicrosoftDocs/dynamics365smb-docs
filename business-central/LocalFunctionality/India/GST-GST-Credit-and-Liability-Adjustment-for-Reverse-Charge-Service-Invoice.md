---
title: GST Credit and GST Liability Adjustment for Open Reverse Charge Goods and Services Invoices
description: Explains how to adjust GST credit and GST liability for open reverse charge service invoices in Business Central India localization.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, liability adjustment, reverse charge goods, services invoices
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# GST credit and GST liability adjustment for open reverse charge goods and services invoices

This article explains the process of adjusting GST Credit and GST Liability for open reverse charge goods and services invoices.

> [!NOTE]
> The day counts below describe the article's background scenarios. Confirm the timing requirements for your transaction. Business Central uses the date formula you enter to select entries; opening the page doesn't post an adjustment automatically.

- For reverse charge invoices of goods, GST Liability and Credit shall be generated immediately, or in next 30 days from date of issue of supplier invoice, if payment to supplier isn't made against it.

- For reverse charge for service invoices, GST Liability and Credit shall be generated immediately, or 60 days from date of issue of supplier invoice, if payment to supplier isn't made against it.

- User can generate GST liability and credit for open reverse charge service invoice through GST Liability Adjustment.

  1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **GST Liability Adjustment**, and then choose the related link.
  1. Select the following in the request page

      |Field Name|Description|
      |----------------------------------|---------------------------------------|  
      |**Adjustment Document No.**|System generates number from number series assigned in Purchases & Payable Setup|
      |**GST Registration No.**|System lists only transactions posted with selected GST Registration No.|  
      |**Posting Date**|Adjustment posting date|  
      |**Liability Date Formula**|Enter 0D, 30D, or 60D. For example, if 60D is mentioned, the system reverses count 60 days from posting date for arriving Liability Filter Date|
      |**Liability Filter Date**|Calculated as the posting date minus the liability date formula. For example, 01-Jan-18 minus 60D gives 02-Nov-17. For **Generate**, the filter includes eligible open invoices posted on or before this date.|
      |**Vendor No.**|System lists invoice from this vendor only|
      |**Document No.**|System verifies only for this document|
      |**External Document No.**|System verifies only for this document|
      |**Nature of Adjustment**|User need to select the option, available options: Generate, Reverse|

  1. Choose **Apply Entries** to open **GST Liability Adj. Journal** with the matching entries.
  1. Review the adjustment lines, and then choose **Post** and confirm.

The registration number can't belong to an input service distributor. **Adjustment Document No.**, **GST Registration No.**, **Posting Date**, **Liability Date Formula**, and **Nature of Adjustment** are required. The date formula is a selection filter; choose it according to the requirements that apply to your transaction.

For example, vendor issued invoice for INR 10000, in an Intra-State or Intra-Union Territory transaction, and GST 18% (9% CGST and 9% SGST), has to be charged.

- GL Entries at the time of posting invoice where Input Tax Credit is available are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase Account**|10000|
    |**CGST Receivable (Interim) Account**|900|
    |**SGST/UTGST Receivable (Interim) Account**|900|
    |**CGST Payable (Interim) Account**|-900|
    |**SGST/UTGST Payable (Interim) Account**|-900|
    |**Vendor Account**|-10000|

- GL Entries at the time of posting invoice where Input Tax Credit isn't available are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase Account**|11800|
    |**SGST Payable Acc(Interim)**|-900|
    |**CGST Payable Acc(Interim)**|-900|
    |**Vendor Account**|-10000|

- GL Entries for Generating GST Liability and GST Credit where Input Tax Credit is available are as following:

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

- GL Entries for Generating GST Liability and GST Credit where Input Tax Credit isn't available are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**CGST Payable (Interim) Account**|900|
    |**SGST/UTGST Payable (Interim) Account**|900|
    |**CGST Payable Account**|-900|
    |**SGST/UTGST Payable Account**|-900|

- GL Entries for Reversing GST Liability and GST Credit where Input Tax Credit is available are as following:

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

- GL Entries for Reversing GST Liability and GST Credit where Input Tax Credit isn't available are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**CGST Payable (Interim) Account**|-900|
    |**SGST/UTGST Payable (Interim) Account**|-900|
    |**CGST Payable Account**|900|
    |**SGST/UTGST Payable Account**|900|

> [!TIP]
> In case of Inter-state Reverse Charge Service purchase, IGST Liability, and IGST Credit is generated.

## Related information

[GST TDS TCS Overview](GST-TDS-TCS-Overview.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
