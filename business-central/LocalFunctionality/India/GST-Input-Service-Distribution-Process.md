---
title: Input Service Distribution Process
description: Set up and process input service distribution to allocate eligible GST credits across locations in the India localization of Business Central.
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, input service distribution, GST distribution process, inter-state distribution, intra-state distribution
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Input service distribution process

GST Input Service Distribution functionality is used to distribute CGST & SGST/IGST paid on Input services (Input Tax Credit) to other locations.

## GST distribution process

1. [!INCLUDE [open-search](../../includes/open-search.md)] **GST Distribution List**, and then choose the related link.
1. Create a distribution document and enter the relevant values on the **General** FastTab. Some fields are filled automatically.

    |Field|Description|
    |----------------------------------|---------------------------------------|  
    |**No.**|Specifies the unique number for the document.|
    |**ISD Document Type**|Shows the ISD document type. This field isn't editable.|
    |**From Location Code**|Specifies the location code from where input credit is distributed.|  
    |**Posting Date**|Specifies the posting date of the document.|
    |**Dist. Document Type**|Select **Invoice** or **Credit Memo** to identify the entries to distribute.|
    |**Dist. Credit Type**|Specifies the distribution credit type.|
    |**Total Amout Applied for Dist.**|Shows the total selected by using **Apply Entries**. This field isn't editable.|
    |**Distribution Basis**|Specifies the distribution basis.|

1. Enter the recipient locations and distribution percentages on the lines. The source location, posting date, GST registration numbers, and jurisdiction are filled from the document and location setup.

    |Field|Description|
    |----------------------------------|---------------------------------------|  
    |**Posting Date**|Specifies the posting date of the document.|  
    |**From Location Code**|Specifies the location code from where input credit is distributed.|  
    |**From GSTIN No.**|Specifies the GST registration number of the location defined in the **From Location Code**.|
    |**To Location Code**|Specifies the location code to which input credit is distributed.|
    |**To GSTIN No.**|Specifies the GST registration number of the location defined in the **To Location Code**.|
    |**Distribution Jurisdiction**|Specifies the distribution jurisdiction, for example, Interstate, Intrastate.|
    |**Distribution %**|Specifies the distribution percentage.|
    |**Distribution Amount**|Specifies the distribution amount.|
    |**Rcpt. Credit Type**|Specifies whether the input credit is available or not.|

1. Choose **Apply Entries** and select the entries to distribute. Select all GST components for each selected document line.
1. Review the distribution amounts and dimensions, and choose **Post**.

**Apply Entries** shows undistributed, nonexempt purchase service entries for the source GST registration number up to the document's **Posting Date**. It also filters by **Dist. Document Type** and **Dist. Credit Type**. Selecting **ISD Interstate Posting** further limits the entries to interstate transactions.

Before posting, the distribution percentages must total 100, and no line can have a zero percentage. A recipient with **Rcpt. Credit Type** set to **Availment** must have a GST registration number. Don't repeat the same recipient location and credit type on multiple lines.

## Inter-state and intra-state distribution of GST under input service distribution

The rates and amounts below are illustrative. The accounts used depend on GST posting setup and the recipient's credit type.

1. GL Entries for an Intra-state Distribution of Invoice to Recipient location (GST Credit is available for both the distributor and recipient locations). For example, service invoice issued for INR 1000 and CGST 9% and SGST 9% has been charged on the invoice, and the input service credit has been distributed to the recipient location.

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**SGST Receivable Account**|90|
    |**CGST Receivable Account**|90|
    |**SGST Receivable Account (Dist.)**|-90|
    |**CGST Receivable Account (Dist.)**|-90|

1. GL Entries for an Interstate Distribution of Invoice Recipient location (GST Credit is available for both the distributor and recipient locations). For example, service invoice issued for INR 1000 and IGST 18% has been charged on the invoice, and the input service credit has been distributed to the recipient location.

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**IGST Receivable Account**|180|
    |**IGST Receivable Account (Dist.)**|-180|

1. GL Entries for an Intrastate Distribution of Invoice to Recipient location (GST Credit isn't available for both the distributor and recipient locations). For example, service invoice issued for INR 1000 and CGST 9% and SGST 9% has been charged on the invoice, and the expense has been distributed to the recipient location.

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Freight**|180|
    |**GST Expense Account**|-90|
    |**GST Expense Account**|-90|

1. GL Entries for an Interstate Distribution of Invoice to Recipient location as Input Tax Credit (GST Credit isn't available for both the distributor and recipient locations). For example, service invoice issued for INR 1000 and IGST 18% has been charged on the invoice, and the expense has been distributed to the recipient location.
  
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Postage**|180|
    |**GST Expense Account**|-180|

1. GL Entries for an Intrastate Distribution of Credit Memo to Recipient location (GST Credit is available for both the distributor and recipient locations). For example, purchase credit memo has been raised for INR 1000 and CGST 9% and SGST 9% has been charged on the invoice, and the input service credit has been distributed to the recipient location.

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**SGST Receivable Account (Dist.)**|90|
    |**CGST Receivable Account (Dist.)**|90|
    |**SGST Receivable Account**|-90|
    |**CGST Receivable Account**|-90|

1. GL Entries for an Interstate Distribution of Credit Memo to Recipient location (GST Credit is available for both the distributor and recipient locations). For example, purchase credit memo has been raised for INR 1000 and IGST 18% has been charged on the invoice, and the input service credit has been distributed to the recipient location.

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**IGST Receivable Account (Dist.)**|180|
    |**IGST Receivable Account**|-180|

1. GL Entries for an Intrastate Distribution of Credit Memo to Recipient location (GST Credit isn't available for both the distributor and recipient locations). For example, purchase credit memo has been raised for INR 1000 and CGST 9% and SGST 9% has been charged on the invoice, and the expense has been distributed to the recipient location.

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Postage**|-180|
    |**GST Expense Account**|90|
    |**GST Expense Account**|90|

1. GL Entries for an Interstate Distribution of Credit Memo to Recipient location as Input Tax Credit (GST Credit isn't available for both the distributor and recipient locations). For example, purchase credit memo has been raised for INR 1000 and IGST 18% has been charged on the invoice, and the expense has been distributed to the recipient location.

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Postage**|-180|
    |**IGST Expense Account**|180|

## Related information

[GST Input Service Distribution Transaction](GST-Input-Service-Distribution-Transaction.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
