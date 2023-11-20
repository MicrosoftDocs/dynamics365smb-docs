---
title: Set up digital vouchers in Denmark
description: This article explains how to set up and use enforced digital vouchers in Microsoft Dynamics 365 Business Central for Danish localization.
author: altotovi
ms.author: altotovi
ms.reviewer: 
ms.service: dynamics365-business-central
ms.topic: how-to
ms.search.keywords: digital voucher, voucher, attachment, setup, denmark
ms.search.form: 5579, 5582, 5587
ms.date: 11/17/2023
ms.custom: bap-template

---

# Set up digital vouchers  

Administrators can use digital voucher functionality to require documents be attached specific transactions when they are posted. This functionality is a source-driven approach and provides a better audit trail. You can configure various types of enforcement, depending on documents or journal types, for these purposes.  

A *digital voucher* refers to a digital or electronic form of a traditional voucher in accounting. The voucher is a document used to support and authorize financial transactions. In accounting, a voucher typically serves as evidence of an expenditure or receipt of funds. The voucher may include details such as the date of the transaction, a description, the amount, and any authorization signatures. 

> [!IMPORTANT]
> Starting January 1st, 2024 in Denmark, this feature will be enabled by default and you will be restricted from additional configurations for purchase and Ssales documents. This is because specific setups are being mandated by new the Danish bookkeeping act, where you must attach minimum vouchers for purchase and sales documents. 

## Setup digital vouchers  

You can use different setups for the following documents and journals. 

  | Entry Type | Description |
  |----------|------------------------------|
  | **Sales Document** | Specifies postings completed from the sales documents. This option can't be edited in Danish localization. |
  | **Purchase Document** | Specifies postings completed from the purchase documents. This option can't be edited in Danish localization. |
  | **General Journal** | Specifies postings completed from the **General Journal** for all **Account Types** excluding those related to **Customer** and **Vendor**. By selecting one of those options, you change control of the posting process. If you select the **Customer** as the **Account Type**, the system checks your setup related to the **Sales Journal**. If you select the **Vendor** as the **Account Type**, the system checks your setup related to the **Purchase Journal**. |
  | **Sales Journal** | Specifies the posting completed from the **Sales Journal** and the **General Journal** with the **Customer** selected as the **Account Type**. |
  | **Purchase Journal** | Specifies the posting completed from the **Purchase Journal** and the **General Journal** with the **Vendor** selected as the **Account Type**. |

To set up how your organization uses enforced digital vouchers outside of those already required by law, follow these steps.

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Digital Voucher Entry Setup**, and then select the related link. Or, run the **Entry Setup** action from the **Digital Voucher Setup** page.  
2. In the **Entry Type** column, select an option.   
3. In the **Check Type** column, select an enforcement option. If you select **None**, you can post this type of entry without any digital voucher. If you select **Attachment**, an attachment is required with an entry. If you select **Attachment or Note**, you can have an attachment or a note for your entry. 
4. Select the **Generate Automatically** checkbox to generate the digital voucher automatically. For example, if you don't want to manually add a sales invoice to your transaction, select this check. Then, you will just need to post the document. The system automatically creates the document based on your report layout and attaches it to this transaction. 
5. Select the **Skip If Manually Added** checkbox to not add the automatically generated digital voucher if the manual attachment has already been added.  

### Use source codes for setup  

To use enforcement for journals but not for all transaction types, you can connect the specific source code to identify the entry type in the general journal, sales journal, or purchase journal.  

To set up specific source codes for digital vouchers, complete these steps.  

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Digital Voucher Entry Setup**, and then select the related link.
2. On the **Digital Voucher Entry Setup** page, select **Source Codes**.  
3. Select the source codes you want to configure. 
4. Close the page.   

## Use the functionality  

**Purchase documents** - Open any of the purchase documents, and populate the required fields. Before you post, use these steps to add a digital voucher.

1. In the **Incoming Document Files** FactBox of the document page, select **Attach File**.  
2. On the **Insert File** page, drop a file directly or browse to and select a file. 
3. The document is attached to the **Incoming Document Files** FactBox. You can find the document name and type for each of the lines. 

**Sales documents** - Open any of the sales documents and populate the required fields. For sales documents, you don't need to attach a document manually because the system automatically creates an attachment based on your sales document layout. After you post the document, you can find the automaticallt created and attached voucher based on your report.   

1. In the **Incoming Document Files** FactBox from the document line, select **Incoming Document**. 
2. On the **Incoming Document** page, select **Delete**.   

> [!NOTE]
> If the digital voucher is configured as mandatory and you try to post documents or journals without attaching the voucher, the system won't allow this. You will receive the error message: _Not possible to post without attaching the digital voucher_.  

### Find attached vouchers in transactions   

You can find the attachment from the posted document or from **General Ledger Entries** by looking at the **Incoming Document Files** FactBox.  

An attached document can't be deleted after posting, but attachments can continue to be added after posting.   


## See also

[Financial Management](../../finance.md)  
[Denmark Local Functionality](denmark-local-functionality.md) 
[Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
