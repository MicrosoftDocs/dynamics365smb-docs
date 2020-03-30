---
    title: Service Posting | Microsoft Docs
    description: Service posting functionality lets you process your documents efficiently and maintain successful customer service policy. You can create and update posted documents, and create ledger entries both in the service area and in other modules to ensure the correct update.
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
# Service Posting
Service posting functionality lets you process your documents efficiently and maintain successful customer service policy. You can create and update posted documents, and create ledger entries both in the service area and in other modules to ensure the correct update.  

> [!NOTE]  
>  The following describes service posting regardless of how items are physically handled in the warehouse.  
>   
>  In a location that is not set up to require warehouse handling, you perform the posting actions directly from the **Service Lines** page. In locations that involve warehouse handling, the described posting actions, except Ship and Consume, are performed indirectly through varying warehouse ship functions, depending on setup. For more information, see [Pick Items with Inventory Picks](warehouse-how-to-pick-items-with-inventory-picks.md).  

## Ship  
The ship option lets you register the relevant items and time entered on the lines of a service order after you complete the service. A posted shipment is created and updates occur in the Inventory module and other modules in [!INCLUDE[d365fin](includes/d365fin_md.md)] to reflect that the items have been taken out of the inventory and sent to the customer. In particular, the item ledger entries, value ledger entries, service ledger entries, and warranty ledger entries are produced.  

If the location is set up to require warehouse handling, then the shipping and moving of service line items functions in the same ways as for other source documents. The only difference is that service line items can be consumed either externally or internally, which requires two different release functions.

## Invoice  
You have to use the invoice option to issue an invoice to the customer you want to charge for the service. Usually, it is the difference between the shipped quantity registered by the **Post Shipment** function and the consumed quantity registered by the **Post Consumption** function that is subject to invoice. You cannot invoice what has not been shipped. When you run the **Post Invoice** function, you create a posted service invoice and update the documents posted before to make them consistent with the quantities that are contained in the issued invoice. Like in other posting procedures, the relevant ledger entries that includes general ledger entries, are generated.  

## Ship and Invoice  
The ship and invoice option lets you issue both a service shipment and an invoice at the same time.  

## Ship and Consume  
With the ship and consume option, you can register and post items, costs, or hours that have been used for servicing but that cannot be included in the invoice to the customer. An invoice is not issued, but you can issue both a service shipment and service consumption at the same time to reflect the fact that some items or hours have been given to the customer free of charge. The corresponding ledger entries are also created to register consumption.  

> [!NOTE]  
>  The service posting procedure enables you to perform partial posting. You can create a partial shipment or a partial invoice by filling in the **Qty. to Ship** and **Qty. to Invoice** fields on the individual service lines of the service orders before you post. Note that you cannot create an invoice for something that is not shipped. That is, before you can invoice, you must have registered a shipment, or you must choose to ship and invoice at the same time.  

After the posting has been completed, you will be able to view the posted service documents from the corresponding **Posted Service Shipment** and **Posted Service Invoice** pages. The posted entries created can be seen in various pages that contain posted entries, such as **G/L Entries**, **Item Ledger Entries**, **Warehouse Entries**, **Service Ledger Entries**, **Job Ledger Entries**, and **Warranty Ledger Entries**.  

## To view information about a posted service document  
When you post a service invoice, a service shipment, or a service credit memo, the information on the document is transferred to the **Posted Service Invoice**, **Posted Service Shipment**, or **Posted Service Credit Memo** pages respectively. You cannot enter, change, or delete anything in these pages. You can print a shipment, invoice, or credit memo from these pages.  

The following procedure uses a posted service invoice as an example, but the same procedure can apply to posted service shipments and posted credit memos.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Service Invoice**, and then choose the related link.  
2. Open the posted service invoice you want to view.  
3. To get an overview of the posted invoice, choose the **Statistics** action.  

    The **Service Order Statistics** page opens. The page displays information such as quantity, amount, VAT, cost, profit, and customer credit limit for the posted document.

## See Also  
[Post Service Orders](service-how-to-post-service-orders.md)   
[Create Service Orders](service-how-to-create-service-orders.md)
