---
title: Swiss Electronic Payments
description: Learn about electronic payment methods, ESR, LSV+, and SEPA credit transfers.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: electronic payment methods, ESR, LSV+, SEPA credit transfers, Swiss version
ms.date: 04/30/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Swiss electronic payments

[!INCLUDE[prod_short](../../includes/prod_short.md)] allows you to send invoices to customers electronically. The invoices are presented and paid directly using the customer's online banking software.  

## Electronic payment methods

You can make electronic payments by using the following methods:  

- Einzahlungsschein mit Referenznummer (ESR)  
- Lastschrift Verfahren (LSV+)  
- SEPA credit transfers  

## ESR

ESR is an electronic debtor service that uses payment slips to collect money. It's the standard electronic payment system created by Swiss Post. You can print ESR payment slips as invoice attachments, calculate ESR reference numbers, and import ESR files that have payment information from banks. Learn more in [Swiss Electronic Payments Using ESR](how-to-print-esr-invoices.md). You can also make ESR and ESR+ payments using the bank's version of this payment method, which is named Bank-ESR (BESR).  

## LSV+

LSV+ is a direct debit service that is used for processing payments. Companies can release customer payments directly from the customer's bank using direct debit. You can request and collect customer payments using direct debit in the LSV+ bank format, or in the DebitDirect PostFinance format. Learn more in [Swiss Electronic Payments Using LSV+](swiss-electronic-payments-using-lsv-.md).  

## SEPA Credit Transfers

To export payments according to the SEPA standard, you must use a bank account. On those bank accounts, the **Bank Acc. Posting Group** field must specify the relevant general ledger account. This way, the related general ledger entries are consistent with the entries that are generated for the Swiss payment methods. Learn more in [Create SEPA Direct Debit Collection Entries and Export to a Bank File](../../finance-collect-payments-with-sepa-direct-debit.md#creating-sepa-direct-debit-collection-entries-and-export-to-a-bank-file), which provides information about how to export SEPA payments.  

### <a name="iban-qr"></a>IBAN and QR-IBAN

In Switzerland, requests for payments based on SEPA credit transfers can include a regular IBAN code for the bank account or a QR-IBAN code. Learn more in [QR-Bill Management](ui-extensions-qr-bill-management.md).  

The IBAN type on the recipient bank account must match the payment reference type on the entry when you try to pay a vendor. If the payment reference is a QR reference, [!INCLUDE [prod_short](../../includes/prod_short.md)] checks that the IBAN on the vendor bank account is a QR-IBAN code. If the payment reference is a creditor reference, that IBAN must be a normal IBAN.  

> [!TIP]
> If a vendor uses both types of accounts regularly, create multiple vendor bank accounts and use them accordingly. Learn more in [Using multiple bank accounts as issuers of QR-Bills](ui-extensions-qr-bill-management.md#multiplebankaccounts).

## Related information

- [QR-Bill Management in the Swiss Version](ui-extensions-qr-bill-management.md)
- [Import Swiss Bank Clearing Numbers](how-to-import-swiss-bank-clearing-numbers.md)
- [Swiss Electronic Payments Using ESR](swiss-electronic-payments-using-esr.md)
- [Print ESR Invoices](how-to-print-esr-invoices.md)
- [Swiss Electronic Payments Using LSV+](swiss-electronic-payments-using-lsv-.md)
- [Switzerland Local Functionality](switzerland-local-functionality.md)
- [Making Payments](../../payables-make-payments.md)
- [Create SEPA Direct Debit Collection Entries and Export to a Bank File](../../finance-collect-payments-with-sepa-direct-debit.md#creating-sepa-direct-debit-collection-entries-and-export-to-a-bank-file)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
