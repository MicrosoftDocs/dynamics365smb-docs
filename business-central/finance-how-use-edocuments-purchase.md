---
title: Use e-documents in the purchase process
description: Learn how to use the e-document functionality that is related to purchase invoices and orders.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: electronic document, electronic invoice, e-document, e-invoice, receive, purchase, matching, mapping, Copilot
ms.search.form: 50, 51, 138, 6103, 6133, 6121, 6167, 9307, 9308
ms.date: 01/21/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: soumramani
---

# Use e-documents in the purchases process

You can use configured electronic documents (e-documents) with the purchase documents.

The following purchase documents can be used with e-documents functionality:  

- Purchase invoices
- Purchase orders (from version 24.0)
- Purchase credit memos
- General journals

> [!NOTE]
>
> From [!INCLUDE[prod_short](includes/prod_short.md)] version 24.0, it's possible to connect **Purchase Orders** with the received **E-Documents**.
> [!NOTE]
> When you receive an electronic document from a specific vendor, Business Central tries to match this e-document with the existing vendor in the system by verifying the following information in this order:
>
> 1. **GLN** (from the Vendor card)
> 1. **VAT Registration No.** (from the Vendor card)
> 1. **Participation Identifier** from the **Service Participant** page (using the **E-Document Service Participation** field from the Vendor card)
> 1. **Name** and **Address** (from the Vendor card)

## E-documents in purchases

The receipt of purchase e-documents in Dynamics 365 Business Central can be done as a batch job or manually.  

### Set up vendors to work with different purchase documents  

Follow these steps to configure vendors to work properly with incoming electronic invoices:

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then select the related link.
2. Choose the vendor you want to configure.
3. In the **Receiving** FastTab, find the **Receive E-Document To** field to specify the default purchase document to be generated from the received e-document.

   > [!NOTE]
   >
   > - In the **Receive E-Document To** field, users can either select a **Purchase Invoice** or **Purchase Order** based on what they would like to create from the received e-invoice. This selection doesn't affect the creation of corrective documents; in both scenarios, the system generates a **Credit Memo**.
   >
   > - If the user chooses the **Purchase Order** option in the **Receive E-Document To** field, the system tries to update one of the existing purchase orders, but if the purchase order for a vendor in the received **E-Document** doesn't exist, [!INCLUDE[prod_short](includes/prod_short.md)] creates a new **Purchase Order**, using the same approach as creating the new **Purchase Invoices** explained in this page later.

4. Choose one of the options you want to use for the selected vendor.
5. Close the page.

### To work with purchase invoices  

#### Run the batch job  

> [!NOTE]
> This batch job is for automated collection of your incoming invoices. It can work only in a country or region where the functionality exists.  

Every time a **Job Queue** is selected to run, if the external service has incoming invoices that were sent from your vendor, the system collects and imports those invoices. To complete the process, follow these steps:

1. After the batch job finishes running, the newly imported invoices are listed on the **E-Documents** page, together with their basic detail information.
2. To view more details, open a specific e-document.
3. If there are no errors or issues in the e-document, the **Record** field maps the document number of the purchase invoice if it's configured on the **Vendor Card** page (that the system automatically created). To open the document, select the link.

   > [!NOTE]
   > This system-created document isn't the posted document.

4. To go directly to the purchase document, select the **Record** field. After you open the **Purchase Invoice** page, check the document. If everything is correct, post the document.  
5. When you post the purchase document, the **Record** field on the **E-Document** is updated from **Invoice** to **Purchase Invoice**, and the number of the posted purchase document is available. You can select the number to open the posted purchase invoice.

Details about logs are the same as they are in the sales process for e-documents.  

Because errors in the sales process are mostly related to the availability of the service, the incoming document can contain multiple reasons. The most common reason for an error is that the system can't recognize the lines on the e-document that you got from your vendor. Therefore, it can't enter lines in your purchase invoice.

There are two common errors:  

