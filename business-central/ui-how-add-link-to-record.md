---
    title: Add Attachments, Links, and Notes on Records| Microsoft Docs
    description: Attach a hyperlink to a document or website to a specific record, such as a customer or document.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe
---
# Manage Attachments, Links, and Notes on Cards and Documents

In the FactBox on most cards and documents, you can attach files, add links, and write notes. For links and notes, you can also do this on the list page by first selecting the related line.

To view or change any of these attached information types, you must first open the **Attachments** tab in the FactBox. The number behind the tab title indicates how many attached files, links, or notes exist for the card or document.

Attachments, links, and notes stay attached as the card or document is processed into other states, such as from an ongoing sales order to a posted sales invoice. However, none of the attachment types are output from the system, for example, when printing or when saving to a file.

> [!NOTE]
> When you partially ship and invoice a sales order or purchase order, the attachment will only be attached to the final invoice of that order. Likewise, when you invoice using the Deferrals feature, the attachment is only attached to the G/L entries for the document but not for the deferral entries.

## To attach a file to a purchase invoice
You can attach any type of file, containing text, image, or video, to a card or document. This is useful, for example, when you want to store a vendor's invoice as a PDF file on the related purchase invoice in [!INCLUDE[d365fin](includes/d365fin_md.md)].

> [!NOTE]
> Files attached with the Incoming Documents feature are not included on the **Attachments** tab. For more information, see [Incoming Documents](across-income-documents.md).

The following procedure is based on a purchase invoice. The steps are similar for all other supported documents and cards.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and then choose the related link.
2. Open the sales order that you want to attach a file to.
3. In the FactBox, open the **Attachments** tab.
4. Choose the value behind the **Documents** field, such as "0".
5. On the **Attached Documents** page, in the **Attachment** field, choose the **Select File** button.
5. Select a file from any location, and then choose the **Open** button.

The file is now attached to the purchase invoice.

## To save a document as a PDF attachment
Whenever you need to save a document as a file, you can use the **Attach as PDF** action to capture the current document content as a PDF file attached to the FactBox of the document. This is useful, for example, when documents follow multiple steps in a process, such as a sales process or an approval workflow, and you want to refer to a printout of the previous step.

The following procedure is based on a sales order. The steps are similar for all supported documents.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.
2. Select a sales order, and then choose the **Attach as PDF** action.

A PDF file with the current content of the sales order is added to the **Attachments** tab in the FactBox. 

## To add a link from an item card
You can add a link from a card or document to any URL or path. This is useful, for example, when you want to link an item card with the supplier's item catalog.

The following procedure is based on an item card. The steps are similar for all other supported cards and documents.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
2. Select the item that you want to add a link from, and then choose the **Attachments** tab in the FactBox.
3. In the **Links**, choose the **+** icon.
4. In the **Link Address** field, enter the link.

    The link must be a valid internet or intranet URL.

5. In the **Description** field, enter any information about the link.  
6. Choose the **OK** button.

The link is now attached to the item card.  

## To write a note on a sales order
You can write a note on a document or card, for example, to communicate special instructions to other users of the document or card. You can include file links and URLs in notes.

> [!NOTE]
> Notes on the **Attachments** tab are not related to internal notes functionality, which is mainly used to communicate between workflow users. For more information, see [Setting Up Workflow Notifications](across-setting-up-workflow-notifications.md).

The following procedure is based on a sales order. The steps are similar for all other supported documents and cards.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.
2. Select the sales order that you want to write a note on, and then choose the **Attachments** tab in the FactBox.
3. In the **Notes** section, choose the **+** icon.
4. In the **Note** field, write any text, such as "This is an urgent order.".
5. Choose the **OK** button.

The note is now attached to the sales order.

## See Also  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Incoming Documents](across-income-documents.md)  
[Setting Up Workflow Notifications](across-setting-up-workflow-notifications.md)  
