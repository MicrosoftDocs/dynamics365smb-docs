---
title: Set up digital vouchers in Denmark
description: This article explains how to set up and use enforced digital vouchers in Business Central for the Danish localization.
author: altotovi
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.search.keywords: digital voucher, voucher, attachment, setup, denmark, enforced voucher, digital voucher setup
ms.search.form: 5579, 5582, 5587
ms.date: 03/03/2025
ms.custom: bap-template
ms.reviewer: v-soumramani
---

# Set up digital vouchers in Denmark

Administrators can use digital voucher functionality to require that documents are attached to specific transactions when they're posted. Therefore, this functionality allows for a source-driven approach and provides a better audit trail. Different types of enforcement can be configured for this purpose, depending on the documents or journal types.

The term *digital voucher* refers to a digital or electronic form of a traditional voucher in accounting. A voucher is a document that's used to support and authorize financial transactions. Vouchers typically serve as evidence of an expenditure or a receipt of funds. The voucher might include details such as the date of the transaction, a description, the amount, and any authorization signatures.

> [!IMPORTANT]
> As of July 1, 2024, this feature will be enabled by default in Denmark. You'll then be restricted from doing additional configuration for purchase and sales documents. This restriction applies because the new Danish bookkeeping act mandates specific setups, where you must attach minimum vouchers for purchase and sales documents. Before this date, you can activate this feature in **Feature Management**.  

## Set up digital vouchers

You can use different setups for the following documents and journals.

| Entry type | Description |
|------------|-------------|
| **Sales Document** | Specifies postings that are completed from sales documents. In the Danish localization, this option can't be edited. |
| **Purchase Document** | Specifies postings that are completed from purchase documents. In the Danish localization, this option can't be edited. |
| **General Journal** | Specifies postings from the general journal for all account types, except postings that are related to the customer and vendor. If you select one of those account types, you change control of the posting process. If you select **Customer** as the account Type, [!INCLUDE [prod_short](../../includes/prod_short.md)] checks your setup related to the sales journal. If you select **Vendor** as the account type, [!INCLUDE [prod_short](../../includes/prod_short.md)] checks your setup related to the purchase journal. |
| **Sales Journal** | Specifies the postings that are completed from the sales journal and the general journal where **Customer** is selected as the account type. |
| **Purchase Journal** | Specifies the postings that are completed from the purchase journal and the general journal where **Vendor** is selected as the account Type. |

Follow these steps to define how your organization uses enforced digital vouchers, beside the steps that are already required by law.

1. Select the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Digital Voucher Entry Setup**, and then select the related link. Alternatively, on the **Digital Voucher Setup** page, select **Entry Setup**.
1. In the **Entry Type** column, select an option.
1. In the **Check Type** column, select an enforcement option. If you select **None**, you can post the selected type of entry without any digital voucher. If you select **Attachment**, the entry must include an attachment. If you select **Attachment or Note**, you can include an attachment or a note for the entry.
1. Select the **Generate Automatically** checkbox to generate the digital voucher automatically. For example, if you don't want to manually add a sales invoice to your transaction, select this checkbox. Then, you just have to post the document. The system automatically creates the document, based on your report layout, and attaches it to the transaction.
1. Select the **Skip If Manually Added** checkbox if you don't want to add an automatically generated digital voucher. This setting is useful if you already added a manual attachment.

### Use source codes for setup

To use enforcement for journals, but not for all transaction types, connect the specific source code to identify the entry type in the general journal, sales journal, or purchase journal.

Follow these steps to set up specific source codes for digital vouchers.

1. Select the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Digital Voucher Entry Setup**, and then select the related link.
1. On the **Digital Voucher Entry Setup** page, select **Source Codes**.
1. Select the source codes that you want to configure.
1. Close the page.

## Use the functionality

> [!IMPORTANT]
> Digital vouchers are enabled by default, and you must retain your vouchers. Retaining vouchers can significantly increase the size of your database. To mitigate this, use lower resolution scans for your purchase invoices. For your sales invoices, create layouts with smaller images or none at all, because attachments are automatically generated based on the layout. All attachments are stored in your database and affect its size, but you can minimize the effect by uploading smaller files.

### Purchase documents

Open one of the purchase documents, and set the required fields. Before you post the document, follow these steps to add a digital voucher.

1. On the document page, in the **Incoming Document Files** FactBox, select **Attach File**.
1. Drag a file directly onto the **Insert File** page, or browse to the file from this page.

The document is attached to the **Incoming Document Files** FactBox. For each line, you can find the document name and type.

### Sales documents

Open one of the sales documents, and set the required fields. For sales documents, you don't have to attach a document manually. The system automatically creates an attachment, based on your sales document layout. After you post the document, you can find the automatically created and attached voucher based on your report.

1. In the **Incoming Document Files** FactBox from the document line, select **Incoming Document**.
1. On the **Incoming Document** page, select **Delete**.

> [!NOTE]
> If attachment of a digital voucher is configured as mandatory, and you try to post documents or journals without attaching a voucher, the system prevents you from posting. You receive the following error message: "Not possible to post without attaching the digital voucher."

### Find attached vouchers in transactions

You can find the attachment from the posted document or from the **General Ledger Entries** page by looking in the **Incoming Document Files** FactBox.

You can't delete an attached document after posting is completed. However, you can add more attachments after posting is completed.

## Related information

- [Financial Management](../../finance.md)  
- [Denmark Local Functionality](denmark-local-functionality.md)  
- [Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
