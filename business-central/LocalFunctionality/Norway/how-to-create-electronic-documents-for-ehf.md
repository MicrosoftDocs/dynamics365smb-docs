---
title: Create Electronic Documents for EHF
description: Learn about the legacy Norwegian EHF workflow for posting sales invoices and creating electronic documents with customer references and invoicing details.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: create electronic documents, create e-documents, EHF, post sales invoice, create electronic invoice, create e-invoice, Norwegian version
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Create electronic documents for EHF

> [!NOTE]
> This article describes the older EHF invoicing workflow. For new electronic invoicing setups, use the E-Documents framework instead. Learn more in [Set up e-documents](../../finance-how-setup-edocuments.md) and [Electronic invoicing in Norway](ehf-electronic-invoicing-in-norway.md#new-e-documents-framework).

When you sell goods or services to a customer in the public sector, you must submit documents electronically. In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can create electronic documents for invoices, credit memos, reminders, and finance charge memos. Before you can create the electronic documents, you must have set up file locations and information about the customers. Learn more in [Set Up EHF](how-to-set-up-ehf.md) and [Set Up Customers for EHF](how-to-set-up-customers-for-ehf.md).

Electronic documents can only be created after a document has been posted or issued. The following procedures describe how to post a sales invoice with the required information and then create an electronic sales invoice, but the same steps also apply to sales credit memos, reminders, finance charge memos, service invoices, and service credit memos.  

> [!NOTE]  
> The sum of lines in an exported electronic document doesn't reflect invoice rounding, even if it's enabled. Instead, [!INCLUDE[prod_short](../../includes/prod_short.md)] sums the lines without rounding.  

## Post a sales invoice  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Sales Invoices**, and then choose the related link.  
1. Select the sales invoice that you want to post, and then choose the **Edit** action.  
1. On the **General** FastTab, make sure that the following fields contain values:  

    - **External Document No.**  
    - **Your Reference**  

    The **External Document No.** field contains the document number that the customer provided.  

1. On the **Invoicing** FastTab, make sure that the following fields have values:  

    - **GLN No.**  
    - **Account Code**  
    - **Bill-to Customer**  
    - **Shipment Date**  

    Select the **E-Invoice** checkbox.  

    The default value of the **Shipment Date** field is the posting date of the document.  

    > [!NOTE]  
    > For reminders and finance charge memos, the **GLN No.**, **Account Code**, and **E-Invoice** fields are on the **Posting** FastTab.  

1. Choose the **Post** action to post the invoice.  

## Create an electronic sales invoice  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Posted Sales Invoices**, and then choose the related link.  
1. Select the relevant sales invoice.  
1. Choose the **Create Electronic Invoice** action.  

   > [!IMPORTANT]  
   > The **E-Invoice** checkbox must be selected on the invoice in order to create an electronic invoice.  

1. Optionally, in the **Create Electronic Invoices** batch job page, set additional filters.  
1. Choose the **OK** button.  

An XML file is created and stored at the location that was defined on the **Sales & Receivables Setup** page. You can now submit the document to the customer.  

## Related information

[EHF Electronic Invoicing in Norway](ehf-electronic-invoicing-in-norway.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
