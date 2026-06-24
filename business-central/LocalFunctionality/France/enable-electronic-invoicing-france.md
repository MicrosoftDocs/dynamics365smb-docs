---
title: Enable electronic invoicing with UBL 2.1 and Factur-X [FR]
description: Enable French e-invoicing in Business Central with UBL 2.1 (PEPPOL BIS 3.0) and Factur-X, ensuring DGFIP B2B compliance.
author: milicadjukic
ms.topic: article
ms.devlang: al
ms.search.keywords: e-invoicing, electronic invoicing, France, Factur-X, UBL, PEPPOL, CII, PDP, DGFIP, SIRET, SIREN, French version
ms.date: 06/23/2026
ms.author: milicadjukic
ms.reviewer: soumramani
ms.custom: references_regions
---

# Electronic invoicing in France with UBL 2.1 and Factur-X

France’s electronic invoicing reform (réforme de la facturation électronique) requires all businesses operating in France to exchange invoices electronically through certified Partner Dematerialization Platforms (PDPs). The reform is being introduced in phases and will ultimately apply to all B2B transactions. Compliant invoices must be submitted in one of the accepted semantic formats, such as **UBL 2.1** (PEPPOL BIS 3.0) or **Factur-X** (CII embedded in PDF/A-3), and must include required French identifiers such as SIRET, SIREN, and electronic routing addresses.

Business Central supports both formats through the **E-Reporting FR** extension, which enables French companies to:
- Generate UBL 2.1 invoices that comply with PEPPOL BIS 3.0 and include required French elements such as SIRET, SIREN, and electronic routing addresses.
- Generate Factur-X hybrid invoices (PDF/A-3 with embedded CII XML) at the EN 16931 profile level, including required French legal notices.
- Automatically import incoming Factur-X and UBL purchase invoices into purchase documents.

After setup is complete, invoices posted in Business Central are automatically exported in the selected format and sent through the E-Document framework for delivery to the PDP or the public invoicing portal (PPF).


## Prerequisites

Before you begin, make sure that:
- The **E-Reporting FR** extension is installed and enabled.
- You have a qualified electronic certificate, if your PDP requires one.
- Your company has valid **SIRET** and **SIREN** numbers.
- Customers are assigned electronic routing addresses.


## Set up company information

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png) icon, enter **Company Information**, and then select the related link.
2. Fill in the following fields required for French e-invoicing:

   | Field | Description | Example |
   |---|---|---|
   | **Name** | Your legal company name as registered. | Contoso France SAS |
   | **Address**, **Post Code**, **City** | Your registered business address. | 10 Rue de Rivoli, 75001, Paris |
   | **Country/Region Code** | Must be set (required for e-invoicing validation). | FR |
   | **VAT Registration No.** | Your intracommunity VAT number. | FR12345678901 |
   | **Registration No.** | Your **SIREN** number (9 digits). Used as the seller legal organization identifier (BT-30, schemeID `0002`) in the generated XML. | 123456789 |
   | **SIRET No.** | Your **SIRET** number (14 digits). Used as the seller identification (BT-29, schemeID `0009`) and the seller electronic endpoint address (BT-34). | 12345678901234 |
   | **IBAN** | The company bank account IBAN. Used in the payment means section (BT-84) of generated invoices. | FR76 1234 5678 9012 3456 7890 123 |
   | **SWIFT Code** | The BIC/SWIFT code for the company bank. Used in payment means (BT-86). | BNPAFRPP |

> [!IMPORTANT]
> The **Registration No.** (SIREN) and **SIRET No.** fields are required for French electronic invoicing. Before exporting a document, the system checks that both fields contain values. If either field is blank, you receive an error message.

## Set up customers for e-invoicing

Each customer who receives electronic invoices must have an electronic address configured for PDP routing.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png) icon, enter **Customers**, and then select the related link.
2. Open the customer card for the customer that you want to set up.
3. In the **Invoicing** FastTab (after the **VAT Registration No.** field), fill in the following fields:

   | Field | Description |
   |-------|-------------|
   | **Electronic Address** | The customer's electronic routing address for PDP delivery. This address is the endpoint identifier used in BT-49 (buyer electronic address). For example, the customer's SIRET number.|
   | **Electronic Address Scheme** | The scheme of the electronic address: **SIRET (0009)**, **SIREN (0002)**, or **Email (EM)**. |

> [!NOTE]
> The **Electronic Address** field (BT-49) is required for French e-invoicing under business rule BR-FR-12. If the field is blank, the system uses the customer’s **Registration Number**, truncated to 14 characters, with scheme `0009`. If neither value is available, the export validation check shows an error.

## Set up vendors for e-invoicing

If you want to import incoming electronic invoices from vendors, set up your vendors in the same way:

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png) icon, enter **Vendors**, and then select the related link.
2. Open the vendor card and then fill in the **Electronic Address** and **Electronic Address Scheme** fields in the same way as for customers.

