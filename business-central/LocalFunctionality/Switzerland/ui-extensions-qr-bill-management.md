---
title: QR-Bill Management in the Swiss Version [CH]
description: Set up QR-bill management in Business Central to issue payment slips, import vendor QR-bills, and reconcile incoming payments in Switzerland.
author: jswymer
ms.topic: article
ms.devlang: al
ms.search.keywords: QR-bill, invoice, incoming documents, payment reference
ms.search.form: 11502, 11510, 11511, 11512, 11513, 11514, 11515, 11516, 11517, 11518
ms.date: 10/19/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# QR-bill management in the Swiss version

Since July 1, 2020, companies in Switzerland must be able to receive QR-bills. QR-bills are payment slips that follow invoices, and are part of a country-wide initiative to streamline payment processes. QR-bills replace all existing payment slips and ESR-related functionality. They contain all the information needed to make payments, and a QR code on the payment slip makes it easy to import the information into [!INCLUDE[prod_short](../../includes/prod_short.md)]. All relevant information is imported and used to generate payments for the vendor who sent the QR-bill, including the payment reference, which automatically gets included in vendor ledger entries and exported in payment files to the bank.

> [!IMPORTANT]
> Use **Structured**, the recommended **Address Type** on the **QR-Bill Setup** page, to encode street names and building numbers separately.
>
> For your company, enter the street name in **Address** and the building number in **Address 2** on the **Company Information** page. For posted sales and service invoices, the QR code uses **Bill-to Address** for the street name and **Bill-to Address 2** for the building number.
>
> For example, enter Bahnhofstrasse in **Address** and 10 in **Address 2**. Don't combine the street name and building number in a single field when you use structured addresses. The QR code includes up to 70 characters for the street name and 16 characters for the building number.

The **Combined** address type joins **Address** and **Address 2** into one line and puts the post code and city on another line. This format doesn't encode the street name and building number separately. Use **Structured** when structured addresses are required.

## <a name="get-started"></a>Get started with the QR-bill management extension

The QR-Bill Management extension is included and automatically installed in [!INCLUDE[prod_short](../../includes/prod_short.md)]. To get started, open **Assisted Setup** and choose **Set up QR-Bills**. You can review or change the settings later on the **QR-Bill Setup** page. The guide helps you:

- Specify whether to use your IBAN or QR-IBAN. QR-IBAN is an IBAN that contains a number between 30000 and 31999 on positions 5 to 9, such as *CH55 30024 123456789012*.
- Define how to display addresses on QR-bills. We recommend **Structured**. QR codes use UTF-8 encoding, so you don't need a separate setting for German umlaut characters.
- Select the **Default QR-Bill Layout**. The layout determines whether to use IBAN or QR-IBAN, whether the reference type is creditor or QR reference, and whether to include billing information in the SWICO format.
- Enable document types and payment methods for QR-bills.
- Specify the journal template and journal batch to use when creating purchase or payment journal lines from QR-bills through incoming documents.

If needed, you can change the layout settings on the **QR-Bill Layout** page.

## <a name="issuing-qr-bills"></a>Issue QR-bills

You can enable QR-bills for posted sales invoices and posted service invoices. On the **QR-Bill Setup** page, select the link that shows how many document types are enabled for QR-bills. On the **QR-Bill Report Setup** page, select **Enabled** for each document type you want to use.

Enabling a document type adds the QR-bill report to the corresponding report selection. For example, posted sales invoices use **Report Selection - Sales**, and posted service invoices use **Report Selection - Service**. The QR-bill is generated as an additional PDF when you print the document.

On the **Payment Methods** page, use **QR-Bill Layout** to specify a layout for a payment method. When a document's payment method doesn't specify a layout, the **Default QR-Bill Layout** on the **QR-Bill Setup** page is used.

## <a name="adding-billing-information-to-qr-bills"></a>Add billing information to QR-bills

When you create a QR-bill, you can include billing information in the SWICO format, as advocated by SIX, the Swiss payment infrastructure provider. Specify a billing information format in the **Billing Information** field on the **QR-Bill Layout** page.

When you import a QR-bill, [!INCLUDE[prod_short](../../includes/prod_short.md)] reads the vendor's invoice number, document date, and VAT registration number from the SWICO billing information, when available. The invoice number and document date are transferred to the purchase document or journal line. Other billing details, such as VAT amounts, aren't used to calculate purchase lines or VAT. You need a customization to process those details automatically.

## <a name="understanding-the-payment-reference"></a>Understand the payment reference

