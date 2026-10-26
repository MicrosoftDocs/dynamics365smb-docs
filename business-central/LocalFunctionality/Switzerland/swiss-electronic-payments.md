---
title: Swiss Electronic Payments
description: Learn about QR-bills, ESR, LSV+, and SEPA credit transfers for collecting customer payments and paying vendors in the Swiss version of Business Central.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: electronic payment methods, ESR, LSV+, SEPA credit transfers, Swiss version
ms.date: 10/19/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Swiss electronic payments

[!INCLUDE[prod_short](../../includes/prod_short.md)] supports Swiss payment processes for collecting customer payments and paying vendors. With QR-bills, you can issue payment slips and import payment details from vendor bills.

## Electronic payment methods

Swiss payment functionality includes the following methods:

- QR-bills
- Einzahlungsschein mit Referenznummer (ESR), which QR-bills replace
- Lastschrift Verfahren (LSV+)  
- SEPA credit transfers  

## QR-bills

Use QR-bills to include payment details and references with customer invoices. You can also scan or import decoded QR-code text to create purchase journal lines or update purchase documents. Learn more in [QR-bill management](ui-extensions-qr-bill-management.md).

## ESR

ESR is an electronic debtor service that uses payment slips to collect money. The ESR articles describe the earlier payment-slip workflow, which QR-bills replace. They cover printing ESR payment slips, calculating ESR reference numbers, and importing ESR payment files. Learn more in [Swiss electronic payments using ESR](swiss-electronic-payments-using-esr.md). The bank's version of ESR and ESR+ is named Bank-ESR (BESR).

## LSV+

LSV+ is a direct debit service that is used for processing payments. Companies can release customer payments directly from the customer's bank using direct debit. You can request and collect customer payments using direct debit in the LSV+ bank format, or in the DebitDirect PostFinance format. Learn more in [Swiss Electronic Payments Using LSV+](swiss-electronic-payments-using-lsv-.md).  

## SEPA credit transfers

To export payments according to the SEPA standard, you must use a bank account. On those bank accounts, the **Bank Acc. Posting Group** field must specify the relevant general ledger account. This way, the related general ledger entries are consistent with the entries that are generated for the Swiss payment methods. Learn more in [Make payments with SEPA credit transfer](../../finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md).

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
- [Make payments with SEPA credit transfer](../../finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