## Set up e-document service format

Create an e-document service for each format that you want to use. The extension supports the following formats:

### Option A: Set up PEPPOL BIS 3.0 FR (UBL 2.1)

Use this format for structured XML electronic invoices in UBL 2.1 syntax. The format complies with PEPPOL BIS 3.0 and includes the required French elements.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png) icon, enter **E-Document Services**, and then select the related link.
2. Select **New** to create a new e-document service.
3. Fill in the following fields:

   | Field | Value |
   |-------|-------|
   | **Code** | PEPPOL-FR |
   | **Description** | PEPPOL BIS 3.0 FR |
   | **Document Format** | Peppol BIS 3.0 FR |
   | **Service Integration** | *(Set to your PDP integration connector, or leave as No Integration for manual export)* |

> [!NOTE]
> For PDP integration, you can choose either a [supported service provider](../../finance-how-setup-edocuments-external.md#available-service-providers) or another provider that's available through Marketplace.

### Option B: Set up Factur-X FR (CII)

Use this format for hybrid PDF/A-3 invoices with embedded CII XML conforming to the Factur-X EN 16931 (Extended) profile. This format produces a human-readable PDF with a machine-readable XML attachment.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png) icon, enter **E-Document Services**, and then select the related link.
2. Select **New** to create a new e-document service.
3. Fill in the following fields:

   | Field | Value |
   |---|---|
   | **Code** | FACTURX-FR |
   | **Description** | Factur-X FR |
   | **Document Format** | Factur-X FR |
   | **Service Integration** | *(Set to your PDP integration connector, or leave as No Integration for manual export)* |

> [!NOTE]
> Factur-X FR generates a **PDF file** (not raw XML). The file name extension is automatically set to `.pdf`. When you download or view the exported e-document from the E-Document Log, you receive a PDF file with the CII XML embedded as an attachment.

## Set up workflows

Create a workflow to automate the export and sending of e-documents. If you use more than one e-document format, such as PEPPOL and Factur-X, create a separate workflow for each format. Because all e-document workflows use the same **EDOC** category, add a **condition** to each workflow so that the system can determine which workflow to trigger for a document.

### Create Factur-X workflow

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png) icon, enter **Workflows**, and then select the related link.
2. Create a new workflow with the following settings:

   | Field | Value |
   |-------|-------|
   | **Code** | FACTURX-FR |
   | **Description** | Factur-X FR |
   | **Category** | EDOC |
   | **Enabled** | Yes |

3. On the workflow lines, enter:

   | When Event | Then Response |
   |------------|---------------|
   | E-Document Created | Send E-Document using service: FACTURX-FR |

4. Select the **On Condition** field on the **E-Document Created** event line. On the condition page, set the **E-Document Service Code** filter to **FACTURX-FR**. This setting ensures that the workflow triggers only for documents routed to the Factur-X service.

### Create PEPPOL workflow

1. Create another new workflow with the following settings:

   | Field | Value |
   |-------|-------|
   | **Code** | PEPPOL-FR |
   | **Description** | PEPPOL BIS 3.0 FR |
   | **Category** | EDOC |
   | **Enabled** | Yes |

2. On the workflow lines, enter:

   | When Event | Then Response |
   |------------|---------------|
   | E-Document Created | Send e-document using service: PEPPOL-FR |

3. Select the **On Condition** field on the **E-Document Created** event line. On the **Condition** page, set the **E-Document Service Code** filter to **PEPPOL-FR**. This setting ensures that the workflow triggers only for documents routed to the PEPPOL service.

> [!IMPORTANT]
> When multiple workflows share the same EDOC category, each workflow must have a condition on the event line to identify the service that it handles. Without conditions, both workflows trigger for every e-document, which can cause errors or duplicate exports.

## Set up document sending profile

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png) icon, enter **Document Sending Profiles**, and then select the related link.
2. Create a new document sending profile:

   | Field | Value |
   |-------|-------|
   | **Code** | FACTURX-FR *(or PEPPOL-FR)* |
   | **Description** | Factur-X FR *(or PEPPOL BIS 3.0 FR)* |
   | **Electronic Document** | E-Document Workflow |
   | **E-Document Workflow** | FACTURX-FR *(or PEPPOL-FR)* |

3. Select **OK**.

## Set up report selection — Sales

Configure the standard sales reports for invoicing:

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png) icon, enter **Report Selection - Sales**, and then select the related link.
2. Verify the following mappings:

   | Usage | Report ID | Report Name |
   |---|---|---|
   | Invoice | 1306 | Standard Sales - Invoice |
   | Credit Memo | 1307 | Standard Sales - Credit Memo |

