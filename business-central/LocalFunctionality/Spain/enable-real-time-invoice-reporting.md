---
title: Enable Embedded VERI*FACTU Mode in Spain [ES]
description: Set up embedded VERIFACTU reporting in Business Central, configure certificate authentication, and review invoice submissions and QR codes for Spain.
author: altotovi
ms.topic: how-to
ms.devlang: al
ms.search.keywords: verifactu, embedded verifactu, AEAT, QR codes, embed QR codes, auditing, Spanish version
ms.date: 10/20/2026
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Enable embedded VERI\*FACTU mode in Spain

Use embedded VERI\*FACTU to report invoice records directly to the Spanish Tax Agency (AEAT) through the E-Documents framework. Business Central generates chained hashes and QR codes, and uses a certificate to authenticate the connection to AEAT.

The use of VERI\*FACTU is part of the Spanish regulatory framework, where companies must adopt a compliant e-invoicing approach. Depending on company size and applicable regulations, businesses can choose between **SII** and **VERI\*FACTU**. However, both modes can't be used simultaneously.

While compliance is mandatory, each company determines which approach, SII or VERI\*FACTU, best applies to its situation. Learn more about integrating VERI\*FACTU with external services in [VERI\*FACTU with external service integration](verifactu-setup.md).

Enable embedded VERI\*FACTU on the **Verifactu Setup** page. If SII is already enabled, Business Central asks you to disable it before you continue.

After you configure the service, workflow, and document sending profile, posting a sales invoice for a customer whose profile uses that workflow creates an e-document. The workflow exports and sends the invoice records to AEAT. Enabling **Verifactu Setup** alone doesn't submit every posted invoice.

Business Central generates the QR code during export, before it receives the AEAT response. The code contains an AEAT validation URL and invoice details. A QR code doesn't prove that AEAT accepted the submission. Check the e-document's clearance status separately.

## Prepare company and certificate information

The certificate authenticates requests to AEAT. Prepare the following company and certificate information:

1. Use an account with the **SUPER** permission set when creating a new certificate.
1. On the **Company information** page, perform the following actions:
   - Enter the **VAT Registration No.** from the qualified electronic certificate issued to you by the tax authorities. For example, **99999910G**.
   - Enter the company **Name** as mentioned in the certificate. For example, **CERTIFICADO PRUEBAS**.
   - Enter the **Post Code** and **City**.

1. Complete the other company information required for your invoices.
1. On the **Post Codes** page, set the **Time Zone** for the company's post code and city. Business Central checks this combination when you enable VERI\*FACTU.

   <!--:::image type="content" source="../../media/spanish-verifactu/timezone.png" alt-text="Screenshot that shows time zones for various places.":::-->

1. For the example in this article, use today's posting date. The Spanish Tax Authorities don't accept a date higher than today's.

   <!--:::image type="content" source="../../media/spanish-verifactu/my-settings.png" alt-text="Screenshot that shows my settings window.":::-->

## Set up VERI\*FACTU

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Verifactu Setup**, and then select the related link. The **Verifactu Setup** page displays.
1. In the **Certificate Code** field, open the lookup and select a valid certificate. Make sure its password is available and the certificate hasn't expired.
1. Select the **Enabled** toggle.

   :::image type="content" source="../../media/spanish-verifactu/setup-enabled.png" alt-text="Screenshot that shows the Verifactu Setup page.":::

> [!NOTE]
> Assigning a certificate can also enable the setup. When prompted, confirm that you want to disable SII and provide consent. If you decline either confirmation, VERI\*FACTU remains disabled.

## Set up the e-document service format

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **E-Document Services**, and then select the related link. The **E-Document Services** page displays.
1. Select **New** to create a new e-document service setup.
1. Fill up the following fields:
   - In the **Code** field, enter **VERIFACTU**.
   - In the **Description** field, enter **VERIFACTU**.
   - In the **Document Format** field, enter **Verifactu**.
   - In the **Service Integration** field, enter **Verifactu Service**.

    :::image type="content" source="../../media/spanish-verifactu/electronic-document-service.png" alt-text="Screenshot that shows the e-document service page.":::

> [!TIP]
> Go to **Configure documents to export** and select **E-Document Service Supported Source Document Types** to check the allowed documents for Verifactu.

<!--:::image type="content" source="../../media/spanish-verifactu/electronic-document-service-document-types.png" alt-text="Screenshot that shows the e-document service supported source document types.":::-->

## Set up workflows

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Workflows**, and then select the related link. The **Workflows** page displays.
1. If you're replacing an existing e-document workflow, disable that workflow.
1. Create a new workflow for Verifactu by filling in the following fields:
   - In the **Code** field, enter **VERIFACTU**.
   - In the **Description** field, enter **VERIFACTU**.
   - In the **Category** field, enter **EDOC**.
