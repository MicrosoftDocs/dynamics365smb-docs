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

> [!IMPORTANT]
> The E-Documents core module is a framework. By default, there's no **Service Integration** field. If you find the **Document Format** options by default, remember that they're offered as examples. Localization apps must provide format detail because they're specific to local requirements.

> [!NOTE]
> A standard PEPPOL document format is a global format in the **Document Format** field. Keep in mind that you probably can't use this format as is. It's a W1 format that Microsoft provides to show how to use this feature. We recommend that you test the existing PEPPOL format before you start to use this format.

The first step to configure electronic documents (e-documents) is to set up the E-Documents Service for e-document communication.

## Set up an e-document service

To set up an e-document service, follow these steps.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **E-Document Services**, and then select the related link.
2. Select **New**, and then, on the **E-Document Service** page, on the **General** FastTab, configure the fields as described in the following table.

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

5. If you selected **Data Exchange** in the **Document Format** field on the **General** FastTab, on the **Data Exchange Definition** FastTab, fill in the fields as described in the following table.

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

5. On the **Exporting** FastTab, fill in the fields as described in the following table:

   |Field  |Description  |
   |---------|---------|
   | Batch Exporting | Specify whether the service uses batch processing to export e-documents. |
   | Embed document PDF to export| Specify whether to embed a PDF version of the e-document in the e-document file when you export.|

   > [!NOTE]
   > The **Embed document PDF to export** option can make life a little easier. When you post a document, [!INCLUDE [prod_short](includes/prod_short.md)] creates a PDF file and embeds it as a PDF attachment in the e-document. The PDF is a human-readable version that's easier to understand than the full XML of the PEPPOL format.

### Supported document types

Support for document types is based on the **Document Format**. To check which document types are supported, on the **E-Document Services** page, choose the **Supported Document Types** action. The **E-Document Service Supported Source Document Types** opens. In the **Source Document Type** column, you can choose different document types for the format you're planning to use. Only use the document type if that document is selected.

## Set up a document sending profile

You need to set up a preferred method of sending sales documents for each customer. On the **Document Sending Profiles** page, you can set up sending profiles and then select the one to use in the **Document Sending Profile** field on a customer card. You can select the **Default** checkbox to specify that a document sending profile is the profile for all customers for which a profile isn't specified in the **Document Sending Profile** field.

This feature is used to set up electronic invoicing automation. If you're using [legacy e-invoices](sales-how-to-send-electronic-documents.md) before enabling the **E-Document** framework, the process is slightly different. When you choose **Post and Send** on a sales document, the **Post and Send Confirmation** dialog shows the sending profile in use. The profile is either the profile set up for the customer or the default profile for all customers.

However, to enable the new **E-Document** framework, you need to configure the **Document Sending Profile** accordingly. To set up a document sending profile, follow these steps.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Document Sending Profile**, and then select the related link.
2. On the **Document Sending Profiles** page, select **New**.
3. On the **General** FastTab, fill in the required fields.
4. On the **Sending Options** FastTab, set the **Printer**, **Email**, and **Disk** fields to **No**. Enabling any of these options prevent you from using the **E-Document** framework, limiting you to the legacy e-invoicing functionality instead.
5. On the same FastTab fill in the fields as described in the following table.

    | Field | Description | Set up options |
    |-------|-------------|----------------|
    | Electronic Document | Specify whether the document is sent as an e-document that the customer can import into their system. This option must be set to the **Extended E-Document Service Flow** to use E-Document framework. To use this option, you must also set the **Format** or **Electronic Document Service Flow Code** field. Alternatively, you can save the file to your computer. | Must choose **Extended E-Document Service Flow**. |
    | Format | Specify the format to use to send an e-document. This field is required if you select **Through Document Exchange** in the **Electronic Document** field. | Don't use this setup for E-Document framework because it's part of [legacy e-invoicing](sales-how-to-send-electronic-documents.md). |
    | Electronic Document Service Flow Code | Specify the electronic service flow that's used to send documents. This field is required if you select **Extended E-Document Service Flow** in the **Electronic Document** field. | You must set up it if you selected the **Extended E-Document Service Flow** option. |

    > [!NOTE]
    > If you select **Extended E-Document Service Flow** in the **Electronic Document** field, you must already have the workflow configured for your e-documents.

    > [!IMPORTANT]
    > The [legacy e-invoicing system](sales-how-to-send-electronic-documents.md) is still in use, which allows users to configure the **Electronic Document** field as **Through Document Exchange Service**. In this setup, the **Printer**, **Email**, and **Disk** fields are applicable and typically enabled. However, this configuration isn't supported in any of Microsoft’s e-invoicing localizations and is planned for deprecation.
    > 
    > To use the new **E-Document** framework, you must configure the **Electronic Document** field as **Extended E-Document Service Flow** and specify a value in the **Electronic Document Service Flow Code** field. 

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

> [!NOTE]
> From [!INCLUDE [prod_short](includes/prod_short.md)] version 24.0, you can set up demo data for E-Documents.

To provide easier ways to test and demonstrate e-documents, Microsoft offers a demo module. To enable the module, follow these steps:  

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
