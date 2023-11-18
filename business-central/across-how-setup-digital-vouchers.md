---
title: Set up digital vouchers
description: This article explains how to set up and use enforced digital vouchers in Microsoft Dynamics 365 Business Central.
author: altotovi
ms.author: altotovi
ms.reviewer: 
ms.service: dynamics365-business-central
ms.topic: how-to
ms.search.keywords: digital voucher, voucher, attachment, setup
ms.search.form: 5579, 5582, 5587
ms.date: 11/17/2023
ms.custom: bap-template

---

# Set up digital vouchers  

Digital voucher functionality empowers administrators to mandate attaching documents when specific transactions, providing a source-driven approach and better audit trail. Various types of enforcement, depending on documents or journal types, can be configured for this purpose.  

Digital voucher refers to a digital or electronic form of a traditional voucher in accounting, which is a document used to support and authorize financial transactions. In accounting, a voucher typically serves as evidence of an expenditure or receipt of funds. The voucher may include details such as the date of the transaction, description, amount, and authorization signatures. 

> [!IMPORTANT]
> In certain countries, you may be restricted from configuring all options, as specific setups may be mandated by legal requirements. If you encounter these restrictions, look for a detailed explanation on your country's documentation page.  

## Enable digital vouchers  

Follow these steps to enable digital voucher functionality.

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Digital Voucher Setup**, and then select the related link. 
2. Select the **Enabled** checkbox.  

## Set up digital vouchers  

You can use a different set up for the following documents and journals:  

  | Entry Type | Description |
  |----------|------------------------------|
  | **Sales Document** | Specifies postings completed from the sales documents. |
  | **Purchase Document** | Specifies postings completed from the purchase documents. |
  | **General Journal** | Specifies postings completed from the **General Journal** for all account types except those related to **Customer** and **Vendor**. When you select one of those options, you change control of the posting process. If you select **Customer** as the **Account Type**, the system checks your setup related to the **Sales Journal**. If you select **Vendor** as the **Account Type**, the system checks your setup related to the **Purchase Journal**. |
  | **Sales Journal** | Specifies the posting completed from the **Sales Journal** and the **General Journal** with the **Customer** selected as the **Account Type**. |
  | **Purchase Journal** | Specifies the posting completed from the **Purchase Journal** and the **General Journal** with the **Vendor** selected as the **Account Type**. |

To set up how your organization uses enforced digital vouchers, follow these steps.   

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Digital Voucher Entry Setup**, and then select the related link. Or, on the **Digital Voucher Setup** page, select **Entry Setup**.  
2. In the **Entry Type** column select an option.
3. In the **Check Type** column, select an enforcement option. If the check type is **None**, you can post this type of entry without a digital voucher. If the check type is **Attachment**, your entry must include an attachment. If the check type is **Attachment or Note**, you can have an attachment or a note for your entry. 
4. Select the **Generate Automatically** checkbox if the digital voucher must be generated automatically. For example, if you don't want to manually add a sales invoice to your transaction, select this check box and post the document. The system automatically creates the document based on your report layout and attaches it to this transaction. 
5. Select the **Skip If Manually Added** checkbox to not add an automatically generated digital voucher if the manual attachment has already been added by the user.  

### Use source codes for setup  

To use enforcement for journals but not for all transaction types, connect the specific source code to identify the entry type in the general journal, sales journal, or purchase journal.  

To setup specific **Source Codes** for **Digital Vouchers** complete the following steps.   

1. On the **Digital Voucher Entry Setup** page, select **Source Codes**.  
2. On the **Voucher Entry Source Codes** page, select the **Source Codes** you want to configure. 
3. Close the page.   

## Use the functionality  

Open a purchase or sales document and enter information in the required fields. Before you post the document, you need to attach a digital voucher. To do this, follow these steps. 

1. In the **Incoming Document Files** FactBox, select **Attach File**.  
2. On the **Insert File** page, drop a file directly or browse to the file from this page. 
3. The document is attached to the **Incoming Document Files** FactBox, and you can find the document name and type for each of lines. 

If you accidentally attach the wrong voucher, you can delete it before you post the document using the following steps.

1. In the **Incoming Document Files** FactBox from the document line, select **Incoming Document**. 
2. On the **Incoming document** page, select **Delete**.   

> [!NOTE]
> If attaching a digital voucher is configured as mandatory and you try to post documents or journals without attaching the voucher, the system won't let you post and you will receive the following error message: _Not possible to post without attaching the digital voucher_.  

### Find attached voucher in transactions   

You can find the attached voucher in the posted document or by going to the **General Ledger Entries** page and looking in the **Incoming Document Files** FactBox.  

AFter the document is attached, it's cant' be deleted after posting. However you can add more attachments after posting is complete.


## See also

[Financial Management](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