1. On the lines, enter the following text in these fields:
   - In **When Event**, enter **E-Document Created**.
   - In **Then Response**, enter **Export E-Document using setup: VERIFACTU**
   - In **When Event**, enter **E-Document has been exported**
   - In **Then Response**, enter **Send E-Document using service: VERIFACTU (indented)**

   :::image type="content" source="../../media/spanish-verifactu/workflow-steps.png" alt-text="Screenshot that shows the workflow page with the values.":::

1. Enable the workflow after you configure its steps and response options.

<!--If you need the e-document in Spanish language, then enter the text as shown in the following image:

   :::image type="content" source="../../media/spanish-verifactu/workflow-steps-spanish.png" alt-text="Screenshot that shows the workflow page with the Spanish values.":::-->

## Set up the document sending profile

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Document Sending Profiles**, and then select the related link. The **Document Sending Profiles** page displays.
1. Fill up the following fields:
   - In the **Code** field, enter **VERIFACTU**.
   - In the **Description** field, enter **Verifactu**.
   - In **Sending Options**, enter values in these fields as follows:
     - In the **Electronic Document** field, enter **E-Document Workflow**.
     - In the **E-Document Workflow** field, enter **VERIFACTU**.

   :::image type="content" source="../../media/spanish-verifactu/document-sending-profile.png" alt-text="Screenshot that shows the document sending profile for Verifactu.":::

1. Select **OK**.

## Set up sales report selection

If it isn't set up already, perform the following steps:

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Report Selection - Sales**, and then select the related link. The **Report Selection - Sales** page displays.
1. Ensure for the **Usage - Invoice**, the report ID **1306** is selected.

   :::image type="content" source="../../media/spanish-verifactu/report-selection-sales.png" alt-text="Screenshot that shows the report selection sales page.":::

## Set up the customer

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Customers**, and then select the related link. The **Customers** page displays.
1. Select a customer. For example, **50000 (Relecloud)**.
1. In the **Document Sending Profile** drop-down, select **VERIFACTU**.

   :::image type="content" source="../../media/spanish-verifactu/customer-document-sending-profile.png" alt-text="Screenshot that shows the customer card with Verifactu selected as the document sending profile.":::

## Example scenario - Set up sales invoice for customers and post it

The following example creates and posts a sales invoice for Relecloud. The customer's document sending profile uses the VERI\*FACTU workflow configured above.

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Sales Invoices**, and then select the related link.
1. Choose **New**, and select Relecloud as the customer.
1. In the **Posting Date** field, enter today's date.
1. Add a line Item, with **Quantity** as **5** and amount as 1000 + VAT.

   :::image type="content" source="../../media/spanish-verifactu/customer-sales-invoice.png" alt-text="Screenshot that shows the sales invoice for the customer.":::

1. Post the sales invoice.
1. Wait for the e-document workflow to finish exporting the invoice before you print its QR code.
1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Posted Sales Invoices**, and then select the related link. The **Posted Sales Invoices** page displays.

   :::image type="content" source="../../media/spanish-verifactu/customer-posted-sales-invoice.png" alt-text="Screenshot that shows the posted sales invoice for the customer.":::

1. Select **Print/Send** > **Print**. The **Sales Invoice** window displays.
1. In the **Report Layout** drop-down, select the **Standard Sales Invoice - E-Document (Word)** layout and select **OK**.

   :::image type="content" source="../../media/spanish-verifactu/report-layout.png" alt-text="Screenshot that shows the report layouts.":::

   You can select **Preview** to visualize the document and the **E-Doc QR Code** generated for Verifactu.

1. On the **Posted Sales Invoices** page, on the ribbon, select **Related** > **E-Document** > **Open**.

   :::image type="content" source="../../media/spanish-verifactu/posted-sales-invoice-related-ribbon.png" alt-text="Screenshot that shows the E-Document Card page.":::

   The **E-Document Card** page for the processed sales invoice for Relecloud displays with the clearance information.

   :::image type="content" source="../../media/spanish-verifactu/customer-sales-invoice-processed.png" alt-text="Screenshot that shows the E-Document page for the processed sales invoice for Relecloud.":::

   On the **E-Document Card** page, select **Document Logs** to see the invoice processing status. An AEAT submission status of `Correcto` sets the e-document service status to **Cleared**. Other submission statuses set it to **Not Cleared**.

   :::image type="content" source="../../media/spanish-verifactu/electronic-document-logs.png" alt-text="Screenshot that shows the e-document logs for the processed invoices.":::

[!INCLUDE [open-search](../../includes/open-search.md)], enter **Verifactu Documents**, and then select the related link to view submission details. The page shows the source document, hash, submission ID, and submission status.

:::image type="content" source="../../media/spanish-verifactu/document-submission-status.png" alt-text="Screenshot that shows the Verifactu document page with the submission status.":::

## Related information

- [VERI\*FACTU with external service integration](verifactu-setup.md)
- [Spain Local Functionality](spain-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
