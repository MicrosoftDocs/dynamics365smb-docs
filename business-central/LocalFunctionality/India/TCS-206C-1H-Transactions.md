---
title: TCS calculation and transactions as per Section 206C(1H)
description: TCS calculation and transactions as per Section 206C(1H)

author: v-debapd

    
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# TCS Calculation and Transactions as per Section 206C(1H)



As per new TCS rules, TCS is to be collected on receipt of payment that is over and above the threshold amount, the threshold amount is INR 50,00,000. User will receive payment from customer for sales of goods and services, TCS is to be calculated on receipt of payment for sale of goods.

Provision has been provided to enter amount on which TCS can be calculated on the event of receipt of payment from customer. In addition to it, provision for selecting posted sales lines for updating amount in 'TCS on Recpt. Of Pmt. Amount' in payment line has been provided. By this way, user will be able to update / enter applicable amount for TCS calculation in 'TCS on Recpt. Of Pmt. Amount' field.

When calculating TCS in payment lines, TCS Base amount will be considered from 'TCS on Recpt. Of Pmt. Amount' field instead of transaction amount. TCS calculation on payment lines should be same as TCS calculation on Invoices. If TCS Nature of Collection selected in payment line has 'TCS on Recpt. Of Pmt.' field as 'TRUE' in TCS Nature Of Collection table, then system should calculate TCS with Invoice logic, where TCS is calculated on forward calculation.


## TCS calculation on customer payments under section 206C(1H).

- Create General Journal, Cash Receipt Journal or Bank Receipt Journal

  1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **General Journal**, **Sales Journal**, **Cash Receipt Voucher** or **Bank Receipt Voucher**, and then choose the related link.
  2. Select **Document Type** as **Payment**.
  3. Select **Customer** in Account Type and select relevant customer code in Account No. field.
  4. Fill the **Amount** field with the credit amount.
  5. Select **G/L Account** or **Bank Account** in Bal. Account Type and select relevant expense account in Bal. Account. No. field.
  6. Select relevant **TCS Nature of Collection** in journal line. **Location Code** and **T.C.A.N No.** fields should not be blank.
  7. **TCS On Recpt. Of Pmt. Amount** can be updated in two different ways. One is you can put the amount directly in this field, else you can go to **Action** > **Function** > **Get Open Posted Lines For TCS Payment**, and select sales lines that are applicable for receipt of payment. System will update sum of the selected lines in 'TCS On Recpt. Of Pmt. Amount' field on payment journal line.
  8. If TCS Nature of Collection selected in payment line has **TCS on Recpt. Of Pmt.** field marked as 'TRUE' in TCS Nature Of Collection table, then system should calculate TCS on **TCS On Recpt. Of Pmt. Amount**, and should not calculate TCS on line amount.


### TCS to be calculated on customer receipt (through general journal, cash receipt journal and bank receipt journal)

For example, payment has been received from customer for INR 1,00,000 on which 0.10 % TCS is applicable for Nature of Collection '1H', 'TCS on Recpt. Of Pmt. Amount' is INR 75,000 hence 'TCS Base Amount' is also INR 75,000.
  
  - In this case TCS calculation will be as following:

    |Component|Value|
    |----------------------------------|---------------------------------------|  
    |**TCS Base Amount**|75,000|  
    |**TCS Amount**|75 (75000 x 0.10 %)|

  - GL Entries will be as following:
     
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Bank Account**|100000|
    |**Customer Account**|-100000|
    |**Customer Account**|75|
    |**TCS Payable Account**|-75|
    
## TCS calculation on customer payments under section 206C(1H) and where GST is also applicable.

- Create General Journal, Cash Receipt Journal or Bank Receipt Journal

  1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **General Journal**, **Sales Journal**, **Cash Receipt Voucher** or **Bank Receipt Voucher**, and then choose the related link.
  2. Select **Document Type** as **Payment**.
  3. Select **Customer** in Account Type and select relevant customer code in Account No. field.
  4. Fill the **Amount** field with the credit amount.
  5. Select **G/L Account** or **Bank Account** in Bal. Account Type and select relevant expense account in Bal. Account. No. field.
  6. Select relevant **TCS Nature of Collection** in journal line. **Location Code** and **T.C.A.N No.** fields should not be blank.
  7. **TCS On Recpt. Of Pmt. Amount** can be updated in two different ways. One is you can put the amount directly in this field, else you can go to **Action** > **Function** > **Get Open Posted Lines For TCS Payment**, and select sales lines that are applicable for receipt of payment. System will update sum of the selected lines in 'TCS On Recpt. Of Pmt. Amount' field on payment journal line.
  8. If TCS Nature of Collection selected in payment line has **TCS on Recpt. Of Pmt.** field marked as 'TRUE' in TCS Nature Of Collection table, then system should calculate TCS on **'TCS On Recpt. Of Pmt. Amount'**, and should not calculate TCS on line amount.
  9. Select **GST Group Code** and **HSN/SAC** Code then click on **GST on Advance Payment**. GST should be calculated normally as back ward calculation.

### TCS to be calculated on customer receipt (through general journal, cash receipt journal or bank receipt journal)

For example, payment has been received from customer for INR 1,00,000 on which 0.10 % TCS is applicable for Nature of Collection '1H', 'TCS on Recpt. Of Pmt. Amount' is INR 55,000 hence 'TCS Base Amount' is also INR 55,000. GST 18% will also be charged.
  
  - In this case TCS calculation will be as following:

    |Component|Value|
    |----------------------------------|---------------------------------------|
    |**TCS Base Amount**|75,000|  
    |**TCS Amount**|55 (55000 x 0.10 %)|
    |**GST Base Amount**|84,745.76|
    |**GST Amount**|15,254.24 (84745.76*18/100)|

  - GL Entries will be as following:
     
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Bank Account**|100000|
    |**Customer Account**|-100000|
    |**Customer Account**|55|
    |**TCS Payable Account**|-55|
    |**GST Receivable**|15,254.24|
    |**GST Payable**|-15,254.24|






## Related information 
[TCS 206C-1H-Overview](TCS-206C-1H-Overview.md)









[!INCLUDE[footer-include](../../includes/footer-banner.md)]