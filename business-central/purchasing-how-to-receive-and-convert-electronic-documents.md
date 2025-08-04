---
title: Receive and convert electronic documents
description: This article describes how to receive electronic documents directly from trading partners or from an OCR service.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.search.form: 189, 190, 191 
ms.date: 03/20/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Receive and convert electronic documents

> [!NOTE]
> The content in this article is only applicable for versions of Dynamics 365 Business Central that were released before 2023 release wave 2. In 2023 release wave 2, new functionality for E-Documents is included. To learn more, see [Set up e-documents](finance-how-setup-edocuments.md). 


The generic version of [!INCLUDE[prod_short](includes/prod_short.md)] supports receiving electronic invoices and credit memos in the PEPPOL format, which is supported by the largest providers of document exchange services. To receive an invoice from a vendor as an electronic PEPPOL document, you process the document in the Incoming Documents page to convert it to a purchase invoice or general journal line in [!INCLUDE[prod_short](includes/prod_short.md)].

In addition to receiving electronic documents directly from trading partners, you can receive electronic documents from an OCR service that has turned your PDF or image files into electronic documents.  

Before you can receive electronic documents through the document exchange service, you must set up various master data, such as company information, vendors, items, and units of measure. These are used to identify the business partners and items when converting data in elements in the incoming document file to fields in [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see [Set Up a Document Exchange Service](across-how-to-set-up-a-document-exchange-service.md).  

Before you can receive electronic documents through the OCR service, you must set up and enable the preconfigured service connection. For more information, see [Set Up Incoming Documents](across-how-setup-income-documents.md).  

The traffic of electronic documents in and out of [!INCLUDE[prod_short](includes/prod_short.md)] is managed by the Job Queue feature. Before you can receive electronic documents, the relevant job queue must be started.  

You can either start the conversion of electronic documents manually, as described in this procedure, or you can enable a workflow to convert electronic documents automatically when they're received. The generic version of [!INCLUDE[prod_short](includes/prod_short.md)] includes a workflow template, *From Incoming Electronic through OCR to Open Purchase Invoice Workflow*, which is ready to be copied to a workflow and enabled. For more information, see [Workflow](across-workflow.md).  

> [!NOTE]  
> When you convert electronic documents received from the OCR service to documents or journal lines in [!INCLUDE[prod_short](includes/prod_short.md)], multiple lines on the source document will be summed on one line. The single line will be of type G/L Account and the **Description** and (G/L account) **No.** fields will be empty. The value in the **Amount** field will equal the total amount excluding VAT of all lines in the source document.  
>
> To make sure that the **Description** and **No.** fields are filled, you can choose the **Map Text to Account** button on the **Incoming Documents** page to define that a certain invoice text is always mapped to a certain debit or credit account in the general ledger. Going forward, the **Description** field on document or journal lines created from an electronic document for that vendor or customer will be filled with the text in question and the (G/L account) **No.** field with the account in question.  
>
> Instead of mapping to a G/L account, you can also map to a bank account. This is practical, for example, for electronic documents for expenses that are already paid where you want to create a general journal line that is ready to post to a bank account.  

The following procedure describes how to receive a vendor invoice and convert it to a purchase invoice in [!INCLUDE[prod_short](includes/prod_short.md)]. The procedure is the same when you convert a vendor invoice to a general journal line.  

### To receive and convert an electronic invoice to a purchase invoice

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Incoming Documents**, and then choose the related link.  

2. Select the line for the incoming document record that represents a new incoming electronic invoice, and then choose the **Edit** action.  

    On the **Incoming Document Card** page, the related XML file is attached, and most of the fields are prefilled with information from the electronic invoice. For more information, see [Create Incoming Document Records](across-how-create-income-document-records.md).  

3. In the **Data Exchange Type** field, choose **PEPPOL - Invoice** or **OCR – Invoice** depending on the source of the electronic document.  

4. To map text on the vendor invoice to a specific debit account, on the **Actions** tab, in the **General** group, choose **Map Text to Account**, and then fill the **Text-to-Account Mapping Worksheet** page.  

5. Choose the **Create Document** action.  

    A purchase invoice will be created in [!INCLUDE[prod_short](includes/prod_short.md)] based on the information in the electronic document.  

    Any validation errors, typically related to wrong or missing master data in [!INCLUDE[prod_short](includes/prod_short.md)] will be shown on the **Error Messages** FastTab.  

## Related information

[Managing Payables](payables-manage-payables.md)  
[Incoming Documents](across-income-documents.md)  
[Set Up Electronic Document Sending and Receiving](across-how-to-set-up-electronic-document-sending-and-receiving.md)  
[Exchanging Data Electronically](across-data-exchange.md)   
[General Business Functionality](ui-across-business-areas.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
