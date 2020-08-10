---
    title: TDS calculation for Customer
    description: Specifies a calculation and tracking process of TDS on customer

    author: v-debapd

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: India, local, IN, English
    ms.date: 07/16/2020
    ms.author: v-debapd


---
# Transactions on TDS for Customer 

## TDS calculation and tracking of TDS Certificate Receivable

TDS can be deducted on receiving payment from customer. TDS can be calculated on the following documents:

- General Journal
- Cash Receipt Voucher
- Bank Receipt Voucher
- Cash Receipt Journal

TDS certificate will be receivable from customer on receiving the advance payment or issueing sales invoice to customer. TDS Certificate Receivable can be tracked through following documents:

- General Journal
- Cash Receipt Voucher
- Bank Receipt Voucher
- Cash Receipt Journal
- Sales Invoice

#### Mandatory fields for TDS calculation on General Journal, Cash Receipt Journal, Bank Receipt Voucher and Cash Receipt Voucher at the time of TDS calculation

1. Choose the ![img](image/search.jpg)icon, enter **General Journal**, **Cash Receipt Journal**, **Bank Receipt Voucher** or **Cash Receipt Voucher**, and then choose the related link. 
2. Select **Customer** in Account Type and select relevant customer code in **Account No.** field. Select **G/L Account** or **Bank Account** in Bal. Account Type and select relevant cash or bank account in **Bal. Account No.** field.
3. **TDS Certificate Receivable** field should be marked true and then select relevant **TDS Section** on journal line, **Location Code** field should not be blank.

#### Mandatory fields for TDS certificate receivable tracking on General Journal, Cash Receipt Journal, Bank Receipt Voucher, Cash Receipt Voucher and Sales Invoice

1. Choose the ![img](image/search.jpg)icon, enter **General Journal**, **Cash Receipt Journal**, **Bank Receipt Voucher**, **Cash Receipt Voucher** or **Sales Invoice**, and then choose the related link.
2. **TDS Certificate Receivable** should be marked true on **Journal** line or **Sales Invoice** header.
3. **TDS Certificate Receivable** identification will flow into Customer Ledger Entry on posting of the document.

#### TDS to be calculated on customer receipts (through General Journal, Cash Receipt Journal, Bank Receipt Voucher, Cash Receipt Voucher)

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


#### TDS Certificate is receivable against payment received from customer or against customer sales invoice

It is required to identify the payment or invoice transaction against which TDS certificate is receivable while receiving the payment from customer who has deducted TDS or issuing the sales invoice on which TDS has been deducted, it is required to identify the payment or invoice transaction against which TDS certificate is receivable.

1. Choose the ![img](image/search.jpg)icon, enter **General Journal**, **Cash Receipt Journal**, **Bank Receipt Voucher**, **Cash Receipt Voucher** or **Sales Invoice**, and then choose the related link.
2. **TDS Certificate Receivable** should be marked true on **Journal** line or **Sales Invoice** header.
3. **TDS Certificate Receivable** identification will flow into Customer Ledger Entry on posting of the document.