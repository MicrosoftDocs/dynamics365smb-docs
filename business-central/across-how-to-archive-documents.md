---
    title: How to Archive Sales and Purchase Documents | Microsoft Docs
    description: You can archive sales and purchase orders, quotes, return orders, and blanket orders, and you can use the archived document to recreate the document that it was archived from.
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
# Archive Documents
You can archive sales and purchase orders, quotes, return orders, and blanket orders, for example because you want to save a copy of a document for reuse later. You can archive a sales or purchase document several times, saving a different archived version each time.

For archived documents where the original still exists and is not posted, you can use the **Restore** function to overwrite the original with the archived version of the document. This is practical if you need to restore the contents of a document to an earlier state.

For archived documents where the original is deleted, you can only reuse the content by copying the data, for example with the **Copy from Document** function.   

## To set up automatic document archiving  
You can set up automatic archiving of sales and purchase orders, quotes, blanket orders, and return orders, before you delete documents.

The following procedure describes how to set up automatic archiving of sales documents. The steps are similar for purchase documents.
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales & Receivables Setup**, and then choose the related link.
2. On the **Sales & Receivables Setup** page, fill in the fields as follows.

|Field|Description|
|-----|-----------|
|**Archiving Sales Quotes**|**Never** to never archive sales quotes when they are deleted. **Question** to prompt the user to choose whether to archive sales quotes when they are deleted. **Always** to archive sales quotes automatically when they are deleted.|
|**Archiving Blanket Sales Orders**|Select to archive blanket sales orders automatically each time they are deleted.|
|**Arch. Orders and Ret. Orders**|Select to automatically archive sales orders each time they are deleted.|

## To archive a sales order
The following procedure describes how to archive a sales order. The steps are similar for all orders, blanket orders, return orders, and quotes.

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
2.  Open a sales order that you want to archive.  
3.  Choose the **Archive Document** action.

The sales order is archived. You can view it on the **Archived Sales Orders** page.

## To restore a non-posted sales order from the archive
The following procedure describes how to bring the contents of an archived sales order back to the original sales order. This is only possible when the original document has not been posted. The steps are similar for all orders, blanket orders, return orders, and quotes.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Archived Sales Orders**, and then choose the related link.
2. Select the archived sales order, or version of it, that you want to restore, and then choose the **Restore** action.  

The contents of the original sales order is replaced with that of the selected archived version.

## To delete archived sales orders
The following procedure describes how to delete archived sales orders. The steps are similar for other archived sales and purchase documents.

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Delete Archived Sales Order Versions**, and then choose the related link.  
2.  On the **Delete Archived Sales Order Versions** page, select the appropriate filters.  
3.  Choose the **OK** button.

## See Also
[Track Document Lines](across-how-to-track-document-lines.md)  
[Sales](sales-manage-sales.md)  
[General Business Functionality](ui-across-business-areas.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
