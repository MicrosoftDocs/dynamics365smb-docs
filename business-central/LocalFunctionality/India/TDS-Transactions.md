---
title: TDS calculation on Purchase and Payment Transactions
description: TDS calculation on Purchase and Payment Transactions

author: v-debapd

    
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# TDS Calculation on Purchase and Payment Transactions



TDS can be deducted on expenses (GL Account) transactions. TDS can be deducted on purchase order, invoice received from vendor or advance payment made to vendor. TDS calculations can be done on following document types:

- Purchase Order
- Purchase Invoice
- General Journal
- Purchase Journal

## Mandatory fields for TDS calculation on general journal, purchase journal, purchase invoice, purchase order.

- Create General Journal or Purchase Journal

  1.  Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **General Journal** or **Purchase Journal**, and then choose the related link. 
  2. Select **Vendor** in Account Type and select relevant vendor code in Account No. field. Select **G/L Account** in Bal. Account Type and select relevant expense account in Bal. Account No. field.
  3. Select relevant **TDS Section** on journal line.  **Location Code** and **T.A.N No.** fields should not be blank.

- Create Purchase Invoice or Purchase Order

  1.  Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Purchase Invoice** or **Purchase Order**, and then choose the related link.
  2. Select **Vendor**, **Location Code** on **Purchase Order** or **Purchase Invoice** header
  3. Select **G/L Account** on **Purchase Order** or **Purchase Invoice** line.
  s4. **TDS Section**, **Location Code** and **T.A.N No.** fields should not be blank.

### TDS to be calculated on vendor invoice (through general journal, purchase journal, purchase invoice or purchase order)

In the given scenario, vendor has issued an invoice for INR 50,000 on which 2% TDS is applicable under TDS Section 194C.
  
  - In this case TDS calculation will be as following:

    |Component|Value|
    |----------------------------------|---------------------------------------|  
    |**TDS Base Amount**|50000|  
    |**TDS Amount**|1000 (50000*2%)|

  - On posting of invoice, GL Entries will be as following:
     
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Expense Account**|50000| 
    |**TDS Payable Account**|-1000| 
    |**Vendor Account**|-49000|

### TDS to be calculated on vendor advance payment (through general journal or payment journal)

In the given scenario, advance payment made to vendor for INR 50,000 on which 2% TDS is applicable under TDS Section 194C.

  - In this case TDS calculation will be as following:

    |Component|Value|
    |----------------------------------|---------------------------------------|  
    |**TDS Base Amount**|50000|  
    |**TDS Amount**|1000 (50000*2%)|

  - On posting of advance payment, GL Entries will be as following:
     
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Expense Account**|50000|
    |**TDS Payable Account**|-1000|
    |**Bank Account**|-49000|

On receiving the invoice from the vendor, TDS will be calculated on the differential amount. Suppose vendor sent an invoice of INR 120000. Since TDS has already been calculated at the time of payment, at the time of invoicing TDS will be calculated on the remaining amount i.e. INR 70000 (1200000 - 50000).

> [!NOTE]
> Advance payment needs to be applied with the invoice before posting. Otherwise TDS will be calculated on the whole invoice amount.

### TDS to be calculated on non-resident vendor invoice in foreign currency

In the given scenario, vendor issued an invoice for USD 10000 on which 2% TDS is applicable under TDS Section 195. All USD amounts will get converted into INR based on currency exchange rates. For this example exchange rate has been considered as USD 1 = INR 65.

  - In this case TDS calculation will be as following:

    |Component|Value|
    |----------------------------------|---------------------------------------|  
    |**TDS Base Amount**|USD 10000 or INR 650000|  
    |**TDS Amount**|INR 13000 (INR 650000*2%)|

  - On posting invoice, GL Entries, will be as following:
     
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Expense Account**|650000|
    |**TDS Payable Account**|-13000|
    |**Vendor Account**|-637000|

> [!TIP]
> Nature of Remittance and Act Applicable are mandatory for NRI Payments.

### TDS calculation on higher rate if vendor is not having PAN

PAN of vendor is mandatory for TDS calculation, but in case PAN is not available, higher rate of TDS will be deducted from the vendor.

In the given scenario, vendor issued an invoice for INR 50000 on which 2% TDS is applicable under TDS section 194C, but PAN is not available for vendor. In such a case 20% TDS will be charged as a higher rate.

  - In this case TDS calculation will be as following:

    |Component|Value|
    |----------------------------------|---------------------------------------|  
    |**TDS Base Amount**|50000|  
    |**TDS Amount**|10000 (50000*20%)|

  - On posting invoice, GL Entries, will be as following:
     
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Expense Account**|50000|
    |**TDS Payable Account**|-10000|
    |**Vendor Account**|-40000|

### Expenses partially subject to TDS

- In the given scenario, vendor issued an invoice for INR 112360, out of which INR 100000 is for auditing service on which 10% TDS will be applicable under Section 194J. INR 12360 is for other charges on which TDS is not applicable.
    
    In this case TDS calculation will be as following:

    |Component|Value|
    |----------------------------------|---------------------------------------|  
    |**TDS Base Amount**|100000|  
    |**TDS Amount**|10000 (100000*10%)|

  On posting invoice, GL Entries will be as following:
     
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Expense Account**|112360|
    |**TDS Payable Account**|-10000|
    |**Vendor Account**|-102360|

### TDS calculation on multiple expenses in a single invoice

A single invoice can be raised by the vendor for multiple expenses. For example, vendor issued a single invoice for INR 100000; INR 50000 each towards two services under TDS Section 194C and 194J.

  - In this case TDS calculation will be as following:

    |Component|Value|
    |----------------------------------|---------------------------------------|  
    |**TDS Base Amount**|100000|  
    |**TDS percent for 194C**|1000 (50,000x2%)|
    |**TDS percent for 194J**|5000 (50,000x10%)|

  - On posting invoice, GL Entries will be as following:
     
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Expense Account (194C)**|50000|
    |**Expense Account (194J)**|50000|
    |**TDS Payable Account (194C)**|-1000|
    |**TDS Payable Account (194J)**|-5000|
    |**Vendor Account**|-94000|


### TDS on expenses at lower rate or zero rate

If a vendor has a certificate of concessional rate instead of normal rate then to handle that scenario, concessional codes can be configured and attached to those vendors.

In the given scenario, vendor issued an invoice for INR 100000 towards professional services. Vendor has a certificate of income tax at Lower rate @ 5% on professional services instead of normal rate.

  - In this case TDS calculation will be as following:

    |Component|Value|
    |----------------------------------|---------------------------------------|  
    |**TDS Base Amount**|100000|  
    |**TDS Amount**|5000 (100000*5%)|

  - On posting invoice, GL Entries will be as following:
     
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Expense Account**|100000|
    |**TDS Payable Account**|-5000|
    |**Vendor Account**|-95000|

In this scenario, vendor issued an invoice for INR 100000 towards professional services. vendor has a certificate of income tax at Zero rate @ 0% on professional services instead of normal rate.

  - In this case TDS calculation will be as following:

    |Component|Value|
    |----------------------------------|---------------------------------------|  
    |**TDS Base Amount**|100000|  
    |**TDS Amount**|0 (100000*0%)|

  - On posting invoice, GL Entries will be as following:
     
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Expense Account**|100000|
    |**Vendor Account**|-100000|

> [!NOTE]
> Concession Code must be selected on vendor master for lower or zero rated TDS transactions.



## Related information 
[TDS Threshold](TDS-Threshold.md)




































[!INCLUDE[footer-include](../../includes/footer-banner.md)]
