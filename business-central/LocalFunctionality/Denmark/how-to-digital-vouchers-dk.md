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
  | **Sales Document** | Specifies postings you are doing from the sales documents, and this option cannot be edited in Danish localization. |
  | **Purchase Document** | Specifies postings you are doing from the purchase documents, and this option cannot be edited in Danish localization. |
  | **General Journal** | Specifies postings you are doing from the **General Journal** for all **Account Types** excluding those related to **Customer** and **Vendor**. By choosing one of those options, you will change control of the posting process. If you select the **Customer** as the **Account Type**, the system will check your setup related to the **Sales Journal**. If you select the **Vendor** as the **Account Type**, the system will check your setup related to the **Purchase Journal**. |
  | **Sales Journal** | Specifies posting you are doing from the **Sales Journal** and the **General Journal** with the **Customer** selected as the **Account Type**. |
  | **Purchase Journal** | Specifies posting you are doing from the **Purchase Journal** and the **General Journal** with the **Vendor** selected as the **Account Type**. |

To set up how your organization will use enforced digital vouchers outside of already required by the law, follow the next steps:   

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Digital Voucher Entry Setup**, and then select the related link. Or run the **Entry Setup** action from the **Digital Voucher Setup** page.  
2. Select one of the options in the **Entry Type** column.   
3. Choose one of the enforcement options in the **Check Type** column. In case of check type **None** you can post this type of entry without any digital voucher. In case of check type **Attachment**, you need to have an attachment to your entry. In case of check type **Attachment or Note** you can either have an attachment or a note for your entry. 
4. Select the **Generate Automatically** checkbox if the digital voucher needs to be generated automatically. For example, if you do not want manually to add sales invoice to your transaction, you can select this check box and you just need to post the document; system will automatically create the document based on your report layout and attach it to this transaction. 
5. Select the **Skip If Manually Added** checkbox, for not adding the automatically generated digital voucher if the manual attachment has already been added by the user.  

### Use Source Codes for setup  

If you want to use enforcement for journals but not for all transaction types, you can connect the specific source code to identify the entry type in general journal, sales journal, purchase journal, etc.  

To setup specific **Source Codes** for **Digital Vouchers**:   

1. Run the **Source Codes** action from the **Digital Voucher Entry Setup** page.  
2. Choose the **Source Codes** you want to have configured from the **Voucher Entry Source Codes** page. 
3. Close the page.   

## Using the functionality  

Open any of purchase documents and populate all required fields. Before posting you need to add a digital voucher. To do this, follow next steps:  

1. In the **Incoming Document Files** FactBox choose the **Attach File** action.  
2. In the **Insert File** page, drop a file directly or browse to the file from this page. 
3. The document will be attached to the **Incoming Document Files** FactBox, and you can find document name and type for each of lines. 

Open any of sales documents and populate all required fields. For sales documents you do not need to attach document manually, as system will automatically create attachment based on your sales document layout. After posting document, you can find automaticall created and attached voucher based on your report.   

1. In the **Incoming Document Files** FactBox from the document line, choose the **Incoming Document** action. 
2. Run the **Delete** action from the **Incoming Document** page.   

> [!NOTE]
> If digital voucher has been configured as a mandatory without automatically creation configured, and user tries to post documents or journals without attaching the voucher, system will not allow this, and it will show the error message: _Not possible to post without attaching the digital voucher_.  

### Finding attached voucher in transactions   

You can find the attachment from the posted document or from **General Ledger Entries** looking at the **Incoming Document Files** FactBox.  

Once attached document after posting cannot be deleted, but users can still add more attachments after posting.   


## See also

[Financial Management](../../finance.md)  
[Denmark Local Functionality](denmark-local-functionality.md) 
[Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
