---
title: Enable embedded Verifactu mode in Spain [ES]
description: Enable real-time invoice reporting to AEAT with Verifactu in Business Central, ensuring QR code, hash chaining, and digital signature compliance.
author: altotovi
ms.topic: article
ms.devlang: al
ms.search.keywords: verifactu, embedded verifactu, AEAT, QR codes, embed QR codes, auditing, Spanish version
ms.date: 05/28/2026
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Enable embedded Verifactu mode in Spain

Verifactu is Spain’s new mandatory e-invoicing standard, requiring businesses to report invoices in real time to the Spanish Tax Agency (AEAT) using digital signatures, hash chaining, and QR code verification for authenticity and traceability. This feature enables Spanish companies to submit invoices automatically to AEAT, embed official QR codes, and maintain legal audit trails, helping prevent fraud and streamline auditing.

Users can activate Verifactu mode by using a dedicated toggle, which ensures full compliance with Spanish e-invoicing regulations and prevents **SII** mode from being enabled at the same time.

Once the setup for Verifactu is complete, any invoices posted (**Posted Sales Invoice**) in Business Central are automatically sent to the AEAT for clearance through the **E-Document** framework.

After the invoice is successfully validated, the system incorporates the official QR code issued by the AEAT directly onto the invoice layout, allowing users to print or email invoices that are legally compliant and easily verifiable by customers.

## Enable digital signing

To enable digital signing, perform the following steps:

<!-- This step is an internal step for testing purpose *Download the certificate from https://safeexchange.smb.dynamics.com/viewdata/*--->

1. Create yourself as a Super user.
1. On the **Company information** page, perform the following actions:
   - Enter the **VAT Registration No.** from the qualified electronic certificate issued to you by the tax authorities. For example, **99999910G**.
   - Enter the company **Name** as mentioned in the certificate. For example, **CERTIFICADO PRUEBAS**.
   - Enter the **Post Code**.

1. Fill up the fields in the **Payments** tab. This tab shouldn’t be blank.
1. On the **Post Codes** page, set the **Time Zone** for the post code.

   <!--:::image type="content" source="../../media/spanish-verifactu/timezone.png" alt-text="Screenshot that shows time zones for various places.":::-->

1. Go to **My Settings** and set the **Working Date** to today’s date and set the **Region** as **Spanish (Spain, International Sort)**. The Spanish Tax Authorities don't accept a date higher than today’s.

   <!--:::image type="content" source="../../media/spanish-verifactu/my-settings.png" alt-text="Screenshot that shows my settings window.":::-->

## Set up Verifactu

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Verifactu Setup**, and then select the related link. The **Verifactu Setup** page displays.
1. Upload your certificate in the **Certificate Code** field.
1. Select the **Enabled** toggle.

   :::image type="content" source="../../media/spanish-verifactu/setup-enabled.png" alt-text="Screenshot that shows the Verifactu Setup page.":::

## Set up the e-document service format

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then select the related link. The **E-Document Services** page displays.
1. Select **New** to create a new e-document service setup.
1. Fill up the following fields:
   - In the **Code** field, enter **VERIFACTU**.
   - In the **Description** field, enter **VERIFACTU**.
   - In the **Document Format** field, enter **Verifactu**.
   - In the **Service Integration** field, enter **Verifactu Service**.

    :::image type="content" source="../../media/spanish-verifactu/edocument-service.png" alt-text="Screenshot that shows the e-document service page.":::

> [!TIP]
> Go to **Configure documents to export** and select **E-Document Service Supported Source Document Types** to check the allowed documents for Verifactu.

<!--:::image type="content" source="../../media/spanish-verifactu/edocument-service-document-types.png" alt-text="Screenshot that shows the e-document service supported source document types.":::-->

## Set up Workflows

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Workflows**, and then select the related link. The **Workflows** page displays.
1. On the **Workflows** page, switch off the current one for e-documents.
1. Create a new e-document for Verifactu by filling up the following fields:
   - In the **Code** field, enter **VERIFACTU**.
   - In the **Description** field, enter **VERIFACTU**.
   - In the **Category** field, enter **EDOC**.
   - Select the **Enabled** toggle.
1. On the lines, enter the following text in these fields:
   - In **When Event**, enter **E-Document Created**.
   - In **Then Response**, enter **Export E-Document using setup: VERIFACTU**
   - In **When Event**, enter **E-Document has been exported**
   - In **Then Response**, enter **Send E-Document using service: VERIFACTU (indented)**

   :::image type="content" source="../../media/spanish-verifactu/workflow-steps.png" alt-text="Screenshot that shows the workflow page with the values.":::

