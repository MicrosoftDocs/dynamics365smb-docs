---
    title: Swiss Electronic Payments
    description: Swiss enhancements allow you to send invoices to customers electronically. The invoices are presented and paid directly using the customer's online banking software.
    author: brentholtorf
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 03/22/2022
    ms.author: bholtorf
---
# Swiss Electronic Payments

[!INCLUDE[prod_short](../../includes/prod_short.md)] allows you to send invoices to customers electronically. The invoices are presented and paid directly using the customer's online banking software.  

## Electronic Payment Methods

You can make electronic payments by using the following methods:  

- Einzahlungsschein mit Referenznummer (ESR)  
- Lastschrift Verfahren (LSV+)  
- SEPA credit transfers  

## ESR

ESR is an electronic debtor service that uses payment slips to collect money. It is the standard electronic payment system created by Swiss Post. You can print ESR payment slips as invoice attachments, calculate ESR reference numbers, and import ESR files that have payment information from banks. For more information, see [Swiss Electronic Payments Using ESR](how-to-print-esr-invoices.md). You can also make ESR and ESR+ payments using the bank's version of this payment method, which is named Bank-ESR (BESR).  

## LSV+

LSV+ is a direct debit service that is used for processing payments. Companies can release customer payments directly from the customer's bank using direct debit. You can request and collect customer payments using direct debit in the LSV+ bank format, or in the DebitDirect PostFinance format. For more information, see [Swiss Electronic Payments Using LSV+](swiss-electronic-payments-using-lsv-.md).  

## SEPA Credit Transfers

To export payments according to the SEPA standard, you must use a bank account. On those bank accounts, the **Bank Acc. Posting Group** field must specify the relevant general ledger account. This way, the related general ledger entries will be consistent with the entries that are generated for the Swiss payment methods. For more information about how to export SEPA payments, see [Create SEPA Direct Debit Collection Entries and Export to a Bank File](../../finance-collect-payments-with-sepa-direct-debit.md#creating-sepa-direct-debit-collection-entries-and-export-to-a-bank-file).  

### <a name="iban-qr"></a>IBAN and QR-IBAN

In Switzerland, requests for payments based on SEPA credit transfers can include a regular IBAN code for the bank account or a QR-IBAN code. For more information, see [QR-Bill Management](ui-extensions-qr-bill-management.md).  

The IBAN type on the recipient bank account must match the payment reference type on the entry when you try to pay a vendor. If the payment reference is a QR reference, [!INCLUDE [prod_short](../../includes/prod_short.md)] will check that the IBAN on the vendor bank account is a QR-IBAN code. If the payment reference is a creditor reference, that IBAN must be a normal IBAN.  

> [!TIP]
> If a vendor uses both types of accounts regularly, create multiple vendor bank accounts and use them accordingly. For more information, see [Using multiple bank accounts as issuers of QR-Bills](ui-extensions-qr-bill-management.md#multiplebankaccounts).

## See Also

[QR-Bill Management in the Swiss Version](ui-extensions-qr-bill-management.md)  
[Import Swiss Bank Clearing Numbers](how-to-import-swiss-bank-clearing-numbers.md)  
[Swiss Electronic Payments Using ESR](swiss-electronic-payments-using-esr.md)  
[Print ESR Invoices](how-to-print-esr-invoices.md)  
[Swiss Electronic Payments Using LSV+](swiss-electronic-payments-using-lsv-.md)  
[Switzerland Local Functionality](switzerland-local-functionality.md)  
[Making Payments](../../payables-make-payments.md)
[Create SEPA Direct Debit Collection Entries and Export to a Bank File](../../finance-collect-payments-with-sepa-direct-debit.md#creating-sepa-direct-debit-collection-entries-and-export-to-a-bank-file)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]