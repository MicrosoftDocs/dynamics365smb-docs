---
title: Use E-Documents in the purchase process
description: Learn how to set up vendors and handle purchase invoices, orders, and credit memos using e-documents in Dynamics 365 Business Central.
author: altotovi
ms.author: altotovi
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: electronic document, electronic invoice, e-document, e-invoice, receive, purchase, matching, mapping, Copilot
ms.search.form: 50, 51, 138, 6103, 6133, 6121, 6167, 9307, 9308
ai-usage: ai-assisted
ms.date: 09/29/2026
ms.custom: bap-template
---

# Use e-documents in the purchase process

You can use electronic documents (e-documents) with the following purchase documents:

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

To configure vendors for incoming electronic invoices, follow these steps:

1. Select the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then select the related link.
1. Choose the vendor you want to configure.
1. On the **Receiving** FastTab, in the **Receive E-Document To** field, specify the default purchase document you want to generate from the received e-document.

   > [!NOTE]
   >
   > In the **Receive E-Document To** field, you can either select a **Purchase Invoice** or **Purchase Order** based on what you want to create from the received e-invoice. This selection doesn't affect the creation of corrective documents. In both scenarios, [!INCLUDE [prod_short](includes/prod_short.md)] generates a credit memo.
   >
   > If you choose the **Purchase Order** option in the **Receive E-Document To** field, [!INCLUDE [prod_short](includes/prod_short.md)] tries to update one of the existing purchase orders. However, if the purchase order for a vendor in the received e-document doesn't exist, [!INCLUDE[prod_short](includes/prod_short.md)] creates a new purchase order, using the same approach as creating a new purchase invoice explained in the [Work with purchase invoices](#work-with-purchase-invoices) section in this article.

1. Choose one of the options you want to use for the selected vendor.
1. Close the page.

### Work with purchase invoices  

#### Run the batch job <!--Import e-documents with the E-Document Import Job--> 

> [!NOTE]
> This batch job automates the process of collecting your incoming invoices. It works only in countries or regions where the functionality is available.  

Every time a **Job Queue** runs, if the external service has incoming invoices from your vendor, [!INCLUDE [prod_short](includes/prod_short.md)] collects and imports those invoices. To complete the process, follow these steps:

1. After the batch job finishes running, the imported invoices are listed on the **E-Documents** page with their basic details.
1. To view more details, open a specific e-document.
1. Depending on whether your e-document setup automatically processes invoices, or requires that you review and confirm the details before processing, follow these steps. To learn more about how to require confirmation, go to [Set up e-documents](finance-how-setup-edocuments.md).

   **Automatic processing**

   - If automatic processing succeeds, [!INCLUDE [prod_short](includes/prod_short.md)] creates a purchase draft from the incoming e-document.
   - Open the **Purchase Drafts** page, open the draft, and review and correct the extracted information.

   **Review and confirm before processing**

   1. If you must review and confirm the details before processing the invoice, open the document.
   1. On the **E-Document** page, choose the **View extracted data** action.
   1. On the **Received purchase document data** page, review the details. If things look good, choose **OK**.
   1. To process the invoice, follow the steps described for **Automatic processing**.

1. When the draft is ready, select **Create Document** to create the purchase invoice.

   > [!NOTE]
   > This [!INCLUDE [prod_short](includes/prod_short.md)]-created document isn't the posted document.

1. To go directly to the purchase document, select the **Record** field. After you open the **Purchase Invoice** page, review the document. If everything is correct, post the document.
1. When you post the purchase document, the **Record** field on the **E-Document** updates from **Invoice** to **Purchase Invoice**, and the number of the posted purchase document is available. You can select the number to open it. Details about logs are the same as they are in the sales process for e-documents.

   > [!TIP]
   > When you receive an incoming e-document, it's typically in an XML or similar format that can be difficult, if not impossible, to read. For example, if you aren't technical and don't understand the XML format, it might be hard to review an invoice before you process it. To make it easier for everyone to review incoming e-documents, invoices and credit memos have an **E-invoice Lines** FastTab that displays details from the imported file, such as line and header information, in a way that's easy to understand.
   >
   > The preview feature is only available for invoice and credit memo types of incoming e-documents.

#### Manually import without using the batch job  

To manually import e-documents when you don't have an active batch job, follow these steps:

1. Select the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Service**, and then select the related link.
2. On the **E-Document Service** page, select the active service.
3. To receive all document in a queue from your external service, select **Receive**.

### Handle errors and warnings

