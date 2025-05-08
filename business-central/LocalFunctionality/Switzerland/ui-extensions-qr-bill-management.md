---
title: QR-Bill Management [CH]
description: Learn how the QR-Bill Management extension in Business Central simplifies the process of generating, sending, and importing QR-bills for streamlined payment management in Switzerland.
author: sorenfriisalexandersen
ms.topic: article
ms.devlang: al
ms.search.keywords: QR-bill, invoice, incoming documents, payment reference
ms.search.form: 11502, 11510, 11511, 11512, 11513, 11514, 11515, 11516, 11517, 11518
ms.date: 05/02/2025
ms.author: soalex
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# QR-bill Management in the Swiss version

Since July 1, 2020, companies in Switzerland must be able to receive QR-bills. QR-bills are payment slips that follow invoices, and are part of a country-wide initiative to streamline payment processes. QR-bills replace all existing payment slips and ESR-related functionality. They contain all the information needed to make payments, and a QR code on the payment slip makes it easy to import the information into [!INCLUDE[prod_short](../../includes/prod_short.md)]. All relevant information is imported and used to generate payments for the vendor who sent the QR-bill, including the payment reference, which automatically gets included in vendor ledger entries and exported in payment files to the bank.

## <a name="get-started"></a>Get started with the QR-Bill Management extension

The QR-Bill Management extension is included and automatically installed in [!INCLUDE[prod_short](../../includes/prod_short.md)]. To get started with the extension, you must make a few configuration changes in [!INCLUDE[prod_short](../../includes/prod_short.md)]. An easy way to do that is to choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **QR-Bill Setup**, and then choose the related link. The guide helps you enter information, such as:

- Specify whether to use your IBAN or QR-IBAN. QR-IBAN is an IBAN that contains a number between 30000 and 31999 on positions 5 to 9, such as *CH55 30024 123456789012*.
- Define how to display names and addresses on QR-bills, and how to use the German Umlaut Chars Encoding. (We recommend you use the default values.)
- Select the **Default QR-Bill Layout**. The layout determines whether to use IBAN or QR-IBAN, whether the reference type is creditor or QR reference, and whether to include billing information in the SWICO format.
- Enable sales and service invoice types and payment methods for QR-bills.
- Specify the journal template and journal batch to use when generating purchase journals from scanned or imported QR-bills.

If needed, you can change the layout settings on the **QR-Bill Layout** page.

## Issuing QR-bills

You can enable QR-bills for sales and service invoices. This option adds an entry to the **Report Selection - Sales** page that generates an extra PDF with the QR-bill when invoices are generated. To enable the feature, choose the **Document Types Enabled for QR-Bills** field on the **QR-Bill Setup** page, and activate the desired document types by selecting the appropriate box in the **Enabled** column.

## Adding billing information to QR-bills

When you create a QR-bill you can include billing information in the SWICO format, as advocated by SIX, the Swiss payment infrastructure provider. Ideally, business applications that produce or import QR-bills should also be able to process information such as the VAT amount, the vendor's invoice number, and so on, because it can be valuable for the payable invoice. In [!INCLUDE[prod_short](../../includes/prod_short.md)], we import this information but use only the vendor's invoice number. You need to customize if you want to include other information.

## Understanding the payment reference

Payment processes are all about paying the right amount to the right party, and making it easy for them to reconcile payments to close outstanding accounts. The QR-Bill Management extension handles these processes by generating a payment reference for QR-bills that is unique to invoices issued in a specific company, which means the same payment reference can't be issued more than once.  

