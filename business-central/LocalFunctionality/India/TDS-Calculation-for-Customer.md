---
title: TDS calculation for Customer
description: Specifies a calculation and tracking process of TDS on customer

author: v-debapd

    
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf


ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# TDS for Customer 



This topic explains the process of calculating TDS on customer payments.

## TDS calculation and tracking of TDS certificate receivable

TDS can be deducted on receiving payment from customer. TDS can be calculated on the following documents:

- General Journal
- Cash Receipt Voucher
- Bank Receipt Voucher
- Cash Receipt Journal

TDS certificate will be receivable from customer on receiving the advance payment or issuing sales invoice to customer. TDS Certificate Receivable can be tracked through following documents:

- General Journal
- Cash Receipt Voucher
- Bank Receipt Voucher
- Cash Receipt Journal
- Sales Invoice

#### Mandatory fields for TDS calculation on general journal, cash receipt journal, bank receipt voucher and cash receipt voucher at the time of TDS calculation

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **General Journal**, **Cash Receipt Journal**, **Bank Receipt Voucher** or **Cash Receipt Voucher**, and then choose the related link. 
2. Select **Customer** in Account Type and select relevant customer code in **Account No.** field. Select **G/L Account** or **Bank Account** in Bal. Account Type and select relevant cash or bank account in **Bal. Account No.** field.
3. **TDS Certificate Receivable** field should be marked true and then select relevant **TDS Section** on journal line, **Location Code** field should not be blank.

#### Mandatory fields for TDS certificate receivable tracking on general journal, cash receipt journal, bank receipt voucher, cash receipt voucher and sales invoice

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **General Journal**, **Cash Receipt Journal**, **Bank Receipt Voucher**, **Cash Receipt Voucher** or **Sales Invoice**, and then choose the related link.
2. **TDS Certificate Receivable** should be marked true on **Journal** line or **Sales Invoice** header.
3. **TDS Certificate Receivable** identification will flow into Customer Ledger Entry on posting of the document.

#### TDS to be calculated on customer receipts (through general journal, cash receipt journal, bank receipt voucher, cash receipt voucher)

- In the given scenario, advance payment received from customer for INR 50,000 on which 2% TDS is applicable under TDS Section 194C.

  In this case TDS calculation will be as following:

    |Component|Value|
    |----------------------------------|---------------------------------------|  
    |**TDS Base Amount**|50000|  
    |**TDS Amount**|1000 (50000*2%)|

  GL Entries will be as following:
     
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|-50000|
    |**TDS Receivable Account**|1000|
    |**Bank Account**|49000|


#### TDS certificate is receivable against payment received from customer or against customer sales invoice

It is required to identify the payment or invoice transaction against which TDS certificate is receivable while receiving the payment from customer who has deducted TDS or issuing the sales invoice on which TDS has been deducted, it is required to identify the payment or invoice transaction against which TDS certificate is receivable.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **General Journal**, **Cash Receipt Journal**, **Bank Receipt Voucher**, **Cash Receipt Voucher** or **Sales Invoice**, and then choose the related link.
2. **TDS Certificate Receivable** should be marked true on **Journal** line or **Sales Invoice** header.
3. **TDS Certificate Receivable** identification will flow into Customer Ledger Entry on posting of the document.






## Related information 
[TDS Certificate Update](TDS-Certificate-Update.md)













[!INCLUDE[footer-include](../../includes/footer-banner.md)]