Although errors in the process often relate to the availability of the service, other reasons can cause errors with incoming documents. The most typical reason is that [!INCLUDE [prod_short](includes/prod_short.md)] can't recognize the lines on an e-document from your vendor and can't enter lines in your purchase invoice.

The following workarounds address two typical errors:  

- If you want to use a specific line from your vendor invoice that you directly posted to the general ledger (G/L) account, you must configure the **Mapping Text** value. To bypass this error when using G/L accounts, select the **Map Text to Account** action to create a specific mapping of the **Mapping Text** value with the **Debit Acc. No.**. Learn more in [Account mapping](finance-how-use-edocuments-purchase.md#map-text-on-an-e-document-to-a-specific-vendor-account).
- If you want to track the inventory and use lines from your vendor invoice to fill in the items on your document lines, you must configure the **Item Reference No.** value. To bypass this error, map external items with your item numbers by using the item reference list. Learn more in [Use item references](inventory-how-use-item-cross-refs.md).

After you fix the errors and warnings, you can manually specify when to create a purchase invoice based on your setup by selecting **Create Document**.

### Delete incorrect e-documents and avoid duplicates

You can easily discard incorrect or duplicate e-documents. You don't need to keep unprocessed e-documents, so you save space in data storage. [!INCLUDE [prod_short](includes/prod_short.md)] doesn't create new incoming e-documents if you import a batch that contains duplicates. Duplicates are documents with the same vendor, external document number, and date.

If you have a duplicate or incorrect e-document, administrators can delete it by running the **Delete Related Document** action. However, you can't delete e-documents that you already processed and are connected with purchase documents.

### Recreate a deleted purchase invoice or credit memo

Mistakes happen, so it's important to be able to fix them quickly. If you accidentally delete a purchase invoice or credit memo and can't link the incoming e-document to the correct one, you can now recreate a new purchase document based on details in the e-document. Problem solved, and you can go take care of other business.

If you accidentally delete a purchase invoice or credit memo, you can't proceed with the e-document connection with the regular purchase document in Business Central. To get yourself unstuck, you can run the **Recreate Document** action from the e-document. The action creates an unposted purchase invoice or credit memo based on the type of incoming document, its information, and the G/L mapping or item references used.

> [!NOTE]
> The action works only with unposted purchase invoices and credit memos. It doesn't work for purchase orders.

### Link an e-document to an existing purchase document

The **Link to Existing Document** action allows you to associate an incoming e-document with a purchase document that already exists in [!INCLUDE [prod_short](includes/prod_short.md)], rather than creating a new document. This is useful when:

- The purchase document was created manually before the e-document arrived.
- You want to attach the e-document as supporting documentation to an existing transaction.
- You need to correct a previous linking by choosing a different document.

#### When to use this action

Use the e-document processing engine to automatically create draft purchase documents rather than link to existing documents. The processing engine ensures proper document tracking and audit trails.

However, certain scenarios might require that you link to existing documents. Currently, the **Link to Existing Document** action only supports intercompany scenarios. For example, with intercompany invoices, you might receive an e-document from the e-document service while an existing purchase document is already in the system.

> [!NOTE]
> The **Link to Existing Document** action is hidden by default. To show the action to the page, use [personalization](ui-personalization-user.md).

#### Prerequisites

Before you can use the **Link to Existing Document** action:

- The e-document must have a vendor number assigned in the draft.
- The vendor must have an **IC Partner Code** configured on the vendor card. This setting is required because the action currently only supports intercompany scenarios.

#### How to link an e-document to an existing document

To link an e-document to an existing purchase document, follow these steps:

1. Open the **E-Document Purchase Draft** page.
1. Make sure a vendor is assigned to the e-document.
1. Select the **Link to Existing Document** action from the **Process** menu.
1. A list of purchase documents opens, pre-filtered by:
   - The vendor from the e-document
   - The total amount (Amount Incl. VAT) from the e-document
1. Select the document you want to link to.
1. Confirm the linking action when prompted.

#### What happens after you link an e-document

When you link an e-document to an existing purchase document:

| Field | Value |
| -------- | ----------------- |
| **E-Document Link** (on Purchase Document) | Set to the e-document's system ID |
| **Doc. Amount Incl. VAT** | Transferred from e-document total |
| **Doc. Amount VAT** | Transferred from e-document VAT total |
| **Created from E-Document** | Set to **No** (the document existed before linking) |
| **E-Document Status** | Changed to **Processed** |

> [!IMPORTANT]
> No new purchase document is created when linking to an existing document.

#### Relinking to a different document

If the e-document is already processed and linked to a document and you want to link it to a different document, follow these steps:

1. When you select **Link to Existing Document**, a warning message appears:

   > "This e-document is already linked to a document. Linking to [Document Type] [Document No.] will unlink the currently linked document. If it was created from this e-document, it will be deleted. Do you want to continue?"

1. If you proceed:
   - If you created the previously linked document from this e-document, [!INCLUDE [prod_short](includes/prod_short.md)] deletes the document.
   - If you didn't create the previously linked document from this e-document, the document is unlinked only. That is, the **E-Document Link** field is cleared, but the document remains.
1. The newly selected document becomes linked to the e-document.

#### Document type matching

The **Link to Existing Document** action opens the appropriate document list based on the e-document type:

| E-Document Type | Opens Page |
| -------- | ----------------- |
| Purchase Invoice | Purchase Invoices |
| Purchase Credit Memo | Purchase Credit Memos |

#### Error messages

When you use the **Link to Existing Document** action, you might encounter the following errors:

| Error | Cause | Resolution |
| -------- | ----------------- | ----------------- |
| "Cannot link e-document to existing purchase document because vendor number is missing" | No vendor assigned to e-document. | Assign a vendor in the **Vendor No.** field. |
| "IC Partner Code must have a value" | Vendor doesn't have an intercompany (IC) partner code. | Fill in the **IC Partner Code** field on the vendor card. |

#### Map text on an e-document to a specific vendor account

To map lines with expenses for e-documents, you need to map descriptions with **G/L Account**. Then, use the **Map Text to Account** action to link specific text on a vendor invoice from the **E-Document Service** to a vendor account. Any part of the e-document description that exists as a mapping text means that the **Vendor No.** field on the resulting document or journal lines of type **G/L Account** are filled with the vendor in question.

In addition to mapping text to a vendor account or G/L accounts, you can also map text to a bank account for e-documents related to paid expenses. This option creates a general journal line that is ready to post to a bank account.

1. Select the relevant e-document line with the displayed error message and then choose **Map Text to Account** action. The **Text-to-Account Mapping** page displays.
1. In the **Mapping Text** field, enter any text that appears on vendor invoices for which you want to create purchase documents or journal lines. You can enter up to 50 characters.
1. In the **Vendor No.** field, enter the vendor that the resulting purchase document or journal line will be created for.
1. In the **Debit Acc. No.** field, enter the debit-type G/L account that is inserted on resulting purchase document or journal line of type G/L Account.

   > [!NOTE]
   > Don't use the **Credit Acc. No.**, **Bal. Source Type**, and **Bal. Source No.** fields with e-documents.

1. Repeat steps 2 through 5 for all error messages on e-documents that you want to automatically create **G/L Accounts** and documents for.  

#### Manually import invoices  

##### Single invoice  

To manually import single external e-documents, follow these steps:

1. Select the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Documents**, and then select the related link.
2. On the **E-Documents** page, select the **New from file** action.
3. Select the active service you want to use, keeping in mind your document type, and the **Document Format** for this service.
4. Upload the e-document file that you got from the vendor.
5. If an error message occurs, open the e-document to fix the issue.
6. In the **Import Manually** group, select **Create Document**.  

##### Multiple invoices

To manually import single or multiple external e-documents, follow these steps:  

1. Select the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inbound E-Documents**, and then select the related link.
2. On the **Inbound E-Documents** page, select the **Import XML** action.
3. Select the active service you want to use, keeping in mind your document type, and the **Document Format** for this service.
4. Upload the e-document files that you got from the vendor.
5. If an error message occurs, open the e-document to fix the issue.
6. In the **Import Manually** group, select **Create Document**.  

#### Work with attachments  

Peppol and similar e-invoicing files are machine-readable formats that aren't easy for people to read. To improve reading, Peppol made it possible to embed a PDF file into the Peppol BIS 3 format as a binary object. If your incoming Peppol BIS 3 file has an embedded PDF, [!INCLUDE [prod_short](includes/prod_short.md)] automatically processes it and adds the PDF as an attachment to the purchase document after creating it.

## E-documents with purchase orders  

The purchase order matching workflow in this section updates **Qty. to Invoice** on the linked purchase order and then posts that order. Matching lines on an incoming purchase invoice draft is a different workflow. Draft matching creates a separate unposted purchase invoice and keeps links from its lines to the purchase order and receipt lines. Learn more in [Match purchase invoice drafts to purchase orders](match-purchase-invoice-drafts-to-orders.md).

### Link purchase orders with the received e-documents

If your vendor configures the **Received E-Document To** field to work with **Purchase Orders**, when you create an electronic document in [!INCLUDE[prod_short](includes/prod_short.md)] (manually or from an external endpoint), [!INCLUDE[prod_short](includes/prod_short.md)] does the following:  

1. If the purchase order for this vendor exists and there's a purchase order number in the e-document file you received, [!INCLUDE[prod_short](includes/prod_short.md)] automatically links this e-document with the purchase order and sets the **Document Status** of the e-document to **In Progress**. It also sets the **E-Document Status** field on the **Service Status** subpage to **Order linked**. This link shows in the **Document** field on the e-document. If you need to change the purchase order link automatically, use the **Update Purchase Order Link** action and manually select another purchase order for the vendor. You can only change the link before you match the lines between the e-document and the purchase order.  

1. If the purchase order for the vendor exists but there's no purchase order number in the e-document file you received, [!INCLUDE[prod_short](includes/prod_short.md)] offers the option to choose another purchase order when you upload this document manually. This option opens the **Purchase Orders** list page with orders only for the vendor from whom you received the e-document. Select the **Purchase Order** you want, and then select **OK**. If you don't select the correct purchase order, or receive the e-document automatically from an external endpoint by using the job queue, the new e-document isn't linked to a purchase document. The **Document Status** field then shows **Error**, and the **E-Document Status** field on the **Service Status** subpage also shows **Imported document processing error**. To finish linking with the **Purchase Order**, select the **Update Purchase Order Link** action and choose one of the existing purchase orders for this vendor.

1. If the purchase order for the vendor doesn't exist when you create a new e-document, [!INCLUDE[prod_short](includes/prod_short.md)] creates a new purchase order in the same way as new purchase invoices. It sets the **Document Status** field on the e-document to **Processed**, and the **E-Document Status** field on the **Service Status** subpage to **Imported document created**. Afterward, this link shows in the **Document** field on the e-document.

### Match lines from received e-document with purchase order  

You can match received electronic documents with purchase order lines from the **E-Document** or **Purchase Order** pages. The easiest way to locate purchase orders that are already linked is to use the **Linked Purchase Orders** tile as a part of **E-Document Activities**. Use the **Waiting Purchase E-Invoices** to find all unlinked documents. The tile opens a list of e-documents that you need to review. You can find the **E-Document Activities** with these two tiles on the following Role Centers:

- Business Manager Evaluation
- Business Manager
- Accountant
- Inventory Manager
- Shipping and Receiving

> [!TIP]
> There are two ways to match lines. One way is to do it manually, as described in this article. The other way is to use **E-document matching assistance with Copilot** ([Map e-documents to purchase order lines with Copilot](map-edocuments-with-copilot.md)). That Copilot capability is being deprecated and is being replaced by the **Payables Agent**, which uses AI to match incoming purchase invoices with open purchase orders. Learn more in [Payables Agent](payables-agent.md).

> [!NOTE]
> If the VAT percentage differs between the incoming document and the company's VAT percentage, matching documents can't be used in a multi-country environment.  

#### Match lines from purchase order  

To match the lines from the **Purchase Orders** list or from one of the opened **Purchase Orders**, follow these steps:  

1. Select the **Linked Purchase Orders** tile on your Role Center if there's a number.
1. Choose one of the two options for matching:

   - To match the lines from the **Purchase Orders** list, select the **Purchase Order** line that you want to match and select the **Map E-Document Lines** action.  
   - To first open the **Purchase Order**, open the document and then select the **Map E-Document Lines** action.
1. Because both options have the same process, the **Purchase Order Matching** page opens with the following content:

    1. The following information in the header can make it easier to match the lines:

       | Field name | Description |
       | -------- | ----------------- |
       | Vendor Name | Specifies the vendor’s name on the e-document. |
       | E-Document No. | Specifies the linked e-document number. |
       | E-Document Date | Specifies the linked e-document date. |
       | E-Document Amount | Specifies the linked e-document total amount, including VAT. |

    1. In the lines, you can find the lines imported from the e-document file on the left side and the lines from the purchase order on the right.  
    1. All lines on both sides have item numbers and descriptions, together with the **Direct Unit Cost** and **Line Discount %**.  
    1. On the **Imported Lines** side, you can also locate the **Quantity** field as a total quantity from e-invoice and the **Matched Quantity** field specifying the quantity that is already matched to the purchase order lines.
    1. On the **Purchase Orders Lines** side, you can also find the **Available Quantity** as the quantity that you can match to this line (received, but not invoiced quantity) and **Qty. to Invoice**, specifying the quantity that is already matched to this line.
    1. To match lines, select the lines on both sides that you want to match and select the **Match Manually** action. The matched lines are marked in green.
    1. You can match one to one, but you can also match many to one or one to many. Select more lines on one side or the other before you choose the **Match Manually** action.
    1. You can also select the **Match Automatically** action to automatically match all lines with the same **Type**, **No.**, **Unit Price**, **Discount**, and **Unit of Measure**.
    1. If you make a mistake, select the **Remove Match** action to remove the matched lines on the purchase order side or select the **Reset Matching** action to reset all matches.
    1. If your e-document has many lines, you can select the **Show Pending Lines** action during the matching process to hide the e-document lines that are already matched. If you need to show all lines, you can always select the **Show All Lines** action.

1. After you finish the matching, select the **Apply To Purchase Order** action.
1. After you apply the matching to the purchase order, [!INCLUDE[prod_short](includes/prod_short.md)] updates the following fields:

    1. The **Vendor Invoice No.** and **Document Date** fields on the document header update with values from the electronic document that you received and linked.
    1. The **Qty. to Invoice** field on the lines update with the values from the **Qty. to Invoice** column from the **Purchase Order Matching** page based on the match.
    1. Now you can post the document by choosing the **Post** action.  
    1. After you post the document, the value in the **Document** field on the **E-Document** page changes to relate to the **Posted Purchase Invoice**.
    1. Close the page.  

> [!IMPORTANT]
> By default, you can match only the lines that have the same total amount in both documents. That means **Direct Unit Cost** together with the applied Line **Discount %** must be the same, because in one document you can have an amount without discount and in another with discount.  

To add tolerance and allow differences between lines in the e-invoice and purchase order, follow these steps:

1. Select the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchases & Payables Setup**, and then select the related link.  
1. In the **E-Document Matching Difference %** field, specify the maximum percentage of cost difference to allow when matching an incoming e-document line with a purchase order line. This setting applies to all matched lines, but it considers the tolerance for the total amount, which is **Direct Unit Cost** together with the applied **Line Discount %**.  
1. Close the page.

##### Other options

If your inbound e-invoice has lines that aren't on your purchase order, [!INCLUDE[prod_short](includes/prod_short.md)] prevents you from posting the document because you can't partially post an incoming invoice. Therefore, you must ensure that all invoice lines are correctly mapped to the purchase order. If you experience this issue, follow these steps to resolve it:

1. On the **Imported Lines** FastTab on the **Purchase Order Matching** page, choose the line that doesn't exist on the purchase order. Now choose the :::image type="content" source="media/assist-edit-icon.png" alt-text="Screenshot of the AssistEdit button."::: button, and choose the **Create Purchase Order Line** action.
1. On the **E-Doc. Create Purch Order Line** page, in the **Type** field, choose the type of line you want to create in your purchase order. You can choose any of type.
1. Based on the line type, you can choose the **No.** to specify what you received. For example, an item, general ledger account, resource, and so on.
1. The unit of measure, quantity, amount, discount, and other values are copied from the inbound invoice line.
1. You can select the **Learn matching rule** field to specify whether to create a matching rule. This feature works only for items and G/L accounts. Item references are created for items and text to account mappings are created for G/L accounts.
1. Select **OK**.
1. A purchase order line is created on the purchase order, and you can map it on the **Purchase Order Lines** FastTab on the **Purchase Order Matching** page.

> [!NOTE]
> If you change the quantity, the unit amount recalculates to the same total amount as the original invoice line.

#### Match lines from an e-document  

To match the lines on the **E-Document** page, follow these steps:  

1. Select the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Documents**, and then select the related link.
1. Select the **E-Document** that you want to match.
1. Choose the **Match Purchase Order** action to open the **Purchase Order Matching** page.  
1. Repeat the same steps that you used when you started matching from purchase orders.

## Overview of e-document statuses

The **Accountant** Role Center offers an overview of all e-documents in the company. There, you can find e-document activities that have the following statuses:

- **Incoming e-documents:**
  - Processed
  - In Progress
  - Error

To learn how to use the Role Center, go to [Change the role](ui-change-basic-settings.md#change-the-role).

## Related information

[Set up e-documents](finance-how-setup-edocuments.md)  
[Match purchase invoice drafts to purchase orders](match-purchase-invoice-drafts-to-orders.md)  
[Use e-document in the sales process](finance-how-use-edocuments.md)  
[Extending e-documents functionality](/dynamics365/business-central/dev-itpro/developer/devenv-extend-edocuments)  
[Financial Management](finance.md)  
[Invoice sales](sales-how-invoice-sales.md)  
[Record purchases with purchase invoices and orders](purchasing-how-record-purchases.md)  
[Work with Business Central](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
