---
title: Set up e-documents
description: Learn how to set up e-documents functionality.
author: altotovi
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: electronic document, electronic invoice, e-document, e-invoice
ms.search.form: 359, 360, 6103, 6133
ms.date: 10/05/2023
ms.author: altotovi
---

# Set up e-documents

> [!IMPORTANT]
> The E-Documents core module is a framework. By default, there's no **Service Integration** field. If you find the **Document Format** options by default, be aware that they're offered as an example, and that localization must provide a detailed format. These details are part of localization apps, because they're specific to local requirements.

> [!NOTE]
> As of version 23.2, a standard PEPPOL document format is added as a global format in the **Document Format** field. Keep in mind that you probably can't use this format as is. It's a W1 format that's provided to show how to use this feature. We recommend that you test the existing PEPPOL format before you start to use this format.

The first step in the configuration of electronic documents (e-documents) is to set up the E-Documents Service where you configure the complete behavior of your system as it's related to e-document communication.

## Set up the E-Document Service

Follow these steps to set up the E-Document Service.

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then select the related link.
2. Select **New**, and then, on the **E-Document Service** page, on the **General** FastTab, configure the fields as described in the following table.

    | Field | Description |
    |-------|-------------|
    | Code | Select the electronic export setup code. |
    | Description | Enter a brief description of the electronic export setup. |
    | Document Format | <p>The export format of the electronic export setup.</p><p>By default, there are two options in this field. You can select **PEPPOL BIS 3** as a generic code-based format or **Data Exchange** when you must set up pre-documents of specific formats on the **Data Exchange Definition** FastTab.</p> |
    | Service Integration | Select the integration code for the electronic export setup. In Wave 1, the only option is **No integration**. |
    | Use Batch Processing | Specify whether the service uses batch processing for export. |

3. On the **Imported Parameters** FastTab, configure the fields as described in the following table.

    | Field | Description |
    |-------|-------------|
    | Validate Receiving Company | Specify whether the receiving company information must be validated during import. |
    | Resolve Unit Of Measure | Specify whether the unit of measure should be resolved during import. |
    | Lookup Item Reference | Specify whether an item should be searched by the item reference during import. |
    | Lookup Item GTIN | Specify whether an item should be searched by Global Trade Item Number (GTIN) during import. |
    | Lookup Account Mapping | Specify whether an account should be searched in **Account Mapping** by the incoming text during import. |
    | Validate Line Discount | Specify whether a line discount should be validated during import. |
    | Apply Invoice Discount | Specify whether an invoice discount should be applied during import. |
    | Verify Totals | Specify whether an invoice total should be verified during import. |
    | Update Order | Specify whether the corresponding purchase order must be updated. |
    | Create Journal Lines | Specify whether a journal line must be created instead of a purchase document. Select this option when you want to use journals as a destination for your invoices. |
    | General Journal Template Name | Specify the name of the general journal template that's used for journal line creation. This field is applicable when you want to use journals as a destination for your invoices. |
    | General Journal Batch Name | Specify the name of the general journal batch that's used for journal line creation. This field is applicable when you want to use journals as a destination for your invoices. |
    | Auto Import | Specify whether documents should be automatically imported from the service. |
    | Batch Start Time | Specify the start time for import jobs. |
    | Minutes between runs | Specify the number of minutes between import job runs. |

4. If you selected **Data Exchange** in the **Document Format** field on the **General** FastTab, use the **Data Exchange Definition** FastTab to set the following fields.

    | Field | Description |
    |-------|-------------|
    | Document Type | Specify the document type that uses data exchange to import and export the data. Examples include **Sales Invoice**, **Sales Credit memo**, and **Purchase Invoice**. |
    | Import Data Exchange Def. Code | Specify the data exchange code that's used to import the data. Use this field only to receive a document in the purchase process. |
    | Export Data Exchange Def. Code | Specify the data exchange code that's used to export the data. Use this field only to deliver documents in the sales process. |

> [!NOTE]
> There are prepared data exchange definitions for the PEPPOL format that are related to the standard sales and purchase document. However, you likely can't use these definitions as is. They're all W1 formats that are provided to show how to use this feature. We recommend that you test the existing PEPPOL format before you start to use them.

If you've configured the **Data Exchange Definition** format in your localization, you can add a line for every document type that you need. Add lines that match the default data exchange example for the W1 PEPPOL format. However, first select the **Document Type** option for each line that you need. For each data type, select the **Import Data Exchange Def. Code** or **Export Data Exchange Def. Code** value that you want to use.

