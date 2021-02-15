---
    title: How to Print an Inventory Picking List from a Sales Order
    description: You can print an inventory picking list directly from a sales order, sales, invoice, and other outbound sales documents.
    author: SorenGP
    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 10/01/2020
    ms.author: edupont

---
# Print the Picking List
You can print an inventory picking list directly from a sales order, a sales invoice, or any other document that initiates shipment of items.

This report is typically used in companies without dedicated functionality for warehouse management, so that an inventory worker can simply view or print the picking list from the related sales document. In companies with higher volume or more complex processes, picking is planned and performed in dedicated warehouse documents. For more information, see [Pick Items](warehouse-pick-items.md).

## To print a picking list from a sales order  
The following procedure is based on a sales order. The steps are similar for all sales documents that can be used to initiate shipment of items.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales Orders**, and then choose the related link.  
2. Open the sales order that you want to pick items for.  
3. Choose the **Report** action, and then choose the **Picking List by Order** action.  
4. Choose the **Print** button to print the picking list or choose the **Preview** button to view it on the screen.

You can also save the picking list as a document, for example, to send to someone or to add as an attachment to the sales order. For more information, see [Manage Attachments, Links, and Notes on Cards and Documents](ui-how-add-link-to-record.md).

> [!NOTE]
> If you used the **Explode BOM** function on the sales order, then only the components of the related assembly item are shown in the report. For more information, see [Work with Bills of Material](inventory-how-work-BOMs.md).

## See Also  
[Inventory](inventory-manage-inventory.md)  
[Pick Items](warehouse-pick-items.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)   


[!INCLUDE[footer-include](includes/footer-banner.md)]