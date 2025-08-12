---
title: GST TDS and GST TCS on Customer Payments
description: Learn how to apply GST TDS and GST TCS on customer payments in Business Central for India.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, customer payments, TDS, TCS, GST
ms.date: 06/25/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# GST TCS on customer payments

GST TCS can be liable on cash or bank payment from customer. The GST TCS entries, which aren't reversed are part of settlement. Business user can reverse the GST TCS entries before settlement is posted. The GST TCS entries, which have Credit Availed field 'TRUE' are shown on settlement page. User can manually enter amount in GST TCS Credit Utilized field for utilizing against the liability.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Bank Receipt Voucher** or **Cash Receipt Voucher**, and then choose the related link.
1. Fill in the fields as described on **Bank Receipt Voucher** or **Cash Receipt Voucher**.

    |Field|Description|
    |---------------------------------|  ---------------------------------------|
    |**Posting Date**|Specify the posting date of the document.|
    |**Document Type**|Specify as 'Payment'|
    |**Account Type**|Specify as 'Customer'|
    |**Account No.**|Select the relevant customer code.|
    |**Amount**|Specify the amount.|
    |**Bal. Account Type**|Specify G/L Account or Bank Account.|
    |**Location Code**|Specify the relevant location code.|
    |**GST TCS State Code**|Specify the relevant state code.|
    |**GST TDS/TCS Base Amount**|Specify the GST TCS calculation base amount.|
    |**GST TCS**|Mark this field as True.|

For example, INR 1000 paid by the customer and 1% GST TCS (0.50% CGST, 0.50% SGST for Intra-State or Intra-Union Territory and 1% IGST for Inter State) has to be charged on the payment amount.

- GST Calculation appears in the Fact Box on Bank or Cash Receipt Voucher as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**Payment Amount**|1000|
    |**GST Transactional Value**|1,000|
    |**CGST Amount**|5|
    |**SGST Amount**|5|
    |**IGST Amount**|10|

- On posting of voucher for GST TCS - Intrastate Transaction, GL Entries are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|-1000|  
    |**CGST TCS Receivable Account**|5|  
    |**SGST/UTGST TCS Receivable Account**|5|
    |**Bank Account**|990|

- On posting of voucher for GST TCS - Interstate Transaction, GL Entries are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|-1000|  
    |**IGST TCS Receivable Account**|10|  
    |**Bank Account**|990|

## GST TDS on customer payment

GST TDS is applicable for Registered Customers. User can calculate GST TDS on cash or bank payment from customer, user needs to enter GST TDS/TCS Base Amount manually for calculating GST TDS.

A provision for updating GST TDS certificate details is available under Financial Management > Periodic Activities > GST > Task: Update GST TDS Certificate Dtl. The GST TDS entries against which the certificate is received are part of GST settlement.

User can reverse the GST TDS entries before certificate is received. An additional option has been provided to user to modify GST TDS Certificate Details. The GST TDS Credit received are shown on settlement page.

User can manually enter amount in GST TDS Credit Utilized field for utilizing against the liability.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Bank Receipt Voucher** or **Cash Receipt Voucher**, and then choose the related link.
1. Fill in the fields as described on **Bank Receipt Voucher** or **Cash Receipt Voucher**.

    |Field|Description|
    |---------------------------------|  ---------------------------------------|
    |**Posting Date**|Specify the posting date of the document.|
    |**Document Type**|Specify as 'Payment'|
    |**Account Type**|Specify as 'Customer'|
    |**Account No.**|Select the relevant customer code.|
    |**Amount**|Specify the amount.|
    |**Bal. Account Type**|Specify G/L Account or Bank Account.|
    |**Location Code**|Specify the relevant location code.|
    |**GST TDS/TCS State Code**|Specify the relevant state code.|
    |**GST TDS/TCS Base Amount**|Specify the GST TCS calculation base amount.|
    |**GST TDS**|Mark this field as True.|

For example, INR 1000 received from customer and 2% GST TDS (1% CGST, 1% SGST for Intra-State or Intra-Union Territory and 2% IGST for Inter State) has to be charged.

- GST calculation appears in the Fact Box on Cash or Bank Receipt Voucher as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**Payment Amount**|1000|
    |**GST Transactional Value**|1,000|
    |**CGST Amount**|10|
    |**SGST Amount**|10|
    |**IGST Amount**|20|

- On posting of voucher for GST TDS - Intrastate Transaction, GL Entries are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|-1000|  
    |**CGST TDS Receivable Account**|10|  
    |**SGST/UTGST TDS Receivable Account**|10|
    |**Bank Account**|980|

- On posting of voucher for GST TDS - Interstate Transaction, GL Entries are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|-1000|  
    |**IGST TDS Receivable Account**|20|  
    |**Bank Account**|980|

## Related information

[GST Credit and Liability Adjustment](GST-GST-Credit-and-Liability-Adjustment-for-Reverse-Charge-Service-Invoice.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
