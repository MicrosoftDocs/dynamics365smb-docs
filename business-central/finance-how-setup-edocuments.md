---
title: Set Up E-documents
description: Learn how to set up e-documents in Business Central with step-by-step configuration of services, formats, workflows, and document sending profiles.
author: altotovi
ms.author: altotovi
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: electronic document, electronic invoice, e-document, e-invoice
ms.search.form: 359, 360, 6103, 6133
ms.date: 07/17/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Set up e-documents

This article describes how to configure electronic documents (e-documents), and how to set up the E-Documents Service for e-document communications.

## Use the Clearance model if your country/region requires it

Some countries/regions, such as Spain, India, Mexico, and Italy, require that a tax authority or third-party certifier pre-approves invoices before businesses can send them to customers. This requirement is referred to as the _Clearance model_.

### Overview of the Clearance model process

The following is an example of the high-level steps in an approval and certification process for the Clearance model. The process might differ in your country/region.

1. The seller creates an invoice, and generates an XML or JSON file. The file type depends on country/regional requirements.
1. The seller submits the e-invoice to the tax authority. The tax authority adds a unique ID or a QR code and returns it to the seller.
1. The seller submits the e-invoice to a third-party certifier for validation. For example, the certifier validates the schema structure, content, checks for duplicates, and so on. If they approve the e-invoice, the certifier marks it as certified. For example, they might add a unique identifier, a digital signature, or a QR code.
1. The seller sends the certified e-invoice to the customer.

> [!TIP]
> If the tax authority provides a QR code, the returned JSON file includes it as a base64-encoded string. If you want to include the QR code in printed documents, you can update your document layout. [!INCLUDE [prod_short](includes/prod_short.md)] stores the QR code in the **Posted Sales Invoices** table. To learn more about document layouts, go to [Report and document layouts overview](ui-manage-report-layouts.md).

### E-Document setups for the Clearance model

