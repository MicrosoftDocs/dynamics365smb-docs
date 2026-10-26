---
title: GST TCS on Customer Payments
description: Apply GST TDS and GST TCS to customer receipts, and review certificate details and illustrative accounting entries in Business Central for India.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, customer payments, TDS, TCS, GST
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# GST TCS on customer payments

GST TCS can be liable on cash or bank payment from customer. The GST TCS entries, which aren't reversed are part of settlement. Business user can reverse the GST TCS entries before settlement is posted. The GST TCS entries, which have Credit Availed field 'TRUE' are shown on settlement page. User can manually enter amount in GST TCS Credit Utilized field for utilizing against the liability.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Bank Receipt Voucher** or **Cash Receipt Voucher**, and then choose the related link.
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
    |**GST TDS/TCS Base Amount**|Specify the GST TCS calculation base amount.|
    |**GST TDS/GST TCS**|Select **TCS**.|

The customer must have **GST Customer Type** set to **Registered**. Business Central compares the location state with the customer's bill-to state to determine the jurisdiction.

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

## Calculate GST TDS on a customer payment

GST TDS is applicable for Registered Customers. User can calculate GST TDS on cash or bank payment from customer, user needs to enter GST TDS/TCS Base Amount manually for calculating GST TDS.

Use **Update GST TDS Certificate Details** to record a received certificate. Settlement includes unreversed, unpaid TDS entries for which **Certificate Received** and **Credit Availed** are selected.

User can reverse the GST TDS entries before certificate is received. An additional option has been provided to user to modify GST TDS Certificate Details. The GST TDS Credit received are shown on settlement page.

User can manually enter amount in GST TDS Credit Utilized field for utilizing against the liability.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Bank Receipt Voucher** or **Cash Receipt Voucher**, and then choose the related link.
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
    |**GST TDS/TCS Base Amount**|Specify the GST TDS calculation base amount.|
    |**GST TDS/GST TCS**|Select **TDS**.|

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

## Record or correct a GST TDS certificate

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Update GST TDS Certificate Details**, and then choose the related link.
1. Enter **Customer No.**, **Certificate No.**, and **Date of Receipt**. To correct existing certificate details, select **Rectify**.
1. Choose **Update TDS Cert. Details** to open the matching entries.
1. Select **Certificate Received** consistently for every component of each document to update, and then choose **Update TDS Cert. Details**.

For a new certificate, the page lists unreversed TDS entries without a certificate number. For rectification, it lists unreversed, unpaid entries for the specified certificate. All components of a document must have the same **Certificate Received** selection.

The rates in the payment examples illustrate the calculations. Use the rates applicable to the transaction date. CGST and SGST are alternatives to IGST, not additional components on the same transaction.

## Related information

[GST Credit and Liability Adjustment](GST-GST-Credit-and-Liability-Adjustment-for-Reverse-Charge-Service-Invoice.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