<!--If you need the e-document in Spanish language, then enter the text as shown in the following image:

   :::image type="content" source="../../media/spanish-verifactu/workflow-steps-spanish.png" alt-text="Screenshot that shows the workflow page with the Spanish values.":::-->

## Set up the Document Sending Profile

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Document Sending Profiles**, and then select the related link. The **Document Sending Profiles** page displays.
1. Fill up the following fields:
   - In the **Code** field, enter **VERIFACTU**.
   - In the **Description** field, enter **Verifactu**.
   - In **Sending Options**, enter values in these fields as follows:
     - In the **Electronic Document** field, enter **E-Document Workflow**.
     - In the **E-Document Workflow** field, enter **VERIFACTU**.

   :::image type="content" source="../../media/spanish-verifactu/document-sending-profile.png" alt-text="Screenshot that shows the document sending profile for Verifactu.":::

1. Select **OK**.

## Set up Report Selection - Sales

If it's not set up already, perform the following steps:

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Selection - Sales**, and then select the related link. The **Report Selection - Sales** page displays.
1. Ensure for the **Usage - Invoice** report ID **1306** is selected.

   :::image type="content" source="../../media/spanish-verifactu/report-selection-sales.png" alt-text="Screenshot that shows the report selection sales page.":::

## Set up/update the Customer

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then select the related link. The **Customers** page displays.
1. Select a customer. For example, **50000 (Relecloud)**.
1. In the **Document Sending Profile** drop-down, select **VERIFACTU**.

   :::image type="content" source="../../media/spanish-verifactu/relecloud-customer-document-sending-profile.png" alt-text="Screenshot that shows the customer card with Verifactu selected as the document sending profile.":::

## Example scenario - Set up sales invoice for customers and post it

The following steps are based on a use case scenario where a sales invoice is created for the customer Relecloud and then posted, which triggers the Verifactu process to send the invoice to AEAT and generate the QR code.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Invoices**, and then select the related link. The **Sales Invoice** page displays.
1. In the **Posting Date** field, enter **TODAY**.
1. Add a line Item, with **Quantity** as **5** and amount as 1000 + VAT.

   :::image type="content" source="../../media/spanish-verifactu/relecloud-sales-invoice.png" alt-text="Screenshot that shows the sales invoice for the customer.":::

1. Post the sales invoice.
1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Sales Invoices**, and then select the related link. The **Posted Sales Invoices** page displays.

   :::image type="content" source="../../media/spanish-verifactu/relecloud-posted-sales-invoice.png" alt-text="Screenshot that shows the posted sales invoice for the customer.":::

1. Select **Print/Send** > **Print**. The **Sales Invoice** window displays.
1. In the **Report Layout** drop-down, select the **Standard Sales Invoice - E-Document (Word)** layout and select **OK**.

   :::image type="content" source="../../media/spanish-verifactu/report-layout.png" alt-text="Screenshot that shows the report layouts.":::

   You can select **Preview** to visualize the document and the **E-Doc QR Code** generated for Verifactu.

1. On the **Posted Sales Invoices** page, on the ribbon, select **Related** > **E-Document** > **Open**.

   :::image type="content" source="../../media/spanish-verifactu/posted-sales-invoice-related-ribbon.png" alt-text="Screenshot that shows the E-Document Card page.":::

   The **E-Document Card** page for the processed sales invoice for Relecloud displays with the clearance information.

   :::image type="content" source="../../media/spanish-verifactu/relecloud-sales-invoice-processed.png" alt-text="Screenshot that shows the E-Document page for the processed sales invoice for Relecloud.":::

   On the **E-Document Card** page, select **Document Logs** to see the invoice processing status. In this case, the status is cleared, and AEAT accepts the document.

   :::image type="content" source="../../media/spanish-verifactu/edocument-logs.png" alt-text="Screenshot that shows the e-document logs for the processed invoices.":::

To view the submission status of the Verifactu document, choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Verifactu Document**, and then select the related link. The **Verifactu Document** page displays with the submission status.

:::image type="content" source="../../media/spanish-verifactu/document-submission-status.png" alt-text="Screenshot that shows the Verifactu document page with the submission status.":::
