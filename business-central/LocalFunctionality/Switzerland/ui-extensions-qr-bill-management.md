---
title: QR-Bill Management [CH]
description: This article describes the enhancements for QR-Bill Management extension and how you can use Business Central to easily generate, send, and import your QR-bills.
author: sorenfriisalexandersen

ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: QR-bill, invoice, incoming documents, payment reference
ms.date: 03/22/2022
ms.author: soalex

---
# QR-Bill Management in the Swiss Version of Business Central

Since July 1, 2020, companies in Switzerland must be able to receive QR-bills. QR-bills are payment slips that follow invoices, and are a country-wide initiative to streamline payment processes. QR-bills replace all existing payment slips and ESR-related functionality. They contain all of the information needed to make payments, and a QR code on the payment slip makes it easy to import the information into [!INCLUDE[prod_short](../../includes/prod_short.md)]. All relevant information is imported and used to generate payments for the vendor who sent the QR-bill, including the payment reference, which automatically gets included in vendor ledger entries and exported in payment files to the bank.

## <a name="get-started"></a>Get started with the QR-Bill Management extension

The QR-Bill Management extension is included and automatically installed in [!INCLUDE[prod_short](../../includes/prod_short.md)]. To get started with the extension, you must make a few configuration changes in [!INCLUDE[prod_short](../../includes/prod_short.md)]. An easy way to that is to choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **QR-Bill Setup**, and then choose the related link. The guide will help you enter information, such as:

* Specify whether to use your IBAN or QR-IBAN.

  QR-IBAN is an IBAN that contains a number between 30000 and 31999 on positions 5 to 9, such as *CH55 30024 123456789012*.
* Define how to display names and addresses on QR-bills, and to use the German Umlaut Chars Encoding. We recommend that you use the default values.
* Select the **Default QR-Bill Layout**. The layout determines whether to use IBAN or QR-IBAN, whether the reference type is creditor or QR reference, and whether to include billing information in the SWICO format.
* Enable sales and service invoice types, and payment methods, for the QR-bills.
* Specify the journal template and journal batch to use when generating purchase journals from scanned or imported QR-bills.

If needed, you can change the layout settings on the **QR-Bill Layout** page.

## Issuing QR-Bills

You can enable QR-bills for sales and service invoices. This option adds an entry to **Report Selection - Sales** that generates an extra PDF with the QR-bill when invoices are generated. To enable the feature, choose the **Document Types enabled for QR-Bills** field in the **QR-Bill Setup** page, and activate the desired document types by selecting the appropriate box on the **Enabled** column.

## Adding billing information to QR-Bills

When you create a QR-bill you can include billing information in the SWICO format, as advocated by SIX, the Swiss payment infrastructure provider. Ideally, business applications that produce or import QR-bills should also be able to process information such as the VAT amount, the vendor's invoice number, and so on, because it can be valuable for the payable invoice. In [!INCLUDE[prod_short](../../includes/prod_short.md)], we import this information but use only the vendor's invoice number. If you want to use the other information, you can create your own customization.

## Understanding the payment reference

Payment processes are all about paying the right amount to the right party, and making it easy for them to reconcile payments to close outstanding accounts. The QR-Bill Management extension handles these processes by generating a payment reference for QR-bills that are unique for invoices issued in a specific company, which means the same payment reference cannot be issued more than one time.  