If you don't use the **Data Exchange Definition** format, you can create and configure formats by using the [interface](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments). Adjust the information on the **Export Mapping** and **Import Mapping** lines, where you can find the tables and fields to configure transformation rules. In this case, you must add a new option in the **Document Format** field that's related to your format.  

### Supported document types 

Supported document types are based on the chosen **Document Format**. To check which document types are supported, on the **E-Document Service** page, run the **Supported Document Types** action. The **E-Document Service Supported Source Document Types** opens and in the **Source Document Type** column, you can find all the supported document types.  

## Set up a document sending profile

You can set up a preferred method of sending sales documents for each customer. In this way, you don't have to select a sending option every time that you select the **Post and Send** action. On the **Document Sending Profiles** page, you can set up different sending profiles and then select among them in the **Document Sending Profile** field on a customer card. You can select the **Default** checkbox to specify that a document sending profile is the default profile for all customers, except customers where the **Document Sending Profile** field is set to a different sending profile.

This functionality is used to set up electronic invoicing automation. When you select **Post and Send** on a sales document, the **Post and Send Confirmation** dialog box shows the sending profile that's used: either the profile that's set up for the customer or the default profile for all customers.

Follow these steps to set up a document sending profile.

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Document Sending Profile**, and then select the related link.
2. On the **Document Sending Profiles** page, select **New**.
3. On the **General** FastTab, enter any required field information.
4. On the **Sending Options** FastTab, configure the fields as described in the following table.

    | Field | Description |
    |-------|-------------|
    | Electronic Document | Specify whether the document is sent as an e-document that the customer can import into their system when you select **Post and Send**. To use this option, you must also set the **Format** or **Electronic Document Service Flow Code** field. Alternatively, the file can be saved to disk. |
    | Format | Specify the format to use to send an e-document. This field is required if you select **Through Document Exchange** in the **Electronic Document** field. |
    | Electronic Document Service Flow Code | Specify the electronic service flow that's used to send documents. This field is required if you select **Extended E-Document Service Flow** in the **Electronic Document** field. |

    > [!NOTE]
    > If you select **Extended E-Document Service Flow** in the **Electronic Document** field, you must already have the workflow configured for your e-documents.

## Set up the workflow

Follow these steps to set up the workflow that's used in e-document functionality.

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Workflow Templates**, and then select the related link.
2. If you can't find **E-Document Workflow Templates** on the **Workflow Templates** page, select **Reset Microsoft Templates**. **E-Document Workflow Templates** should then appear. Close the page.
3. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Workflows**, and then select the related link.
4. Run the **New Workflow from Template** action to select a template for the e-documents process. The available templates are **Send to one service** and **Send to multiple services**.
5. Select **OK** to finish the workflow setup.
6. In the **Then Response** field, select **Send E-Document using setup** to configure the workflow responses.
7. Select the E-Document Service that you created as an option, select **OK**, and then enable the workflow.

> [!NOTE]
> You can create your own workflow for e-documents without using predefined workflow templates. If you have more services, you can use different workflows.

To use more workflows, configure them through the document sending profiles for different customers. When you set up the workflow, specify the document sending profile in the **On Condition** column on the **Workflow Steps** FastTab, because you can't have two services that use the same document sending profile in workflows.

When you configure your workflow on the **Workflow** page, point to the **On Condition** field on the **Workflow Steps** FastTab. On the **Event Conditions** page, in the **Filter** field, select the document sending profile that you want to use.

## Set up a retention policy for e-documents

E-documents can be a subject of different local legislations that are related to the period that the e-documents are kept for. Therefore, we have added a retention policy setup for all important information that's related to e-documents. Administrators can define retention policies that specify how frequently Dynamics 365 Business Central deletes outdated records that are related to e-documents. To learn more about retention policies, see [Define Retention Policies](admin-data-retention-policies.md).

To set up e-document-related retention policies, follow these steps.

1. On the **E-Document Services** page, run the **Retention Policy** action.
2. When the action is completed, select one of the following retention policies to set up:

    - E-Document Log
    - E-Document Integration Log
    - E-Document Mapping Log
    - E-Document Data Storage

## See also

[How to use e-documents in Business Central](finance-how-use-edocuments.md)  
[How to extend e-documents in Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments)  
[Financial Management](finance.md)  
[Invoice Sales](sales-how-invoice-sales.md)  
[Record Purchases with Purchase Invoices and Orders](purchasing-how-record-purchases.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
