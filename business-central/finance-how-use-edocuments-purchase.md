---
title: Use e-documents in the purchase process
description: Learn how to set up vendors and handle purchase invoices, orders, and credit memos using e-documents in Dynamics 365 Business Central.
author: altotovi
ms.author: altotovi
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: electronic document, electronic invoice, e-document, e-invoice, receive, purchase, matching, mapping, Copilot
ms.search.form: 50, 51, 138, 6103, 6133, 6121, 6167, 9307, 9308
ms.date: 03/18/2025
ms.custom: bap-template
---

# Use e-documents in the purchase process

You can use configured electronic documents (e-documents) with the following purchase documents:

- Purchase invoices
- Purchase orders
- Purchase credit memos
- General journals

> [!NOTE]
> When you receive an e-document from a specific vendor, [!INCLUDE [prod_short](includes/prod_short.md)] matches the e-document with the vendor by verifying the following information in this order:
>
> 1. **GLN** (from the Vendor card)
> 1. **VAT Registration No.** (from the Vendor card)
> 1. **Participation Identifier** from the **Service Participant** page (using the **E-Document Service Participation** field from the Vendor card)
> 1. **Name** and **Address** (from the Vendor card)

## E-documents in purchases

You can receive purchase e-documents manually, or by using the **Receive** batch job.  

### Set up vendors to work with different purchase documents  

Follow these steps to configure vendors for incoming electronic invoices:

1. Select the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then select the related link.
1. Choose the vendor you want to configure.
1. On the **Receiving** FastTab, in the **Receive E-Document To** field, specify the default purchase document you want to generate from the received e-document.

   > [!NOTE]
   >
   > - In the **Receive E-Document To** field, you can either select a **Purchase Invoice** or **Purchase Order** based on what you want to create from the received e-invoice. This selection doesn't affect the creation of corrective documents. In both scenarios, [!INCLUDE [prod_short](includes/prod_short.md)] generates a credit memo.
   >
   > - If you choose the **Purchase Order** option in the **Receive E-Document To** field, [!INCLUDE [prod_short](includes/prod_short.md)] tries to update one of the existing purchase orders. However, if the purchase order for a vendor in the received e-document doesn't exist, [!INCLUDE[prod_short](includes/prod_short.md)] creates a new purchase order, using the same approach as creating a new purchase invoice explained in this [article later](#work-with-purchase-invoices).

1. Choose one of the options you want to use for the selected vendor.
1. Close the page.

### Work with purchase invoices  

#### Run the batch job  

> [!NOTE]
> This batch job automates the process of collecting your incoming invoices. It works only in countries or regions where the functionality is available.  

Every time a **Job Queue** runs, if the external service has incoming invoices from your vendor, [!INCLUDE [prod_short](includes/prod_short.md)] collects and imports those invoices. To complete the process, follow these steps:

1. After the batch job finishes running, the imported invoices are listed on the **E-Documents** page with their basic details.
1. To view more details, open a specific e-document.
1. Depending on whether your e-document setup automatically processes invoices, or requires that you review and confirm the details before processing, follow these steps. Learn more in [Set up e-documents](finance-how-setup-edocuments.md) for information about how to require confirmation.

   **Automatic processing**

   1. If you automatically process invoices, and there are no errors or issues in the e-document, the **Record** field maps the document number of the purchase invoice if a number series is specified on the **Vendor Card** page. To open the document, select the link.

   > [!NOTE]
   > This [!INCLUDE [prod_short](includes/prod_short.md)]-created document isn't the posted document.

1. To go directly to the purchase document, select the **Record** field. After you open the **Purchase Invoice** page, check the document. If everything is correct, post the document.  
1. When you post the purchase document, the **Record** field on the **E-Document** updates from **Invoice** to **Purchase Invoice**, and the number of the posted purchase document is available. You can select the number to open it.
   Details about logs are the same as they are in the sales process for e-documents.  

   **Review and confirm before processing**

   1. If you must review and confirm the details before processing the invoice, open the document.
   1. On the **E-Document** page, choose the **View extracted data** action.
   1. On the **Received purchase document data** page, review the details. If things look good, choose **OK**.
   1. To process the invoice, follow the steps described for **Automatic processing**.

   > [!TIP]
   > When you receive an incoming e-document, it's typically in XML or similar format that can be difficult, if not impossible, to read. For example, if you aren't technical and don't understand the XML format, it might be hard to review an invoice before you process it. To make it easier for everyone to review incoming e-documents, invoices and credit memos have an **E-invoice Lines** FastTab that displays details from the imported file, such as line and header information, in a way that's easy to understand.
   >
   > The preview feature is only available for invoice and credit memo types of incoming e-documents.