> [!NOTE]
> Because the Clearance model differs in countries/regions, support for the model in [!INCLUDE [prod_short](includes/prod_short.md)] is a framework only. You must create an extension that meets the requirements in your country/region, and use the extension in your e-document service setup. To explore an example of an extension, go to the samples in our **BCTech** repository on GitHub and find [ClearanceServiceSample](https://github.com/microsoft/BCTech/tree/master/samples/ClearanceServiceSample).

You can set up an e-document service specifically for the Clearance model. The setup is almost the same as setting up any e-document service, with a few exceptions here and there. This section describes the settings that are specific to the Clearance model.

- When you set up the e-document service on the **E-Documents Services Setup** page, enter the following values in the following fields.

   - In the **Code** field, give the e-document service for the Clearance model a name that's easy to differentiate from the service provider.
   - In the **Document Format** field, choose **PEPPOL BIS 3.0**.
   - In the **Service Integration** field, choose the extension that you created for the Clearance model.

- Create a workflow that suits the process in your country/region. The following table shows an example of a workflow. Be sure to specify the correct service for the Clearance model and the provider for the then responses. To learn more about workflows, go to [Workflows in Business Central](across-workflow.md).

|When event  |On condition  |Then Response  |
|---------|---------|---------|
| E-document Created            | \<Always> | Export E-Document using setup: \<clearance model service>  |
| E-Document has been exported  | \<Always> | Send E-Document using setup: \<clearance model service>    |
| E-Document has changed        | \<Always> | Export E-Document using setup: \<service provider>  |
| E-Document has been exported  | \<Always> | Send E-Document using setup: \<service provider>    |
| E-Document has changed        | \<Always> | Send E-Document to customer                         |

## Set up an e-document service

To set up an e-document service, follow these steps.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **E-Document Services**, and then select the related link.
2. Select **New**, and then configure the fields on the **General** FastTab as described in the following table.

    | Field | Description |
    |-------|-------------|
    | Code | Select the electronic export setup code. |
    | Description | Enter a brief description of the electronic export setup. |
    | Document Format | The export format of the electronic export setup. By default, there are two options in this field. You can select **PEPPOL BIS 3** as a generic code-based format or **Data Exchange** when you must set up predocuments of specific formats on the **Data Exchange Definition** FastTab.</p> |
    | Service Integration | Select the integration code for the electronic export setup. Currently, the only option is **No integration**. |
    | Is a Clearance | Select this field only if your country/region uses a clearance e-invoicing model. When selected, the e-document service sends your invoice only to the tax authorities for clearance. You must configure another service to deliver the cleared invoice to the customer, along with a workflow that supports both the clearance and delivery steps. |

    > [!NOTE]
    > You can't use the clearance model until you choose a dedicated service integration.

3. On the **Importing** FastTab, configure the fields as described in the following table.

    | Field | Description |
    |-------|-------------|
    | Automatic Import | Specify whether documents should be automatically imported from the service. |
    | Automatic processing| Specify whether [!INCLUDE [prod_short](includes/prod_short.md)] uses your e-document setup to automatically create a purchase document based on the received e-document. If you choose **No**, [!INCLUDE [prod_short](includes/prod_short.md)] creates the e-document, but you must review its details before you create the purchase document. |
    | Validate Receiving Company | Specify whether the receiving company information must be validated during import. |
    | Resolve Unit Of Measure | Specify whether to resolve the unit of measure during import. |
    | Lookup Item Reference | Specify whether to search for items by item reference during import. |
    | Lookup Item GTIN | Specify whether to search for items by global trade item number (GTIN) during import. |
    | Lookup Account Mapping | Specify whether to search for accounts in **Account Mapping** by the incoming text during import. |
    | Validate Line Discount | Specify whether to validate a line discount during import. |
    | Apply Invoice Discount | Specify whether to apply an invoice discount during import. |
    | Verify Totals | Specify whether to verify invoice totals during import. |
    | Create Journal Lines | Specify whether a journal line must be created instead of a purchase document. Select this option when you want to use journals as a destination for your invoices. |
    | General Journal Template Name | Specify the name of the general journal template that's used for journal line creation. This field is applicable when you want to use journals as a destination for your invoices. |
    | General Journal Batch Name | Specify the name of the general journal batch that's used for journal line creation. This field is applicable when you want to use journals as a destination for your invoices. |
    | Batch Start Time | Specify the start time for import jobs. |
    | Minutes between runs | Specify the number of minutes between import job runs. |

4. If you selected **Data Exchange** in the **Document Format** field on the **General** FastTab, on the **Data Exchange Definition** FastTab, fill in the fields as described in the following table.

    | Field | Description |
    |-------|-------------|
    | Document Type | Specify the document type that uses data exchange to import and export the data. Examples include **Sales Invoice**, **Sales Credit memo**, and **Purchase Invoice**. |
    | Import Data Exchange Def. Code | Specify the data exchange code that's used to import the data. Use this field only to receive a document in the purchase process. |
    | Export Data Exchange Def. Code | Specify the data exchange code that's used to export the data. Use this field only to deliver documents in the sales process. |

> [!NOTE]
> There are data exchange definitions for the PEPPOL format that are related to sales and purchase documents. However, you likely can't use these definitions as is. They're all W1 formats that are provided to show how to use this feature. We recommend that you test the existing PEPPOL format before you start to use them. It's possible that using a specific localization reveals more formats, as some can be country/region-specific.
>
> If you configured the **Data Exchange Definition** format in your localization, you can add a line for the document types that you need. Add lines that match the default data exchange example for the W1 PEPPOL format. However, first select the **Document Type** option for each line that you need. For each data type, select the **Import Data Exchange Def. Code** or **Export Data Exchange Def. Code** value that you want to use.
>
> If you don't use the **Data Exchange Definition** format, you can create and configure formats by using the [interface](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments). Adjust the information on the **Export Mapping** and **Import Mapping** lines, where you can find the tables and fields to configure transformation rules. In this case, you must add a new option for your format in the **Document Format** field.  

5. If you selected **Data Exchange** in the **Document Format** field on the **General** FastTab, on the **Data Exchange Definition** FastTab, fill in the fields as described in the following table.

   | Field | Description |
   |-------|-------------|
   | Document Type | Specify the document type that uses data exchange to import and export the data. Examples include **Sales Invoice**, **Sales Credit memo**, and **Purchase Invoice**. |
   | Import Data Exchange Def. Code | Specify the data exchange code that's used to import the data. Use this field only to receive a document in the purchase process. |
   | Export Data Exchange Def. Code | Specify the data exchange code that's used to export the data. Use this field only to deliver documents in the sales process. |

   > [!NOTE]
   > There are data exchange definitions for the PEPPOL format that are related to sales and purchase documents. However, you likely can't use these definitions as is. They're generic formats that are provided to show how to use this feature. We recommend that you test the existing formats before you start to use them. It's possible that using a specific localization reveals more formats because some can be specific to a country/region.
   >
   > If you configured the **Data Exchange Definition** format in your localization, you can add a line for the document types that you need. Add lines that match the default data exchange example for the W1 PEPPOL format. However, first select the **Document Type** option for each line that you need. For each data type, select the **Import Data Exchange Def. Code** or **Export Data Exchange Def. Code** value that you want to use.
   >
   > If you don't use the **Data Exchange Definition** format, you can create and configure formats by using the [interface](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments). Adjust the information on the **Export Mapping** and **Import Mapping** lines, where you can find the tables and fields to configure transformation rules. In this case, you must add a new option for your format in the **Document Format** field.

## Other configuration options

After you set up the basics for the e-document service, you can add more advanced options:

- **Set up service integration** - Configure authentication and connection settings for your integration connector. This option is only available when integration connectors are installed.
- **Configure documents to export** - Set up the document types the framework exports using this service.
- **Export mapping setup** - Configure simple value mappings for export processes.
- **Import mapping setup** - Configure simple value mappings for import processes.
- **Receive** - Manually trigger the receipt of new e-documents from the integration service.

### Supported document types

The types of documents you can use is based on your selection in the **Document Format** field on the **E-Document Service** page. To explore the types of documents that a document format supports, select the format, and then choose the **Configure documents to export** action. The **E-Document Service Supported Source Document Types** page opens, and the **Source Document Type** field shows the types of documents for the document format. Only use types of documents that the document format supports.

## Set up a document sending profile

You need to set up a preferred method of sending sales documents for each customer. On the **Document Sending Profiles** page, you can set up sending profiles and then select the one to use in the **Document Sending Profile** field on a customer card page. You can select the **Default** checkbox to specify that a document sending profile is the profile for all customers for which a profile isn't specified in the **Document Sending Profile** field.

This feature is used to set up electronic invoicing automation. If you're using [legacy e-invoices](sales-how-to-send-electronic-documents.md) and want to enable the **E-Document** framework, the process is slightly different. When you choose **Post and Send** on a sales document, the **Post and Send Confirmation** dialog shows the sending profile in use. The profile is either the profile set up for the customer or the default profile for all customers.

However, to enable the new **E-Document** framework, you must configure the **Document Sending Profile** accordingly. To set up a document sending profile, follow these steps.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Document Sending Profile**, and then select the related link.
2. On the **Document Sending Profiles** page, select **New**.
3. On the **General** FastTab, fill in the required fields.
4. On the **Sending Options** FastTab, set the **Printer**, **Email**, and **Disk** fields to **No**. Enabling any of these options prevent you from using the **E-Document** framework, limiting you to the legacy e-invoicing functionality instead.
5. On the same FastTab, fill in the fields as described in the following table.

   | Field | Description | E-Document Framework Usage |
   |-------|-------------|----------------------------|
   | Printer | Specify whether to print the document. | Can be used together with e-document options. |
   | Email | Specify whether to email the document. | Can be used together with e-document options to send e-documents as email attachments. |
   | E-Mail Attachment | Specify what to attach to the email when emailing is enabled. Options include **PDF**, **E-Document**, and **PDF & E-Document**. | **E-Document** sends only the electronic file format. **PDF & E-Document** sends both the PDF report and the electronic file. |
   | Disk | Specify whether to save the document to disk. | Can be used together with e-document options. |
   | Electronic Document | Specify whether the document is sent as an e-document. Choose **Extended E-Document Service Flow** to use the E-Document framework. | You must choose **Extended E-Document Service Flow** to use the E-Document framework. |
   | E-Document Workflow | Specify the e-document workflow that's used to send documents. This field is required when **Extended E-Document Service Flow** is selected and must be an enabled workflow. | Required field when using the E-Document framework. |

   > [!NOTE]
   > When you select **E-Document** or **PDF & E-Document** in the **E-Mail Attachment** field, you must set the **Electronic Document** field to **Extended E-Document Service Flow** and specify an **E-Document Workflow**. The specified workflow must be enabled.

   > [!NOTE]
   > The **E-Document Workflow** field is available only when **Extended E-Document Service Flow** is selected in the **Electronic Document** field. Similarly, to prevent conflicts, certain format-related fields are hidden when you use e-document email attachments.

## Sending options combinations

The E-Document framework supports several options for sending documents:

- **Service-based sending**: Use **Extended E-Document Service Flow** with an **E-Document Workflow** to send documents through configured service integrations.
- **Email-based sending**: Enable **Email** and select **E-Document** or **PDF & E-Document** as the attachment type to send e-documents via email. Email-based sending relies on the e-document workflow to run in order to export the e-document. To use this option, you must fill in the **E-Document Workflow** field.
- **Combined sending**: Use both service-based and email-based sending together to send through a service integration and email the document simultaneously.

## Creating e-documents from posted documents

After you post documents, you can create or view e-documents from the pages that show posted documents. For example, the **Posted Sales Invoice** page.

1. Open the posted document.
1. To manually create an e-document from the posted document, choose **Create**.
1. To view the existing e-document, choose **Open**.

This feature is useful when you need to send documents electronically after they were originally posted without e-document processing.

## Set up the workflow

To set up a workflow for e-documents, follow these steps.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Workflow Templates**, and then select the related link.
2. If you can't find **E-Document Workflow Templates** on the **Workflow Templates** page, select **Reset Microsoft Templates**. **E-Document Workflow Templates** should then appear. Close the page.
3. [!INCLUDE[open-search](includes/open-search.md)], enter **Workflows**, and then select the related link.
4. Choose the **New Workflow from Template** action to select a template for the e-documents process. The available templates are **Send to one service** and **Send to multiple services**.
5. Select **OK** to finish the workflow setup.
6. In the **Then Response** field, select **Send E-Document using setup** to configure the workflow responses.
7. Select the E-Document Service that you created as an option, choose **OK**, and then enable the workflow.

> [!NOTE]
> You can create your own workflow for e-documents without using predefined workflow templates. If you have more services, you can use different workflows.

To use more workflows, configure them through the document sending profiles for different customers. When you set up the workflow, specify the document sending profile in the **On Condition** column on the **Workflow Steps** FastTab, because you can't have two services that use the same document sending profile in workflows.

When you configure your workflow on the **Workflows** page, point to the **On Condition** field on the **Workflow Steps** FastTab. On the **Event Conditions** page, in the **Filter** field, select the document sending profile that you want to use.

## Set up a retention policy for e-documents

E-documents can be subject to local legislation that specifies the period for which you must keep e-documents. To manage that, administrators can define retention policies that control how often [!INCLUDE [prod_short](includes/prod_short.md)] deletes records. To learn more about retention policies, go to [Define Retention Policies](admin-data-retention-policies.md).

To set up retention policies for e-documents, follow these steps.

1. On the **E-Document Services** page, choose the **Retention Policy** action.
2. When the action is completed, select one of the following retention policies to set up:

    - E-Document Log
    - E-Document Integration Log
    - E-Document Mapping Log
    - E-Document Data Storage

## E-Documents demo data  

To provide easier ways to test and demonstrate e-documents, Microsoft offers a demo module. 

> [!NOTE]
> From [!INCLUDE [prod_short](includes/prod_short.md)] version 24.0, you can set up demo data for E-Documents.

To enable the module, follow these steps:  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Contoso Demo Tool**, and then select the related link.  
2. Before you enable the **E-Document Contoso Module**, you must first enable the  **Common Module** and **Warehouse Module**.
3. After you enable the modules, select the **E-Documents Contoso Module**, and then choose the **Generate** action.
4. Follow the steps.  
5. Close the page.

After you enable the module, you have demo items, six electronic documents (based on Peppol BIS 3), and configured **E-Document Services** with created workflows.  

## Related information

[How to use e-documents in sales](finance-how-use-edocuments.md)  
[How to use e-documents in purchase](finance-how-use-edocuments-purchase.md)  
[How to extend e-documents in Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments)  
[Financial Management](finance.md)  
[Invoice Sales](sales-how-invoice-sales.md)  
[Record Purchases with Purchase Invoices and Orders](purchasing-how-record-purchases.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
