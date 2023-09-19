---
    title: Print Inventory Picking List from Sales Order
    description: You can print an inventory picking list directly from a sales order, sales, invoice, and other outbound sales documents.
    author: brentholtorf
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/25/2021
    ms.author: bholtorf

---
# Print the Picking List

You can print an inventory picking list directly from a sales order and other documents that initiate the shipment of items.

This report is typically used in companies without dedicated functionality for warehouse management, so that an inventory worker can view or print the picking list from the related sales document. In companies with higher volume or more complex processes, shipping and picking are planned and performed in dedicated warehouse documents. Learn more at [Outbound Warehouse Flow](design-details-outbound-warehouse-flow.md).

## To print a picking list from a sales order

The following procedure is based on a sales order. The steps are similar for all other documents that can be used to initiate shipment of items, such as a transfer order.

1. Choose the ![Search for Page or Report.](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales Orders**, and then choose the related link.  
2. Open the sales order that you want to pick items for.  
3. Choose the **Report** action, and then choose the **Picking List by Order** action.  
4. Choose the **Print** button to print the picking list or choose the **Preview** button to view it on the screen.

You can also save the picking list as a document, for example, to send to someone or to add as an attachment to the sales order. Learn more at [Manage Attachments, Links, and Notes on Cards and Documents](ui-how-add-link-to-record.md).

> [!NOTE]
> If you used the **Explode BOM** function on the sales order, then only the components of the related assembly item are shown in the report. Learn more at [Work with Bills of Material](inventory-how-work-BOMs.md).

## See Also

[Inventory](inventory-manage-inventory.md)  
[Outbound Warehouse Flow](design-details-outbound-warehouse-flow.md)
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