> [!NOTE]
> The Factur-X format uses report rendering to generate a PDF file with embedded XML. The report extensions for **Standard Sales - Invoice** (10970), **Standard Sales - Credit Memo** (10971), **Service - Invoice** (10972), **Service - Credit Memo** (10973), **Reminder** (10974), and **Finance Charge Memo** (10975) automatically add the CII XML attachment to the PDF during the `OnPreRendering` trigger. This action occurs only when the document is exported through the Factur-X e-document workflow.

## Assign document sending profile to customers

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png) icon, enter **Customers**, and then select the related link.
2. Open the customer card.
3. In the **Document Sending Profile** field, select the profile that you created (for example, **FACTURX-FR**).

## Example scenario — Create, post, and export a sales invoice

The following steps show how to create, post, and automatically export a sales invoice as a Factur-X electronic invoice.

### Step 1: Create a sales invoice

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png) icon, enter **Sales Invoices**, and then select the related link.
2. Select **New** to create a sales invoice.
3. Select the customer (ensure the customer has a **Document Sending Profile** set to your e-invoicing profile and an **Electronic Address** configured).
4. In the **Posting Date** field, enter today's date.
5. Add one or more line items with quantity and unit price.

### Step 2: Post the sales invoice

1. Select **Post** to post the sales invoice.
2. Posting triggers the e-document workflow, which automatically does the following:
   - Creates an e-document record.
   - Exports the document in the configured format (Factur-X PDF or PEPPOL XML).
   - Sends the document through the configured service integration (if any).

### Step 3: View the e-document

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png) icon, enter **Posted Sales Invoices**, and then select the related link.
2. Select the posted invoice.
3. On the ribbon, select **Related** > **E-Document** > **Open** to view the **E-Document Card**.
4. The **E-Document Card** shows:
   - **Document No.**: The posted invoice number.
   - **Document Type**: Sales Invoice.
   - **Amount Excl. VAT** and **Amount Incl. VAT**: The invoice amounts.
   - **Status**: The current processing status, such as **Exported**, **Sent**, **Approved**, etc.

### Step 4: View document logs

On the **E-Document Card**, select **Document Logs** to view the processing history:
- **Export**: Shows when the document was exported and the format that was used.
- **Send**: Shows when and whether the document was sent to the PDP.
- **Clearance**: Shows the acceptance date/time when the PDP confirms receipt.

### Step 5: Print/preview the Factur-X PDF (optional)

If you use the Factur-X format, you can preview or print the generated PDF:

1. On the **Posted Sales Invoices** page, select **Print/Send** > **Print**.
2. The PDF contains the human-readable invoice with the CII XML embedded as an attachment named `factur-x.xml`.

## Importing incoming Factur-X invoices

The extension supports importing incoming Factur-X PDF invoices and converting them to purchase documents.

### How it works

1. When an incoming e-document is received in Factur-X format, which is a PDF file with embedded CII XML, the system does the following:
   - Extracts the CII XML from the PDF attachment.
   - Parses the **basic information**, such as the document number, document date, due date, currency, amounts, seller and buyer names, and VAT registration numbers.
   - Matches the seller to an existing vendor by GLN, VAT Registration No., or name and address.
   - Parses the **complete information**, including all line items with descriptions, quantities, unit prices, discounts, VAT rates, and amounts.
   - Applies invoice-level discounts (allowances) proportionally across purchase lines.
   - Creates header-level charge lines for surcharges.

2. The system recognizes the following document type codes:
   - **380**, **384**, **751**, **877**: Purchase Invoice
   - **381**, **261**: Purchase Credit Memo

## Importing incoming PEPPOL BIS 3.0 invoices

The extension also supports importing incoming PEPPOL BIS 3.0 (UBL 2.1) invoices. The import process uses the standard PEPPOL BIS 3.0 import functionality in the **E-Document Core** extension.

## Key French e-invoicing business rules

The following French-specific business rules are enforced by the extension:

| Rule | Description | Validation |
|------|-------------|------------|
| **BR-FR-02** | BT-29 (Seller identifier): SIRET is required. | Error if **SIRET No.** is empty in Company Information. |
| **BR-FR-03** | BT-30 (Seller legal registration): SIREN is required. | Error if **Registration No.** is empty in Company Information. |
| **BR-FR-05** | Mandatory French legal mentions must appear in the invoice. | Automatically added for Factur-X: recovery cost notice, late payment penalty rate, early payment discount statement. |
| **BR-FR-07** | BT-34 (Seller electronic address) is required. | Set from SIRET No. with scheme `0009`. |
| **BR-FR-12** | BT-49 (Buyer electronic address) is required. | Error if **Electronic Address** is empty on the Customer card (with fallback to Registration Number). |
| **BR-FR-DC** | Country/Region Code must be set for the seller. | Error if **Country/Region Code** is empty in Company Information. |

## Related information

- [E-Documents overview](../../finance-edocuments-overview.md)
- [E-Reporting in France](electronic-reporting-france.md)
- [Set up e-documents](../../finance-how-setup-edocuments.md)
- [France local functionality](france-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
