---
    title: Design Details - Internal Warehouse Flows | Microsoft Docs
    description: The flow of items between bins at a company location centers on picking components and putting away end items for assembly or production orders and ad-hoc movements, such as bin replenishments, without a relation to source documents.
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
# Design Details: Internal Warehouse Flows
The flow of items between bins at a company location centers on picking components and putting away end items for assembly or production orders and ad-hoc movements, such as bin replenishments, without a relation to source documents. The scope and nature of the involved activities vary between basic and advanced warehousing.  

 Some internal flows overlap with inbound or outbound flows. Some of this overlap is shown as steps 4 and 5 in the graphical diagrams for advanced inbound and outbound flows respectively. For more information, see [Design Details: Inbound Warehouse Flow](design-details-outbound-warehouse-flow.md).  

## Internal Flows in Basic Warehousing  
 In basic warehouse configuration, the flow of items between bins inside the company centers on picking component and putting away end items for production or assembly orders and ad-hoc movements, such as bin replenishments, without relation to source documents.  

### Flows to and from Production  
 The main integration between production orders and basic warehouse activities is represented by the ability to pick production components with the **Inventory Pick** or the **Inventory Movement** pages.  

> [!NOTE]  
>  On the **Inventory Pick** page, the component consumption is posted together with the pick posting. By using the **Inventory Movement** page, only bin adjustments are registered, no item ledger posting occurs.  

 In addition to component handling, the integration is represented by the ability to put produced items away with the **Inventory Put-away** page.  

 The **To-Production Bin Code**, **From-Production Bin Code**, and **Open Shop Floor Bin Code** fields on the location card or the machine/work center cards define default flows to and from production areas.  

 For more information about how component consumption is flushed from the To-Production or Open Shop Floor bins, see the “Flushing Production Components in the Warehouse” section in this topic.  

### Flows to and from Assembly  
 The main integration between assembly orders and basic warehouse activities is represented by the ability to move assembly components to the assembly area.  

 While no specific warehouse functionality exists for putting assembly items away, the bin code on the assembly order header may be set to a default put-away bin. Posting the assembly order then functions like posting a put-away. The warehouse activity to move assembly items into the warehouse can be managed on the **Internal Movement** page, with no relation to the assembly order.  

 The following assembly flows exist.  

|Flow|Description|  
|----------|---------------------------------------|  
|Assemble-to-stock|The components are needed on an assembly order where the output is stored in the warehouse.<br /><br /> This warehouse flow is managed on the **Inventory Movement** page. One take line specifies where to take the components. One place line specifies where to place the components.|  
|Assemble-to-order|The components are needed on an assembly order that is linked to a sales order that is shipped when the sold item is assembled.|  

> [!NOTE]  
>  If items are assembled to order, then the inventory pick of the linked sales order triggers an inventory movement for all the involved assembly components, not just for the sold item as when shipping inventory items.  

 The **To-Assembly Bin Code**, **From-Assembly Bin Code**, and **Asm.-to-Order Shpt. Bin Code** fields on the location card define default flows to and from assembly areas.  

> [!NOTE]  
>  The **Asm.-to-Order Shpt. Bin Code** field functions as the from-assembly bin in assemble-to-order scenarios.  

### Ad-Hoc Movements  
 In basic warehousing, the movement of items from bin to bin without relation to source documents is performed on the **Internal Movement** page, which functions together with the **Inventory Movement** page.  

 Another way to move items ad hoc between bins is to post positive entries in the **New Bin Code** field on the **Item Reclass. Journal** page.  

## Internal Flows in Advanced Warehousing  
 In advanced warehouse configurations, the flow of items between bins inside the company centers on picking component and putting away end items for production orders and picking components for assembly orders. In addition, internal flows occur as ad-hoc movements, such as bin replenishments, without relation to source documents.  

