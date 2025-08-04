---
title: TDS calculation and transactions as per Section 194Q
description: TDS calculation and transactions as per Section 194Q.

author: v-debapd

    
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 06/25/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# TDS calculation and transactions as per Section 194Q

[!INCLUDE[vnext_preview](../../includes/vnext_preview.md)]

As per new TDS rules, TDS to be deducted to any person, being a buyer responsible for making a payment to a resident for purchase of goods when value or aggregate of purchase from a supplier or payment whichever is earlier, Rs.50 lacs during the previous year.

 As per this section, any purchase invoices/payments that is over and above the threshold amount (50,00,000). TDS amount to be deducted on amount exceeding threshold limit. For Example, Buyer buys goods from Seller amounting to INR. 85 lakhs and is liable to deduct TDS under section 194 Q. In this case TDS to be deducted on INR. 35 lakhs (85-50) @ 0.1%.

Provision (Calc. Over & Above Threshold) has been provided for user on TDS Rates to calculate TDS on amount that is over & above threshold.


The existing TDS calculation logic in system will work for invoice and advance payment normally, below are the functions for example:
  - TDS Calc. Over & Above Threshold
  - Normal TDS Calculation
  - TDS Calculation on Advance Payment

## TDS to be calculated on vendor invoice (through purchase invoice or purchase order).

In the given scenario, vendor has issued an invoice for INR 55,00,000, on which 0.10% TDS is applicable under TDS Section 194Q. Initial threshold achieved value or opening balance under section 194Q, is INR 20,00,000.
  
  - In this case TDS calculation will be as following:

    |Component|Value|
    |----------------------------------|---------------------------------------|  
    |**Initial threshold achieved value/ Opening Balance**|20,00,000|  
    |**1st Transaction, on or after 1st July 21**|2000000 – No TDS|    
    |**2nd Transaction, on or after 1st July 21**|1500000 – TDS Calculated|
    |**TDS Base Amount**|500000 (Total cumulative value 5500000 -5000000)|
    |**TDS Amount**|500 (500000*0.10%)|

  - On posting purchase invoice of second transaction, GL entries will be as following:
     
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Expense Account**|1500000|
    |**Vendor Account**|-1499500|
    |**TDS Payable Account**|-500|
    
## TDS to be calculated on vendor advance payment (through general or payment journal).

In the given scenario, two advance payments must made to vendor for INR 20,00,000 and 15,00,000 respectively, on which 0.10% TDS is applicable under TDS Section 194Q. Initial threshold achieved value or opening balance under section 194Q is INR 20,00,000. 

- In this case TDS calculation will be as following:

    | Component | Value |
    |----------------------------------|---------------------------------------|  
    |**Initial threshold achieved value/ Opening Balance**|2000000|  
    |**1st Transaction, on or after 1st July 21**|2000000 – No TDS|    
    |**2nd Transaction, on or after 1st July 21**|1500000 – TDS Calculated|
    |**TDS Base Amount**|500000 (Total cumulative value 5500000 -5000000)|
    |**TDS Amount**|500 (500000*0.10%)|

- On posting purchase invoice of second transaction, GL entries will be as following:
     
    | Particulars | Amount |
    |----------------------------------|---------------------------------------|  
    |**Vendor Account**|1500000|
    |**Bank Account**|-1499500|
    |**TDS Payable Account**|-500|


## Related information 
[TDS 194Q Overview](TDS-194Q-Section-Overview.md)






