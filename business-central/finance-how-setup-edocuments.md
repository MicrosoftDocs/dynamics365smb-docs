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
 > It is important to understand that E-Documents Core module is a framework. That means, there is no **Document Format** and **Service Integration** by default. These details are part of localization apps as both are specific to local requirements.  

 > [!NOTE]
 > From version 23.1 it is planned to add standard PEPPOL document format as a global format in the **Document Format** option.   

The first step in configuring E-Documents is setting up the **E-Documents Service**, where you need to configure the complete behavior of your system related to electronic document communication.   

## E-Document Service Setup  

To set up the **E-Document Service**: 

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then choose the related link.  
2. Click **New** and the **E-Document Service** page will open.  
3. On the **General** FastTab, configure the fields described in the following table: 

    |Field  |Description  |Comment |  
    |---------|---------|--------|
    |Code |Specifies the code of the electronic export setup. | |   
    |Description |Specifies the description of the electronic export setup. | |  
    |Document Format |Specifies the export format of the electronic export setup. |There is no option in this field in W1 by default. | 
    |Service Integration |Specifies integration code for the electronic export setup. |In W1 there is only **No integration** option. |
    |Use Batch Processing |Specifies if service uses batch processing for export. | |  

4. On the **Imported Parameters** FastTab, configure the fields described in the following table: 

    |Field  |Description  | 
    |---------|---------|
    |Validate Receiving Company |Specifies if receiving company information must be validated during the import. | 
    |Resolve Unit Of Measure |Specifies if unit of measure shall be resolved during the import. |  
    |Lookup Item Reference |Specifies if an item shall be searched by the item reference during the import. | 
    |Lookup Item GTIN |Specifies if an item shall be searched by GTIN during the import. |  
    |Lookup Account Mapping |Specifies if an account shall be searched in Account Mapping by the incoming text during the import. | 
    |Validate Line Discount |Specifies if a line discount shall be validated during the import. |  
    |Apply Invoice Discount |Specifies if an invoice discount shall be applied during the import. | 
    |Verify Totals |Specifies if an invoice total shall be verified during the import. |  
    |Update Order |Specifies if the corresponding purchase order must be updated. |   
    |Create Journal Lines |Specifies if journal line must be created instead of purchase document. Only in a case you want to use Journals as destionation for your invoices. |  
    |General Journal Template Name |Specifies the General Journal Template Name used for journal line creation. Only in a case you want to use Journals as destionation for your invoices. | 
    |General Journal Batch Name |Specifies the General Journal Batch Name used for journal line creation. Only in a case you want to use Journals as destionation for your invoices. | 
    |Auto Import |Specifies whether to automatically import documents from the service. | 
    |Batch Start Time |Specifies import jobs starting time. |    
    |Minutes between runs |Specifies the number of minutes between running import job. |  

If you have configured **Data Exchange Definition** format in your localization, you can add as many lines as document types you need, but first choosing the **Document Type** option for each line you need. Further,	for each of **Data Type** you should select the **Import Data Exchange Def. Code** or the **Export Data Exchange Def. Code** you want to use.  

Eventually, if you don’t use **Data Exchange Definition**, you can configure formats through the **Export Mapping** and **Import Mapping** lines, where you can locate tables and fields they want to use, and configure **Transformation Rules** if applicable.

## Document Sending Profile Setup  

You can set each customer up with a preferred method of sending sales documents, so that you do not have to select a sending option every time you choose the **Post and Send** action. On the **Document Sending Profiles** page, you can set up different sending profiles that you can select from in the **Document Sending Profile** field on a customer card. You can select the **Default** check box to specify that the document sending profile is the default profile for all customers, except for customers where the **Document Sending Profile** field is filled with another sending profile.  

This functionality is used for setting up electronic invoicing automation. When you choose the **Post and Send** action on a sales document, the **Post and Send Confirmation** dialog box shows the sending profile used, either the one set up for the customer or the default for all customers. 

To set up a **Document Sending Profile**:   

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Document Sending Profile**, and then choose the related link.  
2. On the **Document Sending Profiles** page, choose the **New** action.   
3. Fill in the fields on the **General** FastTab as necessary. 
4. On the **Sending Options** FastTab, set up **Electronic Document** and **Electronic Document Service Flow Code** fields described in the following table:  

    |Field  |Description  | 
    |---------|---------|
    |Electronic Document |Specifies if the document is sent as an electronic document that the customer can import into their system when you choose the **Post and Send** button. To use this option, you must also fill in the **Format** or **Electronic Document Service Flow Code** field. Alternatively, the file can be saved to disk. |
    |Format |Specifies which format to use for electronic document sending. You must fill this field if you select the **Through Document Exchange** option in the **Electronic Document** field. |   
    |Electronic Document Service Flow Code |Specifies **Electronic Service Flow** that is used for sending documents. You must fill this field if you select the **Extended E-Document Service Flow** option in the Electronic Document field. |  

 > [!NOTE]
 > If you use **Extended E-Document Service Flow** option in the **Electronic Document** field, you must have previously configured Workflow for you electronic documents. 

## Workflow Setup

To set up the workflow for using in electrnic documents functionality: 

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Workflow Templates**, and then choose the related link.  
2. If you cannot find **E-Document Workflow Templates** on the **Workflow Templates** page click the **Reset Microsoft Templates** action, and new **E-Document Workflow Templates** will appear.
3. Close the page.
4. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Workflows**, and then choose the related link.  
5. Run the **New Workflow from Template** action to choose one template for E-document process (**Send to one service** or **Send to multiple services**).
6. Click **OK** to finish the workflow set up.
7. Click on **Send E-Document using setup** in the **Then Response** field to configure **Workflow Responses**.  
8. Choose previously created **E-Document Service** as an option. Click **OK** and enable the workflow.

 > [!NOTE]
 > You can create your own **Workflow** for E-Documents without using predefined **Workflow Templates**. If you have more services you can use different workflows.

## Retention Policy for E-Documents

Electronic documents can be a subject of different local legislations related with the peirod for keeping them. Because of that we add **Retention Policy** setup for all important information related with electronic documents. Administrators can define retention policies to specify how frequently they want Business Central to delete outdated records related with electronic documents. More inforation about **Retention Policy** here: [Define Retention Policies
](admin-data-retention-policies.md).

To set up electronic documents related retention policies you need to run the **Retention Policy** action on the **E-Document Services** page. Once you run this action, you can choose one of the following retention policies to set up: 
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