The payment reference helps you match incoming payments to invoices. When you first print a QR-bill, the extension generates a reference from a company-specific counter and stores the reference on the customer ledger entry. For sales and service invoices, the reference is also stored on the posted invoice.

If your customer is also using [!INCLUDE[prod_short](../../includes/prod_short.md)], the payment reference is imported when receiving QR-bills, transferred to their **Vendor Ledger Entries** page, and used as a reference when creating vendor payments. Learn more in [Receiving QR-Bills](ui-extensions-qr-bill-management.md#receiving-qr-bills).

The flow is similar to the previous ESR reference functionality that QR-bills are replacing. Eventually, payment files (pain.001) are sent from the customer's business app to their bank with the message to transfer the amounts to the vendor's account. The bank then produces a customer statement file (camt.054) that the vendor can import to reconcile accounts. This file includes the payment reference and is imported through the Data Exchange Framework that is updated by the QR-Bill Management extension to import camt.054 files.

For ESR references, you can configure information, for example, so they include the customer number and invoice number. For QR-bills, [!INCLUDE[prod_short](../../includes/prod_short.md)] generates payment references from a counter in the company setup instead. You don't configure customer or invoice numbers as parts of the reference. When you reprint a QR-bill for a document that already has a payment reference, the existing reference is reused.

When you scan or import a QR-bill, [!INCLUDE[prod_short](../../includes/prod_short.md)] checks whether the same vendor and payment reference already occur on a purchase order, purchase invoice, purchase journal line, active incoming document, or nonreversed vendor invoice ledger entry. If a match is found, a warning identifies the existing record and asks whether you want to continue. Review the record before continuing to avoid duplicate processing.

### <a name="formats"></a>Formats for QR references and creditor references

The QR reference consists of 26 numerical positions plus a check digit.  

The ISO Creditor Reference (ISO 11649) enables the creditor to make automatic comparisons between their bills and the incoming payments. It must include the value *RF* in positions 1-2 and a correct test character in positions 3-4, and can include up to a maximum of 25 characters.  

## <a name="multiplebankaccounts"></a>Use multiple bank accounts as issuers of QR-bills

Issuers of QR-bills can route payments to different bank accounts. On the **Payment Methods** page, specify **QR-Bill Bank Account No.** for each payment method. QR-bills that use the payment method take the IBAN or QR-IBAN from that bank account, according to the selected layout.

If **QR-Bill Bank Account No.** is blank, the IBAN or QR-IBAN from **Company Information** is used instead. Set up your primary bank account information there. Learn more in [Set up bank accounts](../../bank-how-setup-bank-accounts.md).

> [!NOTE]
> If you're an issuer of QR-bills, set up your bank accounts so the right accounts display to your customers, depending on if you use QR-IBANs or regular IBANs. If you're a receiver and payer of QR-bills, we recommend you set up vendor bank accounts correctly for payment and transfer to accounts with either regular IBANs or QR-IBANs.

### Add a QR-IBAN to a new or existing bank account

To use a QR-IBAN different from the one set in the **Company Information** page, specify the bank account information in the **Bank Account Card**:

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Bank Accounts**, and then choose the related link.
1. In the **Bank Accounts** list, choose **New**, or select an existing bank account and choose **Edit**.
1. On the **Bank Account Card** page, enter the QR-IBAN in the **QR-IBAN** field.
1. Open **Payment Methods** and set **QR-Bill Bank Account No.** to this bank account for the payment methods that should use it.

## <a name="scanning-and-importing-qr-bills"></a>Scan and import QR-bills

To scan or import a QR-bill, use one of the following methods:

- An input scanner that decodes the QR code and simulates the keyboard to paste the decoded value directly in a field in [!INCLUDE[prod_short](../../includes/prod_short.md)].
- A scanner that can decode the QR code and save it to a .txt file you import to [!INCLUDE[prod_short](../../includes/prod_short.md)].
- Copy the decoded QR-code text from another application and paste it into **QR-Code Input** on the **QR-Bill Scan** page.

> [!NOTE]
> The **Import Scanned QR-Bill File** action reads decoded QR-code text, not QR-code images or PDF files. Decode the QR code before you import it.

## <a name="receiving-qr-bills"></a>Receive QR-bills

You can receive QR-bills in several places in [!INCLUDE[prod_short](../../includes/prod_short.md)]:

- **Incoming Documents**, when you want a QR-bill to initiate the creation of a new purchase document or purchase journal.
- **Purchase Orders and Purchase Invoices**, when you want to import information from a QR-bill to an existing purchase document and use it to validate the amount and currency and to store the payment reference.
- **Purchase Journals**, when you want to create new purchase journal lines based on QR-bills.

### Receive a QR-bill through an incoming document

Use an incoming document to review a QR-bill before you create a purchase invoice or journal line.

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Incoming Documents**, and then choose the related link.
1. Choose one of the following actions to create an incoming document from the QR-bill:
   * **Scan QR-Bill** to scan or paste decoded QR-code text.
   * **Import Scanned QR-Bill File** to import decoded QR-code text from a file.
1. On the resulting incoming document, review the imported details and the **Matching Details** FastTab.
1. Choose **Create Purchase Invoice** or **Create Journal Line** when you're ready to process the QR-bill.

> [!TIP]
> Resolve vendor matching before you create a document or journal line. **Create Purchase Invoice** requires a vendor. **Create Journal Line** also requires a vendor bank account.

From the incoming document, you can create a purchase invoice or a journal line. The journal template and batch on **QR-Bill Setup** determine where the journal line is created. A purchase journal template creates an invoice line, and a payment journal template creates a payment line. The payment reference is transferred to the document or journal line. Learn more in [Work with incoming documents](../../across-income-documents.md).

> [!NOTE]
> When you import QR-bills, [!INCLUDE[prod_short](../../includes/prod_short.md)] looks for a vendor bank account that has a matching IBAN or QR-IBAN. The matching bank account identifies the vendor on the incoming document. Importing the QR-bill doesn't automatically create a purchase document or journal line. Use the creation actions on the incoming document when you're ready.

#### Receive through the Kofax OCR service

> [!NOTE]
> If existing companies in [!INCLUDE[prod_short](../../includes/prod_short.md)] want a QR reference to be returned when they use the Kofax OCR service, they must update the existing data exchange definition that's used as **Data Exchange Type** for processing invoices in incoming documents.  

Complete the following steps to update an existing data exchange definition.

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Data Exchange Definitions**, and then select the related link.
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

### Receive a QR-bill through purchase orders or purchase invoices

You can scan or import a QR-bill to an existing purchase order or invoice. The IBAN or QR-IBAN identifies the vendor bank account. If the account belongs to a different pay-to vendor, the import isn't completed. If no matching account exists, you can create a bank account for the document's pay-to vendor during the import.

To add a QR-bill to an existing purchase document, open the **Purchase Order** or **Purchase Invoice** page, and then choose **Scan QR-Bill** or **Import Scanned QR-Bill File**.

The import stores the amount, currency, payment reference, and other QR-bill information on the purchase document. The **QR-Bill** FastTab shows the imported details. If the QR-bill has no amount, you can enter **Amount** on this FastTab. If the imported QR-bill includes a nonzero amount, **Amount** isn't editable.

When you post an invoice with an imported QR-bill and a nonzero QR-bill amount, the currency and total amount including VAT must match the QR-bill. A mismatch blocks posting. This QR-bill check doesn't apply when **Prepayment %** is nonzero.

If the vendor and payment reference already exist on another record, a warning asks whether you want to continue. Learn more in [Understand the payment reference](#understanding-the-payment-reference).

To remove an imported QR-bill, choose **Void the imported QR-Bill**. This action also clears **Payment Reference**, **Posting Description**, and **Vendor Invoice No.**, so review those fields before you continue.

### Receive a QR-bill through a purchase journal

You can scan or import QR-bills directly into a purchase journal. This option is useful when you want to create new journal lines based on a QR-bill. Scanning or importing directly into a purchase journal creates a new **Purchase Journal Line** using the vendor and amount from the QR-bill, and tries to identify the vendor by finding a **Vendor Bank Account** containing a matching IBAN or QR-IBAN. For example, using purchase journals is useful if you don't want to use purchase orders or invoices.

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Purchase Journals**, and then choose the related link.
1. Select the journal batch in which you want to create the line, and then choose one of the following actions:
   - **Scan QR-Bill** to create a journal line from decoded QR-code text.
   - **Import Scanned QR-Bill File** to use the file generated by the second scanner type described in the [Scanning and importing QR-bills](#scanning-and-importing-qr-bills) section.

## <a name="reconciliation"></a>Reconcile incoming payments

When you import bank transactions in camt format on the **Payment Reconciliation Journals** page, the payment reference helps match incoming payments to customer ledger entries. Make sure that your bank file and data exchange definition include the payment reference, and review the suggested applications before posting.

## Related information

- [Swiss Electronic Payments](swiss-electronic-payments.md)  
- [Switzerland Local Functionality](switzerland-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