- If you want to use this specific line from your vendor invoice that was directly posted to the general ledger (G/L) account, you must correctly configure the **Mapping Text** value. To bypass this error, if you want to use G/L accounts, select the **Map Text to Account** to create a specific mapping of the **Mapping Text** value with the **Debit Acc. No.** value that you want to use. Learn more about account mapping [here](finance-how-use-edocuments-purchase.md#to-map-text-on-an-e-document-to-a-specific-vendor-account).  
- If you want to track the inventory and use lines from your vendor invoice to fill in the items on your document lines, you must correctly configure the **Item Reference No.** value. To bypass this error, map the external item with your item numbers by using the item reference list. Learn more in [use item references](inventory-how-use-item-cross-refs.md).

After you fix the errors and warnings, you can manually specify when the system should create a purchase invoice based on your setup by selecting **Create Document**.

#### To map text on an e-document to a specific vendor account

To map lines with expenses for E-Documents, you need to map description with **G/L Account**. Then, use the **Map Text to Account** action to link specific text on a vendor invoice from the **E-Document Service** to a vendor account. Any part of the E-document description that exists as a mapping text means that the **Vendor No.** field on resulting document or journal lines of type **G/L Account** are filled with the vendor in question.

In addition to mapping to a vendor account or G/L accounts, you can also map text to a bank account. Use this option for electronic documents related to expenses that are paid. It is for e-documents for which you want to create a general journal line that is ready to post to a bank account.

1. Select the relevant E-Document line with the displayed error message and then choose **Map Text to Account** action. The **Text-to-Account Mapping** page displays.
2. In the **Mapping Text** field, enter any text that appears on vendor invoices for which you want to create purchase documents or journal lines. You can enter up to 50 characters.
3. In the **Vendor No.** field, enter the vendor that the resulting purchase document or journal line will be created for.
4. In the **Debit Acc. No.** field, enter the debit-type G/L account that is inserted on resulting purchase document or journal line of type G/L Account.

   > [!NOTE]
   > Don't use the **Credit Acc. No.**, **Bal. Source Type, and **Bal. Source No.** fields with E-documents.

5. Repeat steps 2 through 5 for all error messages on E-documents that you want to automatically create **G/L Accounts** and documents for.  

#### Manually import invoices  

To manually import external e-documents, follow these steps:

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Service**, and then select the related link.
2. On the **E-Document Service** page, select the active service.
3. Select **Receive**, and upload the e-document file that you got from the vendor.
4. If an error message occurs, open the e-document to fix the issues.
5. When you finish fixing the issues, in the **Import Manually** group, select **Create Document**.  
6. After the document is created in [!INCLUDE[prod_short](includes/prod_short.md)], using a batch job doesn't change the way you view it.

#### Work with attachments  

Peppol and similar e-invoicing files are machine-readable formats and not easy for human reading. To improve reading, Peppol made it possible to embed a PDF file into the Peppol BIS 3 format as a binary object. If your incoming Peppol BIS 3 file has an embedded PDF, Business Central automatically processes it and adds the PDF as an attachment to the purchase document after creating it.

## E-documents with purchase orders  

### Link purchase orders with the received e-documents

If your **Vendor** configured the **Received E-Document To** field to work with **Purchase Orders**, once an electronic document is created in [!INCLUDE[prod_short](includes/prod_short.md)] (manually or from external end point), [!INCLUDE[prod_short](includes/prod_short.md)] does the following steps:  

1. If the **Purchase Order** for this particular vendor exists and there's a purchase order number in the receive **E-Document** file, [!INCLUDE[prod_short](includes/prod_short.md)] automatically links this **E-Document** with the mentioned **Purchase Order**, and the **Document Status** of this **E-Document** is set to **In Progress**, and the **E-Document Status** in the **Service Status** subpage is set to **Order linked**. This link is visible in the **Document** field on this specific **E-Document**. If you need to change the **Purchase Order** linked automatically, you can do it using the **Update Purchase Order Link** action and manually select one of the existing purchase orders for this vendor. You can only do it before matching the lines between **E-Document** and **Purchase Order**.  

2. If the **Purchase Order** for this particular vendor exists but there's no purchase order number in the received **E-Document** file, [!INCLUDE[prod_short](includes/prod_short.md)] offers the possibility to choose one of the existing purchase orders when and if you uploaded this document manually. This condition opens the **Purchase Orders** list with orders only for the vendor from whom you received the **E-Document**. You need to select the **Purchase Order** you want and then select **OK**. If you failed to select the correct **Purchase Order**, or obtained the **E-Document** automatically from an external endpoint using the **Job Queue**, a new **E-Document** isn't linked to any purchase document. The **Document Status** then shows **Error**, and the **E-Document Status** in the **Service Status** subpage also shows **Imported document processing error**. To finish linking with the **Purchase Order**, select the **Update Purchase Order Link** action and choose one of the existing purchase orders for this vendor.

3. If the **Purchase Order** for this particular vendor doesn't exist when a new **E-Document** is created, [!INCLUDE[prod_short](includes/prod_short.md)] creates a new **Purchase Order**, using the same model of creation that already exists for new **Purchase Invoices**. The **Document Status** of this **E-Document** is set to **Processed**, and the **E-Document Status** in the **Service Status** subpage is set to **Imported document created**. After which, this link is visible in the **Document** field on this specific **E-Document**.

### Matching lines from received e-document with purchase order  

You can match your received electronic documents with purchase orders' lines from two different places: from the **E-Document** page or from the **Purchase Order** page. The easiest way to locate the already linked **Purchase Orders** is to use the **Linked Purchase Orders** tile as a part of **E-Document Activities**. All nonlinked documents can be found using the tile **Waiting Purchase E-Invoices** where you have a list of **E-Documents** that you need to review. The **E-Document Activities** with these two tiles can be found in the following **Role Centers**: Business Manager Evaluation, Business Manager, Accountant, Inventory Manager, and Shipping and Receiving.

> [!TIP]
> There are two ways to match lines. One way is to do it manually, as described in the article. The other way is to use the **E-document matching assistance with Copilot**. The E-document matching assistance feature helps you match received electronic invoices with existing purchase order lines by using large language modules (LLM) model. Learn more about using Copilot in [Map e-documents to purchase order lines with Copilot](map-edocuments-with-copilot.md).
> [!NOTE]
> If the VAT percentage differs between the incoming document and the company's VAT percentage, matching documents can't be used in a multi-country environment.  

#### Matching lines from purchase order  

You can match the lines from the **Purchase Orders** list or from one of the opened **Purchase Orders**. To begin process, use the following steps:  

1. Select the **Linked Purchase Orders** tile on your Role Center if there's any number.
2. Choose one of the two options for matching:

   - If you want to match the lines from the **Purchase Orders** list, select the **Purchase Order** line that you want to match and select the **Map E-Document Lines** action.  
   - If you want to first open the **Purchase Order**, open the document and then select the **Map E-Document Lines** action.

3. Because both options have the same process, the **Purchase Order Matching** page opens with the following content:

    1. In the header you can find the following information, which can help you to map the lines easier:

       |Field name |Description |
       |--------|-----------------|
       |Vendor Name |Specifies the vendor’s name of the electronic document. |
       |E-Document No. |Specifies the linked electronic document number. |
       |E-Document Date |Specifies the linked electronic document date.  |
       |E-Document Amount |Specifies the linked e-document total amount including VAT. |

    2. In the lines, you can find the lines imported from the **E-Document** file on the left side and the lines from the existing **Purchase Order** on the right.  
    3. All lines on both sides have item numbers and descriptions, together with the **Direct Unit Cost** and **Line Discount %**.  
    4. On the **Imported Lines** side, you can also locate the **Quantity** field as a total quantity from e-invoice and the **Matched Quantity** field specifying the quantity that already matched to the purchase order lines.
    5. On the **Purchase Orders Lines** side, you can also find the **Available Quantity** as the quantity that can be matched to this line (received, but not invoiced quantity) and **Qty. to Invoice**, specifying the quantity that is already matched to this line.
    6. To match lines, select the lines on both sides that you want to match and select the **Match Manually** action. The matched lines are marked in green.
    7. It's possible to match one to one, but it's also possible to match many to one or one to many, selecting more lines on one or another side before choosing the **Match Manually** action.
    8. You can also select the **Match Automatically** action to automatically match all lines with the same **Type**, **No.**, **Unit Price**, **Discount**, and **Unit of Measure**.
    9. If you make a mistake, you can select the **Remove Match** action to remove the matched lines on the purchase order side or select the **Reset Matching** action to reset all that match.
    10. If your **E-Document** has many lines, you can select the **Show Pending Lines** action during the matching process to remove all the e-document lines if they're already matched. If you need to view all the lines, you can always select the **Show All Lines** action. 

4. After you finish the matching, you need to select the **Apply To Purchase Order** action.
5. After you apply the matching to the **Purchase Order**, [!INCLUDE[prod_short](includes/prod_short.md)] will update the following fields:

    1. **Vendor Invoice No.** and **Document Date** on the document header are updated with values from the electronic document that you'd received and linked. 
    2. **Qty. to Invoice** in lines are updated with the values from the **Qty. to Invoice** column from the **Purchase Order Matching** page based on the match you did.
    3. Now you can post the document by choosing the **Post** action.  
    4. After you post the document, the **Document** field on the **E-Document** page changes value to relate to the **Posted Purchase Invoice**.
    5. Close the page.  

> [!IMPORTANT]
> By default, you can match only the lines that have the same total amount in both documents. That means **Direct Unit Cost** together with the applied Line **Discount %** must be the same, because in one document you can have an amount without discount and in another with discount.  

If you want to add some tolerance and allow the difference between lines in **E-invoice** and **Purchase Order**, follow these steps:

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchases & Payables Setup**, and then select the related link.  
2. You want to allow tolerance in the **E-Document Matching Difference %** field, specifying the maximum allowed percentage of cost difference when matching an incoming **E-Document** line with the **Purchase Order** line.
3. This setup applies to all the matching lines, but again considering tolerance for the total amount, as for **Direct Unit Cost** together with applied **Line Discount %**.  
4. Close the page.

#### Matching lines from e-document  

You can match the lines on the **E-Document** page. To begin, use the following steps:  

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Documents**, and then select the related link.
2. Select the **E-Document** that you want to match.
3. Choose the **Match Purchase Order** action to open the **Purchase Order Matching** page.  
4. Repeat the same steps that you used when you started matching from purchase orders.

## Overview of e-document statuses

To get a better overview of all e-documents in the company, you can select the **Accountant** role center where e-document statuses exist. There, you can find e-document activities that have the following statuses:

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