### Handle errors and warnings

Errors in the sales process are mostly related to the availability of the service. The incoming document can contain multiple reasons for errors. The most common reason is that [!INCLUDE [prod_short](includes/prod_short.md)] can't recognize the lines on an e-document from your vendor and can't enter lines in your purchase invoice.

There are two common errors:  

- If you want to use a specific line from your vendor invoice that was directly posted to the general ledger (G/L) account, you must correctly configure the **Mapping Text** value. To bypass this error when using G/L accounts, select the **Map Text to Account** to create a specific mapping of the **Mapping Text** value with the **Debit Acc. No.**. Learn more about [account mapping](finance-how-use-edocuments-purchase.md#map-text-on-an-e-document-to-a-specific-vendor-account).  
- If you want to track the inventory and use lines from your vendor invoice to fill in the items on your document lines, you must correctly configure the **Item Reference No.** value. To bypass this error, map external items with your item numbers by using the item reference list. Learn more in [use item references](inventory-how-use-item-cross-refs.md).

After you fix the errors and warnings, you can manually specify when to create a purchase invoice based on your setup by selecting **Create Document**.

### Recreate a deleted purchase invoice or credit memo

Mistakes happen, so it's important to be able to fix them quickly. If you accidentally delete a purchase invoice or credit memo and can't link the incoming e-document to the correct one, you can now recreate a new purchase document based on details in the e-document. Problem solved, and you can go take care of other business.

If you accidentally delete a purchase invoice or credit memo, you can't proceed with the e-document connection with the regular purchase document in Business Central. To get yourself unstuck, you can run the **Recreate Document** action from the e-document. The action creates an unposted purchase invoice or credit memo based on the type of incoming document, its information, and the G/L mapping or item references used.

> [!NOTE]
> The action works only with unposted purchase invoices and credit memos. It doesn't work for purchase orders.

#### Map text on an e-document to a specific vendor account

To map lines with expenses for E-Documents, you need to map descriptions with **G/L Account**. Then, use the **Map Text to Account** action to link specific text on a vendor invoice from the **E-Document Service** to a vendor account. Any part of the E-document description that exists as a mapping text means that the **Vendor No.** field on the resulting document or journal lines of type **G/L Account** are filled with the vendor in question.

In addition to mapping text to a vendor account or G/L accounts, you can also map text to a bank account for electronic documents related to paid expenses. This option creates a general journal line that is ready to post to a bank account.

1. Select the relevant E-Document line with the displayed error message and then choose **Map Text to Account** action. The **Text-to-Account Mapping** page displays.
1. In the **Mapping Text** field, enter any text that appears on vendor invoices for which you want to create purchase documents or journal lines. You can enter up to 50 characters.
1. In the **Vendor No.** field, enter the vendor that the resulting purchase document or journal line will be created for.
1. In the **Debit Acc. No.** field, enter the debit-type G/L account that is inserted on resulting purchase document or journal line of type G/L Account.

   > [!NOTE]
   > Don't use the **Credit Acc. No.**, **Bal. Source Type**, and **Bal. Source No.** fields with E-documents.

1. Repeat steps 2 through 5 for all error messages on E-documents that you want to automatically create **G/L Accounts** and documents for.  

#### Manually import one or more invoices  

To manually import one or more external e-documents, follow these steps:

1. Select the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Service**, and then select the related link.
1. On the **E-Document Service** page, select the active service.
1. Select **Receive**, and upload the e-document file that you got from the vendor.
1. If an error message occurs, open the e-document to fix the issues.
1. When you finish fixing the issues, in the **Import Manually** group, select **Create Document**.  
1. After you create the document in [!INCLUDE[prod_short](includes/prod_short.md)], using a batch job doesn't change the way you view it.

#### Work with attachments  

Peppol and similar e-invoicing files are machine-readable formats that aren't easy for people to read. To improve reading, Peppol made it possible to embed a PDF file into the Peppol BIS 3 format as a binary object. If your incoming Peppol BIS 3 file has an embedded PDF, [!INCLUDE [prod_short](includes/prod_short.md)] automatically processes it and adds the PDF as an attachment to the purchase document after creating it.

## E-documents with purchase orders  

### Link purchase orders with the received e-documents

If your **Vendor** configured the **Received E-Document To** field to work with **Purchase Orders**, once an electronic document is created in [!INCLUDE[prod_short](includes/prod_short.md)] (manually or from external end point), [!INCLUDE[prod_short](includes/prod_short.md)] does the following steps:  

1. If the **Purchase Order** for this particular vendor exists and there's a purchase order number in the receive **E-Document** file, [!INCLUDE[prod_short](includes/prod_short.md)] automatically links this **E-Document** with the mentioned **Purchase Order**, and the **Document Status** of this **E-Document** is set to **In Progress**, and the **E-Document Status** in the **Service Status** subpage is set to **Order linked**. This link is visible in the **Document** field on this specific **E-Document**. If you need to change the **Purchase Order** linked automatically, you can do it using the **Update Purchase Order Link** action and manually select one of the existing purchase orders for this vendor. You can only do it before matching the lines between **E-Document** and **Purchase Order**.  

1. If the **Purchase Order** for this particular vendor exists but there's no purchase order number in the received **E-Document** file, [!INCLUDE[prod_short](includes/prod_short.md)] offers the possibility to choose one of the existing purchase orders when and if you uploaded this document manually. This condition opens the **Purchase Orders** list with orders only for the vendor from whom you received the **E-Document**. You need to select the **Purchase Order** you want and then select **OK**. If you failed to select the correct **Purchase Order**, or obtained the **E-Document** automatically from an external endpoint using the **Job Queue**, a new **E-Document** isn't linked to any purchase document. The **Document Status** then shows **Error**, and the **E-Document Status** in the **Service Status** subpage also shows **Imported document processing error**. To finish linking with the **Purchase Order**, select the **Update Purchase Order Link** action and choose one of the existing purchase orders for this vendor.

1. If the **Purchase Order** for this particular vendor doesn't exist when a new **E-Document** is created, [!INCLUDE[prod_short](includes/prod_short.md)] creates a new **Purchase Order**, using the same model of creation that already exists for new **Purchase Invoices**. The **Document Status** of this **E-Document** is set to **Processed**, and the **E-Document Status** in the **Service Status** subpage is set to **Imported document created**. After which, this link is visible in the **Document** field on this specific **E-Document**.

### Match lines from received e-document with purchase order  

You can match your received electronic documents with purchase orders' lines from two different places: from the **E-Document** page or from the **Purchase Order** page. The easiest way to locate the already linked **Purchase Orders** is to use the **Linked Purchase Orders** tile as a part of **E-Document Activities**. All nonlinked documents can be found using the tile **Waiting Purchase E-Invoices** where you have a list of **E-Documents** that you need to review. The **E-Document Activities** with these two tiles can be found in the following **Role Centers**: Business Manager Evaluation, Business Manager, Accountant, Inventory Manager, and Shipping and Receiving.

> [!TIP]
> There are two ways to match lines. One way is to do it manually, as described in the article. The other way is to use the **E-document matching assistance with Copilot**. The E-document matching assistance feature helps you match received electronic invoices with existing purchase order lines by using large language modules (LLM) model. Learn more about [using Copilot][Map e-documents to purchase order lines with Copilot](map-edocuments-with-copilot.md).
> [!NOTE]
> If the VAT percentage differs between the incoming document and the company's VAT percentage, matching documents can't be used in a multi-country environment.  

#### Match lines from purchase order  

You can match the lines from the **Purchase Orders** list or from one of the opened **Purchase Orders**. To begin the process, use the following steps:  

1. Select the **Linked Purchase Orders** tile on your Role Center if there's a number.
1. Choose one of the two options for matching:

   - If you want to match the lines from the **Purchase Orders** list, select the **Purchase Order** line that you want to match and select the **Map E-Document Lines** action.  
   - If you want to first open the **Purchase Order**, open the document and then select the **Map E-Document Lines** action.
1. Because both options have the same process, the **Purchase Order Matching** page opens with the following content:

    1. In the header, you can find the following information, which can help you to map the lines easier:

       |Field name |Description |
       |--------|-----------------|
       |Vendor Name |Specifies the vendor’s name of the electronic document. |
       |E-Document No. |Specifies the linked electronic document number. |
       |E-Document Date |Specifies the linked electronic document date.  |
       |E-Document Amount |Specifies the linked e-document total amount including VAT. |

    1. In the lines, you can find the lines imported from the **E-Document** file on the left side and the lines from the existing **Purchase Order** on the right.  
    1. All lines on both sides have item numbers and descriptions, together with the **Direct Unit Cost** and **Line Discount %**.  
    1. On the **Imported Lines** side, you can also locate the **Quantity** field as a total quantity from e-invoice and the **Matched Quantity** field specifying the quantity that is already matched to the purchase order lines.
    1. On the **Purchase Orders Lines** side, you can also find the **Available Quantity** as the quantity that can be matched to this line (received, but not invoiced quantity) and **Qty. to Invoice**, specifying the quantity that is already matched to this line.
    1. To match lines, select the lines on both sides that you want to match and select the **Match Manually** action. The matched lines are marked in green.
    1. It's possible to match one to one, but it's also possible to match many to one or one to many, by selecting more lines on one side or the other before you choose the **Match Manually** action.
    1. You can also select the **Match Automatically** action to automatically match all lines with the same **Type**, **No.**, **Unit Price**, **Discount**, and **Unit of Measure**.
    1. If you make a mistake, you can select the **Remove Match** action to remove the matched lines on the purchase order side or select the **Reset Matching** action to reset all matches.
    1. If your **E-Document** has many lines, you can select the **Show Pending Lines** action during the matching process to remove all the e-document lines if they're already matched. If you need to view all the lines, you can always select the **Show All Lines** action.

1. After you finish the matching, select the **Apply To Purchase Order** action.
1. After you apply the matching to the purchase order, [!INCLUDE[prod_short](includes/prod_short.md)] updates the following fields:

    1. The **Vendor Invoice No.** and **Document Date** fields on the document header update with values from the electronic document that you received and linked.
    1. The **Qty. to Invoice** field on the lines update with the values from the **Qty. to Invoice** column from the **Purchase Order Matching** page based on the match.
    1. Now you can post the document by choosing the **Post** action.  
    1. After you post the document, the value in the **Document** field on the **E-Document** page changes to relate to the **Posted Purchase Invoice**.
    1. Close the page.  

> [!IMPORTANT]
> By default, you can match only the lines that have the same total amount in both documents. That means **Direct Unit Cost** together with the applied Line **Discount %** must be the same, because in one document you can have an amount without discount and in another with discount.  

If you want to add tolerance and allow the difference between lines in e-invoice and purchase order, follow these steps:

1. Select the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchases & Payables Setup**, and then select the related link.  
1. Allow tolerance in the **E-Document Matching Difference %** field by specifying the maximum percentage of cost difference to allow when matching an incoming e-document line with a purchase order line.
1. This setup applies to all the matching lines, but considers the tolerance for the total amount, as for **Direct Unit Cost** together with applied **Line Discount %**.  
1. Close the page.

##### Other options

If your inbound electronic invoice has lines that aren't on your purchase order, [!INCLUDE[prod_short](includes/prod_short.md)] prevents you from posting the document because you can't partially post an incoming invoice. Therefore, you must ensure that you all invoice lines are correctly mapped to the purchase order. If you experience this issue, follow these steps to resolve it:

1. On the **Imported Lines** FastTab on the **Purchase Order Matching** page, choose the line that doesn't exist on the purchase order. Now choose the :::image type="content" source="media/assist-edit-icon.png" alt-text="Screenshot of the AssistEdit button."::: button, and choose the **Create Purchase Order Line** action.
1. On the **E-Doc. Create Purch Order Line** page, in the **Type** field, choose the type of line you want to create in your purchase order. You can choose any of type.
1. Based on the line type, you can choose the **No.** to specify what you received. For example, an item, general ledger account, resource, and so on.
1. The unit of measure, quantity, amount, discount, and other values are copied from the inbound invoice line.
1. You can select the **Learn matching rule** field to specify whether to create a matching rule. This feature works only for items and G/L accounts. Item references are created for items and text to account mappings are created for G/L accounts.
1. Select **OK**.
1. A purchase order line is created on the purchase order, and you can map it on the **Purchase Order Lines** FastTab on the **Purchase Order Matching** page.

> [!NOTE]
> If you change the quantity, the unit amount recalculates to the same total amount as the original invoice line.

#### Matching lines from e-document  

You can match the lines on the **E-Document** page. To begin, use the following steps:  

1. Select the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Documents**, and then select the related link.
1. Select the **E-Document** that you want to match.
1. Choose the **Match Purchase Order** action to open the **Purchase Order Matching** page.  
1. Repeat the same steps that you used when you started matching from purchase orders.

## Overview of e-document statuses

To get a better overview of all e-documents in the company, you can select the **Accountant** Role Center where e-document statuses exist. There, you can find e-document activities that have the following statuses:

- **Incoming e-documents:**
  - Processed
  - In Progress
  - Error

## Related information

- [Set up e-documents](finance-how-setup-edocuments.md)  
- [Use e-document in the sales process](finance-how-use-edocuments.md)  
- [Extending e-documents functionality](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments)  
- [Financial Management](finance.md)  
- [Invoice sales](sales-how-invoice-sales.md)  
- [Record purchases with purchase invoices and orders](purchasing-how-record-purchases.md)  
- [Work with Business Central](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
