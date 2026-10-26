---
title: TCS Calculation and Transactions as per Section 206C(1H)
description: Review the documented section 206C(1H) TCS transaction workflow and illustrative calculation and accounting examples in Business Central for India.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, TCS calculation, Section 206C
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# TCS calculation and transactions as per Section 206C(1H)

This article describes TCS calculation on customer receipts using the section 206C(1H) configuration. The historical examples assume a threshold of INR 50,00,000 and a TCS rate of 0.10%. These values illustrate the calculation and aren't guidance on current tax law. Use the rates and thresholds that apply to your transactions.

Provision has been provided to enter amount on which TCS can be calculated on the event of receipt of payment from customer. In addition to it, provision for selecting posted sales lines for updating amount in 'TCS on Recpt. Of Pmt. Amount' in payment line has been provided. By this way, user is able to update / enter applicable amount for TCS calculation in 'TCS on Recpt. Of Pmt. Amount' field.

When **TCS On Recpt. Of Pmt.** is selected for the nature of collection, TCS uses **TCS On Recpt. Of Pmt. Amount** instead of the journal line amount as its base. The calculation adds TCS to this base rather than extracting it from an inclusive payment amount.

Before posting, specify **TCS Debit Note No.** in **General Ledger Setup** and an effective **TCS Posting Setup** line. Posting creates a separate customer debit note for the TCS amount.

The receipt examples assume that the threshold has already been exceeded, so the entered receipt base is fully taxable.

## TCS calculation on customer payments under section 206C(1H)

- Create General Journal, Cash Receipt Journal, or Bank Receipt Journal

  1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **General Journal**, **Sales Journal**, **Cash Receipt Voucher**, or **Bank Receipt Voucher**, and then choose the related link.
  1. Select **Document Type** as **Payment**.
  1. Select **Customer** in Account Type and select relevant customer code in Account No. field.
  1. Fill the **Amount** field with the credit amount.
  1. Select **G/L Account** or **Bank Account** in **Bal. Account Type**, and select the relevant cash or bank account in **Bal. Account No.**
  1. Select relevant **TCS Nature of Collection** in journal line. **Location Code** and **T.C.A.N No.** fields shouldn't be blank.
  1. Enter **TCS On Recpt. Of Pmt. Amount** directly, or choose **Get Open Posted Lines For TCS On Payment Calculation** and select the applicable sales lines. The lookup includes lines without a TCS nature of collection from the customer's open posted invoices. The selected line amounts, including GST where applicable, are totaled into the field. The amount must be nonnegative and can't exceed the absolute journal line amount.
  1. If TCS Nature of Collection selected in payment line has **TCS on Recpt. Of Pmt.** field marked as 'TRUE' in TCS Nature Of Collection table, then system should calculate TCS on **TCS On Recpt. Of Pmt. Amount**, and shouldn't calculate TCS on line amount.

### TCS to be calculated on customer receipt (through general journal, cash receipt journal and bank receipt journal)

For example, payment has been received from customer for INR 1,00,000 on which 0.10 % TCS is applicable for Nature of Collection '1H', 'TCS on Recpt. Of Pmt. Amount' is INR 75,000 hence 'TCS Base Amount' is also INR 75,000.
  
- In this case TCS calculation is as following:

  |Component|Value|
  |----------------------------------|---------------------------------------|  
  |**TCS Base Amount**|75,000|  
  |**TCS Amount**|75 (75000 x 0.10 %)|

- GL Entries are as following:

  |Particulars|Amount|
  |----------------------------------|---------------------------------------|  
  |**Bank Account**|100000|
  |**Customer Account**|-100000|
  |**Customer Account**|75|
  |**TCS Payable Account**|-75|
  
## TCS calculation on customer payments under section 206C(1H) and where GST is also applicable

- Create General Journal, Cash Receipt Journal, or Bank Receipt Journal

  1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **General Journal**, **Sales Journal**, **Cash Receipt Voucher**, or **Bank Receipt Voucher**, and then choose the related link.
  1. Select **Document Type** as **Payment**.
  1. Select **Customer** in Account Type and select relevant customer code in Account No. field.
  1. Fill the **Amount** field with the credit amount.
  1. Select **G/L Account** or **Bank Account** in **Bal. Account Type**, and select the relevant cash or bank account in **Bal. Account No.**
  1. Select relevant **TCS Nature of Collection** in journal line. **Location Code** and **T.C.A.N No.** fields shouldn't be blank.
  1. Enter **TCS On Recpt. Of Pmt. Amount** directly, or choose **Get Open Posted Lines For TCS On Payment Calculation** and select the applicable sales lines. The selected line amounts, including GST where applicable, are totaled into the field. The amount must be nonnegative and can't exceed the absolute journal line amount.
  1. If TCS Nature of Collection selected in payment line has **TCS on Recpt. Of Pmt.** field marked as 'TRUE' in TCS Nature Of Collection table, then system should calculate TCS on **'TCS On Recpt. Of Pmt. Amount'**, and shouldn't calculate TCS on line amount.
  1. Select **GST Group Code** and **HSN/SAC Code**, then select **GST on Advance Payment**. GST is calculated from the GST-inclusive receipt amount.

### TCS to be calculated on customer receipt (through general journal, cash receipt journal or bank receipt journal)

For example, payment has been received from customer for INR 1,00,000 on which 0.10 % TCS is applicable for Nature of Collection '1H', 'TCS on Recpt. Of Pmt. Amount' is INR 55,000 hence 'TCS Base Amount' is also INR 55,000. GST 18% will also be charged.
  
- In this case TCS calculation is as following:

  |Component|Value|
  |----------------------------------|---------------------------------------|
  |**TCS Base Amount**|55,000|
  |**TCS Amount**|55 (55000 x 0.10 %)|
  |**GST Base Amount**|84,745.76|
  |**GST Amount**|15,254.24 (84745.76*18/100)|

- GL Entries are as following:

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
