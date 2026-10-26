---
title: Transactions for Input Service Distributor
description: Describes how to process and record transactions for Input Service Distributor in Business Central, including purchase and return scenarios with GST calculations.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, input service distributor
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Transactions for input service distributor

This article explains purchase invoices and returns for an input service distributor location. The rates and amounts in the posting examples are illustrative.

## Purchase transaction with input service distribution location

1. [!INCLUDE [open-search](../../includes/open-search.md)] **Purchase Invoices**, and then choose the related link.
1. Select **Vendor** on **Purchase Invoice** header.
1. Specify **Location Code** on the invoice header. The location's GST registration number must have **Input Service Distributor** selected, which updates **GST Input Service Distributor** on the location.
1. Select **G/L Account** on the invoice line. Select a **GST Group Code** with **GST Group Type** set to **Service**, and check **HSN/SAC Code** and **GST Credit**.

For a GST invoice with input service distribution selected, the purchase line validation blocks **Item**, **Fixed Asset**, and **Charge (Item)** lines. Post the service invoice before selecting its entries in a GST distribution document.

- For example, service of INR 10000 purchased by Input Services Distributor where input tax credit is available, GST 18% (9% CGST and 9% SGST for Intra-State/Intra-Union Territory, 18% for Inter-State transaction) will be charged on the invoice amount.

    GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|

    G/L Entries for Intra-State Purchase of Services by Input Service Distributor where Input Tax Credit is available is as following:

    |Particulars|Amount|
    |---------|---------|
    |**Service Account**|10000|
    |**CGST Receivable Distributor Account**|900|
    |**SGST/UTGST Receivable Distributor Account**|900|
    |**Vendor Account**|-11800|

- For example, service of INR 10000 purchased by Input Services Distributor where input tax credit isn't available, GST 18% (9% CGST and 9% SGST for Intra-State/Intra-Union Territory, 18% for Inter-State transaction) will be charged on the invoice amount.

    GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|

    G/L Entries for Intra-State Purchase of Services by Input Service Distributor where Input Tax Credit isn't available is as following:

    |Particulars|Amount|
    |---------|---------|
    |**Service Account**|10000|
    |**CGST Expense Account**|900|
    |**SGST/UTGST Expense Account**|900|
    |**Vendor Account**|-11800|

- For example, service of INR 10000 purchased by Input Services Distributor where input tax credit is available, GST 18% (9% CGST and 9% SGST for Intra-State/Intra-Union Territory, 18% for Inter-State transaction) will be charged on the invoice amount.

    GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**IGST**|1800|  

    G/L Entries for Inter-State Purchase of Services by Input Service Distributor where Input Tax Credit is available is as following:

    |Particulars|Amount|
    |---------|---------|
    |**Service Account**|10000|
    |**IGST Receivable Distributor Account**|1800|
    |**Vendor Account**|-11800|

- For example, service of INR 10000 purchased by Input Services Distributor where input tax credit isn't available, GST 18% (9% CGST and 9% SGST for Intra-State/Intra-Union Territory, 18% for Inter-State transaction) will be charged on the invoice amount.

    GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**IGST**|1800|  

    G/L Entries for Inter-State Purchase of Services by Input Service Distributor where Input Tax Credit isn't available is as following:

    |Particulars|Amount|
    |---------|---------|
    |**Service Account**|10000|
    |**IGST Expense Account**|1800|
    |**Vendor Account**|-11800|

## Purchase return transaction with input service distribution location

1. [!INCLUDE [open-search](../../includes/open-search.md)] **Purchase Return Orders** or **Purchase Credit Memos**, and then choose the related link.
1. Select **Vendor** on **Purchase Return Order** or **Purchase Credit Memo** header
1. Specify **Location Code** on the return order or credit memo header. Check that the location has **GST Input Service Distributor** selected.
1. Select **G/L Account** on **Purchase Return Order** or **Purchase Credit Memo** line for service transaction.

- For example, service of INR 10000 returned by Input Services Distributor where input tax credit is available, GST 18% (9% CGST and 9% SGST for Intra-State/Intra-Union Territory, 18% for Inter-State transaction) will be charged on credit memo.

  GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|

  G/L Entries for Intra-State Purchase Return/Credit Memo of Services by Input Service Distributor where Input Tax Credit is available is as following:

    |Particulars|Amount|
    |---------|---------|
    |**Service Account**|-10000|
    |**CGST Receivable Distributor Account**|-900|
    |**SGST/UTGST Receivable Distributor Account**|-900|
    |**Vendor Account**|11800|

- For example, service of INR 10000 returned by Input Services Distributor where input tax credit isn't available, GST 18% (9% CGST and 9% SGST for Intra-State/Intra-Union Territory, 18% for Inter-State transaction) will be charged on credit memo.

  GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|

  G/L Entries for Intra-State Purchase Return/Credit Memo of Services by Input Service Distributor where Input Tax Credit isn't available is as following:

    |Particulars|Amount|
    |---------|---------|
    |**Service Account**|-10000|
    |**CGST Expense Account**|-900|
    |**SGST/UTGST Expense Account**|-900|
    |**Vendor Account**|11800|

- For example, service of INR 10000 returned by Input Services Distributor where input tax credit is available, GST 18% (9% CGST and 9% SGST for Intra-State/Intra-Union Territory, 18% for Inter-State transaction) will be charged on credit memo.

  GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**IGST**|1800|  

  G/L Entries for Inter-State Purchase Return/Credit Memo of Services by Input Service Distributor where Input Tax Credit is available is as following:

    |Particulars|Amount|
    |---------|---------|
    |**Service Account**|-10000|
    |**IGST Receivable Distributor Account**|-1800|
    |**Vendor Account**|11800|

- For example, service of INR 10000 returned by Input Services Distributor where input tax credit isn't available, GST 18% (9% CGST and 9% SGST for Intra-State/Intra-Union Territory, 18% for Inter-State transaction) will be charged on credit memo.

  GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**IGST**|1800|  

  G/L Entries for Inter-State Purchase Return/Credit Memo of Services by Input Service Distributor where Input Tax Credit isn't available is as following:

    |Particulars|Amount|
    |---------|---------|
    |**Service Account**|-10000|
    |**IGST Expense Account**|-1800|
    |**Vendor Account**|11800|

## Related information

[GST Input Service Distribution Process](GST-Input-Service-Distribution-Process.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]