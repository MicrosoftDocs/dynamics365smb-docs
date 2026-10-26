---
title: Voucher Transaction
description: Record cash, bank, contra, and journal voucher transactions, review posting examples, and print posted vouchers in Business Central for India.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, voucher transaction
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Voucher transaction

This article explains the process of recording day-to-day transactions through voucher interface.

## Type of vouchers and transactions

Following are the vouchers needed to record the transactions like Cash, Bank, and Journals for this functionality:

- Cash Receipt Voucher: Entries, which affect the Cash accounts while receiving cash payments from customers or refund from vendor.
- Cash Payment Voucher: Entries, which affect the Cash accounts while making cash payments to vendors or refund to customer
- Bank Receipt Voucher: Entries, which affect the Bank accounts while receiving payments from customers or refund from vendor.
- Bank Payment Voucher: Entries, which affect the Bank accounts while making payments to vendors or refund to customer.
- Contra Voucher: Entries, which affect the Cash and Bank Account together are termed as Contra Vouchers. For example, withdrawal from bank is one such transaction.
- Journal Voucher: Entries, which are affecting neither the Cash Account nor the Bank account are termed as Journal Vouchers.

## Fields for voucher entries

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Cash Receipt Voucher**, **Cash Payment Voucher**, **Bank Receipt Voucher**, **Bank Payment Voucher**, **Contra Voucher**, or **Journal Voucher**, and then choose the related link.
1. Fill in the fields required for your transaction. Not every field in the following table is mandatory for every voucher:

    |Field|Description|
    |----------------------------------|---------------------------------------|  
    |**Posting Date**|Specify the posting date.|  
    |**Document Type**|Specify document type as per transaction requirement, that is, Payment, Refund, etc.|
    |**Document No.**|Specifies the document number, which can be entered manually or assigned from the number series.|
    |**Account Type**|Select relevant account type, that is, Customer, Vendor, G/L Account, Bank, etc.|
    |**Account No.**|Select the relevant account number|
    |**Debit Amount**|Enter the debit amount when the line is a debit.|
    |**Credit Amount**|Enter the credit amount when the line is a credit.|
    |**Bal. Account Type**|Select the balancing account type when using a balancing account.|
    |**Bal. Account No.**|Select the balancing account number, or balance the document with separate journal lines.|
    |**Cheque No.**|Enter the cheque number for cheque transactions. Cheque fields are also available on contra and journal vouchers.|
    |**Cheque Date**|Enter the cheque date for cheque transactions.|
    |**Line Narration**|Optionally provide narration for the journal line.|
    |**Voucher Narration**|Optionally provide narration for the whole document.|

Posting validates accounts against the voucher setup for the line's location and template type. Set up the voucher before entering transactions. Narration is copied to posted narration records when the journal is posted.

### Posted general ledger entries for each voucher

- Payment received in cash from customer for INR 10,000 through Cash Receipt Voucher.

  GL Entries are as following:

  |Particulars|Amount|
  |----------------------------------|---------------------------------------|  
  |**Cash Account**|10000|
  |**Customer Account**|-10000|

  > [!TIP]
  > Cash is always debited in Cash receipt voucher.

- Payment made in cash to vendor for INR 10,000 through Cash Payment Voucher.

  GL Entries are as following:

  |Particulars|Amount|
  |----------------------------------|---------------------------------------|  
  |**Cash Account**|-10000|
  |**Vendor Account**|10000|

  > [!TIP]
  > Cash is always credited in Cash payment voucher.

- Payment received by cheque from customer for INR 10,000 through Bank Receipt Voucher.

  GL Entries are as following:

  |Particulars|Amount|
  |----------------------------------|---------------------------------------|  
  |**Bank Account**|10000|
  |**Customer Account**|-10000|

  > [!TIP]
  > Bank is always debited in Bank receipt voucher.

- Payment made by cheque to vendor for INR 10,000 through Bank Payment Voucher.

  GL Entries are as following:

  |Particulars|Amount|
  |----------------------------------|---------------------------------------|  
  |**Bank Account**|-10000|
  |**Vendor Account**|10000|

  > [!TIP]
  > Bank is always credited in Bank payment voucher.

- Payment made by cheque to vendor for INR 12,000 and INR 200 as Bank Charges through Bank Payment Voucher.

  GL Entries are as following:

  |Particulars|Amount|
  |----------------------------------|---------------------------------------|  
  |**Bank Account**|-12200|
  |**Vendor Account**|12000|
  |**Bank Charges Account**|200|

  > [!TIP]
  > Bank is always credited in Bank payment voucher.

- Cash Withdrawn/deposited or Transfer between bank accounts through Contra Voucher, for example Cash Withdrawn from Bank for INR 10,000.

  GL Entries are as following:

  |Particulars|Amount|
  |----------------------------------|---------------------------------------|  
  |**Bank Account**|-10000|
  |**Cash Account**|10000|

  > [!TIP]
  > Only Bank or Cash accounts can be allowed in Contra Voucher.

- Expense booked for INR 10,000 and crediting Vendor through Journal Voucher.

  GL Entries are as following:

  |Particulars|Amount|
  |----------------------------------|---------------------------------------|  
  |**Expenses Account**|10000|
  |**Vendor Account**|-10000|

  > [!TIP]
  > Bank and Cash accounts aren't allowed in Journal Voucher.

## Opening balances for GST

GST opening balances shall be created in Business Central. In Journal Voucher, options available to provide the opening balances for:

- GST Credit
- GST Liability
- GST TDS Credit
- GST TCS Credit

> [!NOTE]
>
> - Use positive amounts for GST credit opening balances.
> - Use negative amounts for GST liability opening balances.
> - Posting records the values in the GST subledger.

## TDS and TCS payment to government

It's required to pay the TDS and TCS to government authorities through Bank/Cash Payment Vouchers. Provision is available to select the TDS and TCS sub-ledger entries by applying filters like Companies/Non-Companies, etc. and on the basis of TAN and TCAN Numbers.

> [!NOTE]
> Details are available in respective TDS and TCS documents.

## Print a posted voucher

1. Open **General Ledger Entries**, and select an entry for the transaction.
1. Choose **Print Voucher**.
1. Review the report options, and preview or print the voucher.

The report is filtered by the selected entry's transaction number, not just the individual ledger entry.

## Related information

[Voucher Interface Overview](Vouche-Interface-Overview.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