If your customer is also using [!INCLUDE[prod_short](../../includes/prod_short.md)], the payment reference is imported when receiving QR-bills, transferred to their **Vendor Ledger Entries** page, and used as a reference when creating vendor payments. Learn more in [Receiving QR-Bills](ui-extensions-qr-bill-management.md#receiving-qr-bills).

The flow is similar to the previous ESR reference functionality that QR-bills are replacing. Eventually, payment files (pain.001) are sent from the customer's business app to their bank with the message to transfer the amounts to the vendor's account. The bank then produces a customer statement file (camt.054) that the vendor can import to reconcile accounts. This file includes the payment reference and is imported through the Data Exchange Framework that is updated by the QR-Bill Management extension to import camt.054 files.

For ESR references, you can configure information, for example, so they include the customer number and invoice number. You can't configure the payment reference in QR-bills. There will always be a 1:1 relation between an issued QR-bill and a payment, which makes reconciliation easy and eliminates the need to configure the payment reference on QR-bills. Instead, [!INCLUDE[prod_short](../../includes/prod_short.md)] uses a unique counter for the payment reference. Additionally, logic is in place to block the import or scan of the same payment reference twice.

### <a name="formats"></a>Formats for QR references and creditor references

The QR reference consists of 26 numerical positions plus a check digit.  

The ISO Creditor Reference (ISO 11649) enables the creditor to make automatic comparisons between their bills and the incoming payments. It must include the value *RF* in positions 1-2 and a correct test character in positions 3-4, and can include up to a maximum of 25 characters.  

## <a name="multiplebankaccounts"></a>Using multiple bank accounts as issuers of QR-bills

Issuers of QR-Bills can use multiple bank accounts to route payments into different bank accounts. This is tied to the payment method where you specify the **QR-Bill Bank Account No.** When specified, the IBAN/QR-IBAN information from this bank account will be used on QR-bills that use the given payment method. This way you can route incoming payments into the desired bank account. If you don't use multiple bank accounts and specify the **QR-Bill Bank Account No.** on the **Payment Methods** card, the QR-IBAN/IBAN information from the **Company Information** page is used on QR-Bills instead. Make sure you have at least your primary bank account information set up there. Learn more in [Set Up Bank Accounts](../../bank-how-setup-bank-accounts.md).

> [!NOTE]
> If you're an issuer of QR-bills, set up your bank accounts so the right accounts display to your customers, depending on if you use QR-IBANs or regular IBANs. If you're a receiver and payer of QR-bills, we recommend you set up vendor bank accounts correctly for payment and transfer to accounts with either regular IBANs or QR-IBANs.

### Adding a QR-IBAN to a new or existing bank account

To use a QR-IBAN different from the one set in the **Company Information** page, specify the bank account information in the **Bank Account Card**:

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, and then choose the related link.
1. In the **Payment Methods** list, choose the **New** or **Edit** action.
1. On the **Transfer** FastTab, enter the bank account in the **QR-IBAN** field.

## Scanning and importing QR-bills

To scan or import a QR-bill, you must use one of the following types of scanning devices:

- An input scanner that decodes the QR code and simulates the keyboard to paste the decoded value directly in a field in [!INCLUDE[prod_short](../../includes/prod_short.md)].
- A scanner that can decode the QR code and save it to a .txt file you import to [!INCLUDE[prod_short](../../includes/prod_short.md)].

> [!NOTE]
> You can't import QR-bills received as PDF files directly into [!INCLUDE[prod_short](../../includes/prod_short.md)] because [!INCLUDE[prod_short](../../includes/prod_short.md)] can't interpret QR codes. You must use one of the above-referenced scanning methods.

## Receiving QR-bills

You can receive QR-bills in several places in [!INCLUDE[prod_short](../../includes/prod_short.md)]:

- **Incoming Documents**, when you want a QR-bill to initiate the creation of a new purchase document or purchase journal.
- **Purchase Orders and Purchase Invoices**, when you want to import information from a QR-bill to an existing purchase document and use it to validate the amount and currency and to store the payment reference.
- **Purchase Journals**, when you want to create new purchase journal lines based on QR-bills.

### Receiving a QR-bill through an incoming document

Receiving a QR-bill through incoming documents is especially useful when the process is automated, but you can also manually receive a QR-bill through incoming documents.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Incoming Documents**, and then choose the related link.
1. In the **Incoming Documents** list, create a new entry by choosing **New**, and then **New**.
1. On the **Incoming Document** page, enter a description in the **Description** field.
1. To import the QR-bill, choose one of the following actions:
   * **Scan QR-Bill** to scan a QR-bill into the incoming document entry.
   * **Import Scanned QR-Bill File** to use a file generated by the second scanner type described in the [Scanning and importing QR-bills](#scanning-and-importing-qr-bills) section.

> [!TIP]
> After you import the QR-bill, you can check for errors on the **Matching Details** FastTab.

From the incoming document you can create a purchase journal or a purchase invoice, and the payment reference from the QR-bill is assigned to both. Learn more at [Working with Incoming Documents](../../across-income-documents.md).

> [!NOTE]
> When you import QR-bills, [!INCLUDE[prod_short](../../includes/prod_short.md)] looks for a vendor bank account that has a matching IBAN or QR-IBAN. When you import QR-bills on incoming documents, a document or purchase journal is created and the vendor bank account determines the vendor to use. The incoming document approach helps ensure that the correct vendor is assigned.

#### Receiving through the Kofax OCR service

> [!NOTE]
> If existing companies in [!INCLUDE[prod_short](../../includes/prod_short.md)] want a QR reference to be returned when they use the Kofax OCR service, they must update the existing data exchange definition that's used as **Data Exchange Type** for processing invoices in incoming documents.  

Complete the following steps to update an existing data exchange definition.

1. Select the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Data Exchange Definitions**, and then select the related link.
1. In the **Data Exchange Definitions** list, find the line you want to update, and open the card.
1. On the **Line Definitions** FastTab, select **OCRINVHEADER**.  
1. On the **Column Definitions** FastTab, create a new line, and enter the following values.

    | Field | Value |
    |-------|-------|
    | **Column No.** | 11513 |
    | **Name** | Swiss QR-Bill Reference No. |
    | **Description** | Swiss QR-Bill Reference No. |
    | **Path** | /Document/HeaderFields/HeaderField\[Type\[text()='qrreference'\]\]/Text |
1. On the **Line Definitions** FastTab, select **Field Mapping**.  
1. On the **Field Mapping** page, create a new line, and enter the following values.

    | Field | Value |
    |-------|-------|
    | **Column No.** | 11513 |
    | **Target Table ID** | 38 |
    | **Target Field ID** | 171 |
    | **Validate Only** | False |

1. Close the pages.  

### Receiving a QR-bill through purchase orders or purchase invoices

Receiving a QR-bill through a purchase order or purchase invoice validates the invoice amount and adds the payment reference to the ledgers. Like incoming documents, you can scan or import a QR-bill to an existing purchase order or invoice. This process uses the QR-IBAN or IBAN from the QR-bill to find the vendor with a matching number. If no match is found you can't scan or import the QR-bill, so you need to create the vendor bank account, and then allow the QR-bill to be attached to the purchase document.

To add a QR-bill to an existing purchase document, select the target document and then choose either the **Scan QR-Bill** or the **Import Scanned QR-Bill File** action on either the **Purchase Orders** or **Purchase Invoices** page.

When the QR-bill is scanned or imported to the purchase document, the amount, payment reference, and other information from the QR-bill are added. This data is used to validate the purchase document before it's posted. Posting is blocked if the amount on the order or invoice doesn't match the amount on the QR-bill. Validation also happens when you scan or import the QR-bill. If you upload the QR-Bill that doesn't contain the **Amount**, for example if the decoded QR-Bill has a blank line where amount should be, after you upload, the **QR-Bill** section is shown on the **Purchase Invoice** page. The **Amount** field of the **QR-Bill** section can be edited and you can add the appropriate amount to this field. If an uploaded QR-Bill does have value in the **Amount** field, it's automatically set to the **Amount** field of the **QR-Bill** section, but the field can still be edited.  

If the payment reference is already in use on a vendor ledger entry for a vendor, an error occurs. Vendors can't issue multiple QR-bills with the same payment reference. Similarly, an error occurs if the QR-bill and payment reference have already been imported to an open purchase document.

### Receiving a QR-bill through a purchase journal

You can scan or import QR-bills directly into a purchase journal. This option is useful when you want to create new journal lines based on a QR-bill. Scanning or importing directly into a purchase journal creates a new **Purchase Journal Line** using the vendor and amount from the QR-bill, and tries to identify the vendor by finding a **Vendor Bank Account** containing a matching IBAN or QR-IBAN. For example, using purchase journals is useful if you don't want to use purchase orders or invoices.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Journals**, and then choose the related link.
1. In the **Purchase Journals** list, create a new entry by choosing one of the following actions:
   - **Scan QR-Bill** to scan a QR-bill into the incoming document entry.
   - **Import Scanned QR-Bill File** to use the file generated by the second scanner type described in the [Scanning and importing QR-bills](#scanning-and-importing-qr-bills) section.

## Reconciliation

When importing bank transactions (camt) on the **Payment Reconciliation Journals** page, it's assumed the file includes the payment reference, and the corresponding **Customer Ledger Entries** is automatically found to settle the transaction.

## Related information

- [Swiss Electronic Payments](swiss-electronic-payments.md)  
- [Switzerland Local Functionality](switzerland-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