If your customer is also using [!INCLUDE[prod_short](../../includes/prod_short.md)], the payment reference is imported when receiving QR-bills, transferred to their **Vendor Ledger Entries** page, and used as a reference when creating vendor payments. For more information, see [Receiving QR-Bills](ui-extensions-qr-bill-management.md#receiving-qr-bills).

The flow is similar to the previous ESR Reference functionality that the QR-bills are replacing. Eventually, payment files (pain.001) will be sent from the customer's business app to their bank with the message to transfer the amounts to the vendor's account. The bank will produce a customer statement file (camt.054) that the vendor can import to reconcile accounts. This file will include the payment reference and is imported through the Data Exchange Framework that is updated by the QR-Bill Management extension to import camt.054 files.

For ESR references, you could configure information, for example, so that they contain the customer number and invoice number. You cannot configure the payment reference in QR-bills. There will always be a 1:1 relation between an issued QR-bill and a payment, which makes reconciliation easy and eliminates the need to configure the payment reference on QR-bills. Instead, [!INCLUDE[prod_short](../../includes/prod_short.md)] uses a unique counter for the payment reference. Additionally, logic is in place to block import or scan of the same payment reference twice.

### <a name="formats"></a>Formats for QR references and creditor references

The QR reference consists of 26 numerical positions plus a check digit.  

The ISO Creditor Reference (ISO 11649) enables the creditor to make automatic comparisons between their bills and the incoming payments. It must include the value *RF* in position 1-2 and a correct test character in position 3-4, and can include up to a maximum of 25 characters.  

## <a name="multiplebankaccounts"></a>Using multiple bank accounts as issuers of QR-Bills

Issuers of QR-Bills can use multiple bank accounts to route payments into different bank accounts. This is tied to the Payment Method on which you can specify the **QR-Bill Bank Account No.**. When specified, the IBAN/QR-IBAN information from this bank account will be used on QR-Bills that use the given Payment Method. This way you can route incoming payments into the desired bank account. If you do not use multiple bank accounts and specify the **QR-Bill Bank Account No.** on the **Payment Methods** card, the QR-IBAN/IBAN information from the **Company Information** page is used on QR-Bills instead. Make sure you have at least your primary bank account information set up there. For more information, see [Set Up Bank Accounts](bank-how-setup-bank-accounts.md).

> [!NOTE]
> If you are an issuer of QR-bills, make sure that you set up your bank accounts so that you identify with the right accounts towards your customers, depending on if you use QR-IBANs or regular IBANs. If you are a receiver and payer of QR-bills, we recommend that you set up vendor bank accounts correctly for payment and transfer to accounts with either regular IBANs or QR-IBANs.

### Add a QR-IBAN to a new or existing bank account

In order to use a QR-IBAN different from the one set in the **Company Information** page, you need to specify the bank account information in the **Bank Account Card**:

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, and then choose the related link.
2. In the **Payment Methods** list, choose the **New** or **Edit** action.
3. On the **Transfer** FastTab, enter the bank account in the **QR-IBAN** field.

## Scanning and Importing QR-Bills

To scan or import a QR-bill, you must use one of the following types of scanning devices:

* An input scanner that decodes the QR code and simulates the keyboard to paste the decoded value directly in a field in [!INCLUDE[prod_short](../../includes/prod_short.md)].
* A scanner that can decode the QR code and save it to a .txt file that you import to [!INCLUDE[prod_short](../../includes/prod_short.md)]. 

> [!NOTE]
> You cannot import QR-bills received as PDF files directly into [!INCLUDE[prod_short](../../includes/prod_short.md)] because [!INCLUDE[prod_short](../../includes/prod_short.md)] cannot interpret QR-codes. You must use one of the scanning methods.

## Receiving QR-Bills

You can receive QR-bills in several places in [!INCLUDE[prod_short](../../includes/prod_short.md)]:

* **Incoming Documents**, when you want a QR-bill to initiate the creation of a new purchase document or purchase journal.
* **Purchase Orders and Purchase Invoices**, when you want to import information from a QR-bill to an existing purchase document and use it to validate the amount and currency and to store the payment reference.
* **Purchase Journals**, when you want to create new purchase journal lines based on QR-bills. 

### Receiving a QR-bill through an incoming document

Receiving a QR-bill through incoming documents is especially useful when the process is automated, but you can also manually receive a QR-bill through incoming documents.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Incoming Documents**, and then choose the related link.
2. In the **Incoming Documents** list, create a new entry by choosing **New**, and then **New**.
3. On the **Incoming Document** page, enter a description in the **Description** field.
4. To import the QR-bill, choose one of the following actions:
   * **Scan QR-Bill** to scan a QR-bill into the incoming document entry.
   * **Import Scanned QR-Bill File** to use the file generated by the second scanner type described in the [Scanning and Importing QR-Bills section](#scanning-and-importing-qr-bills).

> [!TIP]
> After you import the QR-bill, you can check for errors on the **Matching Details** FastTab.

From the incoming document you can create a purchase journal or a purchase invoice, and the payment reference from the QR-bill will be assigned to both. For more information, see [Working with Incoming Documents](../../across-income-documents.md)

> [!NOTE]
> When you import QR-bills, [!INCLUDE[prod_short](../../includes/prod_short.md)] will try to find a vendor bank account that has a matching IBAN or QR-IBAN. When importing QR-bills on incoming documents, and thereby creating a document or purchase journal, the vendor bank account will determine the vendor to use. The incoming document approach helps ensure that the correct vendor is assigned.

### Receiving a QR-Bill through Purchase Orders or Purchase Invoices

Receiving a QR-bill through a purchase order or purchase invoice validates the invoice amount and adds the payment reference to the ledgers. Like incoming documents, you can scan or import a QR-bill to an existing purchase order or invoice. This process uses the QR-IBAN or IBAN from the QR-bill to find the vendor with a matching number. If no match is found, you cannot scan or import the QR-bill. If that happens, you can create the vendor bank account and then allow the QR-bill to be attached to the purchase document.

* To add a QR-Bill to an existing purchase document, select the target document and then choose either the **Scan QR-Bill** or the **Import Scanned QR-Bill File** action in the **Purchase Orders** or **Purchase Invoices** pages.

When the QR-bill is scanned or imported to the purchase document it will add the amount, payment reference, and other information from the QR-bill. These data are used for validation before posting the purchase document. Posting will be blocked if the amount of the order or invoice does not match the amount from the QR-bill. Validation also happens when you scan or import the QR-bill. If the payment reference is already used on a vendor ledger entry for a vendor, an error will display. Vendors cannot issue multiple QR-bills with the same payment reference. Similarly, an error will display if the QR-bill and payment reference has already been imported to an open purchase document.

### Receiving a QR-Bill through a purchase journal

You can scan or import QR-bills directly into a purchase journal. This option is useful when you want to create new journal lines based on a QR-bill. Scanning or importing directly into a purchase journal creates a new **Purchase Journal Line** using the vendor and amount from the QR-bill, and tries to identify the vendor by finding a **Vendor Bank Account** that has a matching IBAN or QR-IBAN. For example, using purchase journals is useful if you do not want to use purchase orders or invoices.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Journals**, and then choose the related link.
2. In the **Purchase Journals** list, create a new entry by choosing one of the following actions:
   * **Scan QR-Bill** to scan a QR-bill into the incoming document entry.
   * **Import Scanned QR-Bill File** to use the file generated by the second scanner type described in the [Scanning and Importing QR-Bills section](#scanning-and-importing-qr-bills).

## Reconciliation

When importing bank transactions (camt) on the **Payment Reconciliation Journals** page, the file is assumed to include the payment reference, which will automatically find the corresponding **Customer Ledger Entries** to settle.

## See also

[Swiss Electronic Payments](swiss-electronic-payments.md)  
[Switzerland Local Functionality](switzerland-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
