---
title: Set Up E-Documents
description: Learn how to set up E-Documents functionality.
author: altotovi
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: electronic document, electronic invoice, e-document, e-invoice
ms.search.form: 359, 360, 6103, 6133
ms.date: 10/03/2023
ms.author: altotovi
---

# Set up E-Documents   

 > [!IMPORTANT]
 > The E-Documents core module is a framework. By default, there is no **Document Format** or **Service Integration**. These details are part of localization apps as they are both are specific to local requirements.  

 > [!NOTE]
 > Starting in version 23.1, a standard PEPPOL document format is added as a global format in the **Document Format** option.   

The first step to configure E-Documents is to set up the **E-Documents Service** where you configure the complete behavior of your system related to electronic document communication.   

## E-Document Service Setup  

Complete the following steps to set up the **E-Document Service**.

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then select the related link.  
2. Select **New**, and on the **E-Document Service** page, on the **General** FastTab, configure the fields as described in the following table.

   | Field   | Description  | 
   |---------|--------------|
   | Code    | Select the electronic export setup code. |   
   | Description | Enter a brief description of the electronic export setup. |  
   | Document Format | The export format of the electronic export setup. <br> By default, there's no option in this field in Wave 1. | 
   | Service Integration | Select the integration code for the electronic export setup. In W1 the only option is **No integration**. |
   | Use Batch Processing | Specify if service uses batch processing for export. |  

4. On the **Imported Parameters** FastTab, configure the fields described in the following table.

    | Field  | Description  | 
    |--------|--------------|
    | Validate Receiving Company | Specify if the receiving company information must be validated during import. | 
    | Resolve Unit Of Measure | Specify if the unit of measure should be resolved during import. |  
    | Lookup Item Reference | Specify if an item should be searched by the item reference during import. | 
    | Lookup Item GTIN | Specify if an item should be searched by GTIN during import. |  
    | Lookup Account Mapping | Specify if an account should be searched in **Account Mapping** by the incoming text during import. | 
    | Validate Line Discount | Specify if a line discount should be validated during import. |  
    | Apply Invoice Discount | Specify if an invoice discount should be applied during import. | 
    | Verify Totals | Specify if an invoice total should be verified during import. |  
    | Update Order | Specify if the corresponding purchase order must be updated. |   
    | Create Journal Lines | Specify if a journal line must be created instead of a purchase document. Select this option when you want to use Journals as a destination for your invoices. |  
    | General Journal Template Name | Specify the General Journal Template Name used for journal line creation. This field is applicable when you want to use Journals as destination for your invoices. | 
    | General Journal Batch Name | Specify the General Journal Batch Name used for journal line creation. This field is applicable when you want to use Journals as destination for your invoices. | 
    | Auto Import | Specify whether to automatically import documents from the service. | 
    | Batch Start Time | Specify the start time for import jobs. |    
    | Minutes between runs | Specify the number of minutes between running import jobs. |  

If you have configured the **Data Exchange Definition** format in your localization, you can add as many lines as document types you need. However you must first choose the **Document Type** option for each line you need. For each of **Data Type**, select the **Import Data Exchange Def. Code** or the **Export Data Exchange Def. Code** you want to use.  

Eventually, if you don’t use **Data Exchange Definition**, you can configure formats through the **Export Mapping** and **Import Mapping** lines, where you can locate tables and fields to use, and configure **Transformation Rules** if applicable.

## Document Sending Profile Setup  

You can a preferred method of sending sales documents for each customer, so that you don't have to select a sending option every time you choose the **Post and Send** action. On the **Document Sending Profiles** page, you can set up different sending profiles that you can select from in the **Document Sending Profile** field on a customer card. You can select the **Default** check box to specify that the document sending profile is the default profile for all customers, except for customers where the **Document Sending Profile** field has a different sending profile.  

This functionality is used to set up electronic invoicing automation. When you select **Post and Send** on a sales document, the **Post and Send Confirmation** dialog box shows the sending profile used, either the one set up for the customer or the default for all customers. 

Complete the following steps to set up a **Document Sending Profile**.

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Document Sending Profile**, and then select the related link.  
2. On the **Document Sending Profiles** page, select **New**.   
3. On the **General** FastTab, enter any required field information. 
4. On the **Sending Options** FastTab, select a value in the set up **Electronic Document**, **Format**, and **Electronic Document Service Flow Code** fields as described in the following table.  

    | Field  | Description  | 
    |---------|---------|
    | Electronic Document | Specify if the document is sent as an electronic document that the customer can import into their system when you select **Post and Send**. To use this option, you must also fill in the **Format** or **Electronic Document Service Flow Code** fields. Alternatively, the file can be saved to disk. |
    | Format | Specify the format to use to send an electronic document. This field is required if you select **Through Document Exchange** in the **Electronic Document** field. |   
    | Electronic Document Service Flow Code | Specify the **Electronic Service Flow** that is used to send documents. This field is required if you select **Extended E-Document Service Flow** in the **Electronic Document** field. |  

 > [!NOTE]
 > If you select **Extended E-Document Service Flow** in the **Electronic Document** field, you must already have the Workflow configured for you electronic documents. 

## Workflow Setup

To set up the workflow for using in electrnic documents functionality: 

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Workflow Templates**, and then select the related link.  
2. If you can't find **E-Document Workflow Templates** on the **Workflow Templates** page, select **Reset Microsoft Templates**, and a new **E-Document Workflow Templates** appears. Close the page.
3. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Workflows**, and then select the related link.  
4. Run the **New Workflow from Template** action to select a template for the E-document process. The available templates are **Send to one service** or **Send to multiple services**.
5. Select **OK** to finish the workflow set up.
6. In the **Then Response** field, select **Send E-Document using setup** to configure the **Workflow Responses**.  
7. Select the **E-Document Service** you created as an option and then select **OK** and enable the workflow.

 > [!NOTE]
 > You can create your own **Workflow** for E-Documents without using predefined **Workflow Templates**. If you have more services you can use different workflows.

## Retention Policy for E-Documents

Electronic documents can be a subject of different local legislations related to the period in which they are kept. Because of that, we added a **Retention Policy** setup for all important information related to electronic documents. Administrators can define retention policies that specify how frequently they want Dynamics 365 Business Central to delete outdated records that are related to electronic documents. To learn more about the Retention Policy, see [Define Retention Policies](admin-data-retention-policies.md).

To set up electronic documents related retention policies, select **Retention Policy** on the **E-Document Services** page to run the action. After the action is complete, select one of the following retention policies to set up: 
- E-Document Log
- E-Document Integration Log
- E-Document Mapping Log
- E-Document Data Storage


## See also

[How to use e-documents in Business Central](finance-how-use-edocuments.md) 
[How to extend e-documents in Business Central](finance-how-extend-edocuments.md)  
[Financial Management](finance.md)  
[Invoice Sales](sales-how-invoice-sales.md) 
[Record Purchases with Purchase Invoices and Orders](purchasing-how-record-purchases.md)
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
