---
title: Transactions for Input Service Distributor
description: Transactions for Input Service Distributor

author: v-debapd

    
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Transactions for Input Service Distributor


In this document we are going to discuss the process and entries of input service distribution.

## Purchase transaction with input service distribution location

1. Choose the ![img.](image/search.jpg)icon, enter **Purchase Invoice**, and then choose the related link.
2. Select **Vendor** on **Purchase Invoice** header.
3. **Location** code should not be blank on **Purchase Invoice** header, and Input Service Distribution should be marked True on **Location** master.
4. Select **G/L Account** on **Purchase Invoice** line for service transaction.

- For example, service of INR 10000 purchased by Input Services Distributor where input tax credit is available, GST 18% (9% CGST and 9% SGST for Intra-State/Intra-Union Territory, 18% for Inter-State transaction) will be charged on the invoice amount.

    GST calculation will appear in the Fact Box, as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|

    G/L Entries for Intra-State Purchase of Services by Input Service Distributor where Input Tax Credit is available, will be as following:

    |Particulars|Amount|
    |---------|---------|
    |**Service Account**|10000|
    |**CGST Receivable Distributor Account**|900|
    |**SGST/UTGST Receivable Distributor Account**|900|
    |**Vendor Account**|-11800|

- For example, service of INR 10000 purchased by Input Services Distributor where input tax credit is not available, GST 18% (9% CGST and 9% SGST for Intra-State/Intra-Union Territory, 18% for Inter-State transaction) will be charged on the invoice amount.

    GST calculation will appear in the Fact Box, as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|

    G/L Entries for Intra-State Purchase of Services by Input Service Distributor where Input Tax Credit is not available, will be as following:

    |Particulars|Amount|
    |---------|---------|
    |**Service Account**|10000|
    |**CGST Expense Account**|900|
    |**SGST/UTGST Expense Account**|900|
    |**Vendor Account**|-11800|

- For example, service of INR 10000 purchased by Input Services Distributor where input tax credit is available, GST 18% (9% CGST and 9% SGST for Intra-State/Intra-Union Territory, 18% for Inter-State transaction) will be charged on the invoice amount.

    GST calculation will appear in the Fact Box, as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**IGST**|1800|  

    G/L Entries for Inter-State Purchase of Services by Input Service Distributor where Input Tax Credit is available, will be as following:

    |Particulars|Amount|
    |---------|---------|
    |**Service Account**|10000|
    |**IGST Receivable Distributor Account**|1800|
    |**Vendor Account**|-11800|

- For example, service of INR 10000 purchased by Input Services Distributor where input tax credit is not available, GST 18% (9% CGST and 9% SGST for Intra-State/Intra-Union Territory, 18% for Inter-State transaction) will be charged on the invoice amount.

    GST calculation will appear in the Fact Box, as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**IGST**|1800|  

    G/L Entries for Inter-State Purchase of Services by Input Service Distributor where Input Tax Credit is not available, will be as following:

    |Particulars|Amount|
    |---------|---------|
    |**Service Account**|10000|
    |**IGST Expense Account**|1800|
    |**Vendor Account**|-11800|

## Purchase return transaction with input service distribution location

1. Choose the ![img.](image/search.jpg)icon, enter **Purchase Return Order** or **Purchase Credit Memo**, and then choose the related link.
2. Select **Vendor** on **Purchase Return Order** or **Purchase Credit Memo** header
3. **Location** code should not be blank on **Purchase Return Order** or **Purchase Credit Memo** header, and Input Service Distribution should be marked True on **Location** master.
4. Select **G/L Account** on **Purchase Return Order** or **Purchase Credit Memo** line for service transaction.

- For example, service of INR 10000 returned by Input Services Distributor where input tax credit is available, GST 18% (9% CGST and 9% SGST for Intra-State/Intra-Union Territory, 18% for Inter-State transaction) will be charged on credit memo.

    GST calculation will appear in the Fact Box, as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|

    G/L Entries for Intra-State Purchase Return/Credit Memo of Services by Input Service Distributor where Input Tax Credit is available, will be as following:

    |Particulars|Amount|
    |---------|---------|
    |**Service Account**|-10000|
    |**CGST Receivable Distributor Account**|-900|
    |**SGST/UTGST Receivable Distributor Account**|-900|
    |**Vendor Account**|11800|

- For example, service of INR 10000 returned by Input Services Distributor where input tax credit is not available, GST 18% (9% CGST and 9% SGST for Intra-State/Intra-Union Territory, 18% for Inter-State transaction) will be charged on credit memo.

    GST calculation will appear in the Fact Box, as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|

    G/L Entries for Intra-State Purchase Return/Credit Memo of Services by Input Service Distributor where Input Tax Credit is not available, will be as following:

    |Particulars|Amount|
    |---------|---------|
    |**Service Account**|-10000|
    |**CGST Expense Account**|-900|
    |**SGST/UTGST Expense Account**|-900|
    |**Vendor Account**|11800|


- For example, service of INR 10000 returned by Input Services Distributor where input tax credit is available, GST 18% (9% CGST and 9% SGST for Intra-State/Intra-Union Territory, 18% for Inter-State transaction) will be charged on credit memo.

    GST calculation will appear in the Fact Box, as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**IGST**|1800|  
    
    G/L Entries for Inter-State Purchase Return/Credit Memo of Services by Input Service Distributor where Input Tax Credit is available, will be as following:

    |Particulars|Amount|
    |---------|---------|
    |**Service Account**|-10000|
    |**IGST Receivable Distributor Account**|-1800|
    |**Vendor Account**|11800|

- For example, service of INR 10000 returned by Input Services Distributor where input tax credit is not available, GST 18% (9% CGST and 9% SGST for Intra-State/Intra-Union Territory, 18% for Inter-State transaction) will be charged on credit memo.

    GST calculation will appear in the Fact Box, as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**IGST**|1800|  
    
    G/L Entries for Inter-State Purchase Return/Credit Memo of Services by Input Service Distributor where Input Tax Credit is not available, will be as following:

    |Particulars|Amount|
    |---------|---------|
    |**Service Account**|-10000|
    |**IGST Expense Account**|-1800|
    |**Vendor Account**|11800|

## Related information 
[GST Input Service Distribution Process](GST-Input-Service-Distribution-Process.md)









[!INCLUDE[footer-include](../../includes/footer-banner.md)]