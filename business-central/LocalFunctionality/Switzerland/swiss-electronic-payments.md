---
    title: Swiss Electronic Payments
    description: Swiss enhancements allow you to send invoices to customers electronically. The invoices are presented and paid directly using the customer's online banking software.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Swiss Electronic Payments
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] allows you to send invoices to customers electronically. The invoices are presented and paid directly using the customer's online banking software.  

## Electronic Payment Methods  
You can make electronic payments using the following methods:  

- Einzahlungsschein mit Referenznummer (ESR)  
- Lastschrift Verfahren (LSV+)  
- SEPA credit transfers  

## ESR  
ESR is an electronic debtor service that uses payment slips to collect money. It is the standard electronic payment system created by Swiss Post. You can print ESR payment slips as invoice attachments, calculate ESR reference numbers, and import ESR files that have payment information from banks. For more information, see [Swiss Electronic Payments Using ESR](how-to-print-esr-invoices.md). You can also make ESR and ESR+ payments using the bank's version of this payment method, which is named Bank-ESR (BESR).  

## LSV+  
LSV+ is a direct debit service that is used for processing payments. Companies can release customer payments directly from the customer's bank using direct debit. You can request and collect customer payments using direct debit in the LSV+ bank format, or in the DebitDirect PostFinance format. For more information, see [Swiss Electronic Payments Using LSV+](swiss-electronic-payments-using-lsv-.md).  

## SEPA Credit Transfers  
To export payments according to the SEPA standard, you must use a bank account. To make sure that the related general ledger entries are consistent with those generated for local Swiss payment methods (see above), the value in the **Bank Acc. Posting Group** field on the **Bank Account Card** page must point to the relevant general ledger account. For more information about how to export SEPA payments, see [Create SEPA Direct Debit Collection Entries and Export to a Bank File](../../finance-collect-payments-with-sepa-direct-debit.md#creating-sepa-direct-debit-collection-entries-and-export-to-a-bank-file).  

## See Also  
 [Import Swiss Bank Clearing Numbers](how-to-import-swiss-bank-clearing-numbers.md)  
 [Swiss Electronic Payments Using ESR](swiss-electronic-payments-using-esr.md)  
 [Print ESR Invoices](how-to-print-esr-invoices.md)  
 [Swiss Electronic Payments Using LSV+](swiss-electronic-payments-using-lsv-.md)  
 [Switzerland Local Functionality](switzerland-local-functionality.md)  
 [Making Payments](../../payables-make-payments.md)