### Flows To and From Production  
 The main integration between production orders and advanced warehouse activities is represented by the ability to pick production components, on the **Warehouse Pick** page and the **Pick Worksheet** page, and the ability to put produced items away with the **Whse. Internal-Put-away** page.  

 Another integration point in production is provided with the **Warehouse Movement** page, together with the Movement Worksheet page, which enables you to place components and take produced items for released production orders.  

 The **To-Production Bin Code**, **From-Production Bin Code**, and **Open Shop Floor Bin Code** fields on the location card or the machine/work center cards define default flows to and from production areas.  

 For more information about how component consumption is flushed from the To-Production or Open Shop Floor Bins, see the “Flushing Production Components in the Warehouse” section in this topic.  

### Flows to and from Assembly  
 The main integration between assembly orders and advanced warehouse activities is represented by the ability to pick assembly components, both with the **Warehouse Pick** page and the **Pick Worksheet** page. This functionality works just like when picking components for production orders.  

 While no specific warehouse functionality exists for putting assembly items away, the bin code on the assembly order header may be set to a default put-away bin. Posting the assembly order then functions like posting a put-away. The warehouse activity to move assembly items into the warehouse can be managed on the **Movement Worksheet** page or the **Whse. Internal Put-away** page, with no relation to the assembly order.  

> [!NOTE]  
>  If items are assembled to order, then the warehouse shipment of the linked sales order triggers a warehouse pick for all the involved assembly components, not just for the sold item as when shipping inventory items.  

 The **To-Assembly Bin Code** and **From-Assembly Bin Code** fields on the location card define default flows to and from assembly areas.  

### Ad-Hoc Movements  
 In advanced warehousing, the movement of items from bin to bin without relation to source documents is managed on the **Movement Worksheet** page and registered in the Warehouse Movement page.  

## Flushing Production Components in the Warehouse  
 If set up on the item card, components picked with warehouse picks are posted as consumed by the production order when the warehouse pick is registered. By using the **Pick + Forward** method and the **Pick + Backward** flushing method, the pick registration triggers the related consumption posting when the first operation starts or when the last operation finishes, respectively.  

 Consider the following scenario based on the [!INCLUDE[d365fin](includes/d365fin_md.md)] demonstration database, WHITE location.  

 A production order for 15 PCS of item LS-100 exists. Some of the items on the component list must be flushed manually in a consumption journal, and other items on the list can be picked and flushed automatically using the **Pick + Backward** flushing method.  

> [!NOTE]  
>  **Pick + Forward** only works if the second production routing line operation uses a routing link code. Releasing a planned production order initiates forward flushing of components set to **Pick + Forward**. However, the flushing cannot take place until the pick of the components is registered, which again can only take place when the order is released.  

 The following steps describe the involved actions by different users and the related response:  

1.  The shop floor supervisor releases the production order. Items with **Forward** flushing method and no routing link code are deducted from the open shop floor bin.  
2.  The shop floor supervisor chooses the **Create Warehouse Pick** button on the production order. A warehouse pick document is created pick for items with **Manual**, **Pick + Backward**, and **Pick + Forward** flushing methods. These items are placed in the To-Production bin.  
3.  The warehouse manager assigns the picks to a warehouse worker.  
4.  The warehouse worker picks the items from appropriate bins and places them in the To-Production bin or in the bin specified on the warehouse pick, which may be a work center or machine center bin.  
5.  The warehouse worker registers the pick. The quantity is subtracted from the pick bins and added to the consumption bin. The **Qty. Picked** field on the component list for all picked items is updated.  

    > [!NOTE]  
    >  Only the quantity that is picked can be consumed.  

6.  The machine operator informs the production manager that the end items are finished.  
7.  The shop floor supervisor uses the consumption journal or production journal to post the consumption of component items that use either **Manual** flushing method or **Forward** or **Pick + Forward** flushing methods together with routing link codes.  
8.  The production manager posts the output of the production order and changes status to **Finished**. The quantity of component items that use **Backward** flushing method is deducted from the open shop floor bin, and the quantity of component items that use **Pick + Backward** flushing method is deducted from the To-Production bin.  

 The following illustration shows when the **Bin Code** field on the component list is filled according to your location or machine/work center setup.  

 ![Overview of when/how the Bin Code field is filled in](media/binflow.png "Overview of when/how the Bin Code field is filled in")  

## See Also  
 [Design Details: Warehouse Management](design-details-warehouse-management.md)
