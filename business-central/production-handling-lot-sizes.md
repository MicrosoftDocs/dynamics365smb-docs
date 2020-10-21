---
    title: Handling Lot Sizes | Microsoft Docs
    description: This topic describes different ways to handle lot sizes. 
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 10/01/2020
    ms.author: bholtorf

---

# Handling Lot Sizes in Production
From a quantity perspective, the way you produce items might not correlate to how sell them. For example, you might produce hundreds of items at the same time, but ship each item individually. There are few nuances you should know when configure production.

## Units of Measure in Production Bill of Materials
Even if you decide to use PCS or Liters as the base unit of measure (UoM) <!--is this on the item?-->, you can use different ones in production bills of materials (BOMs). For example, you can create a BOM and specify the unit of measure as pallet or ton. This comes in handy when your machines or raw components dictate the volume. For example, you rarely bake a single muffin because it is difficult to use a portion of an egg. Instead, you bake a batch of muffins to reduce waste. For more information, see [Create Production BOMs](production-how-to-create-production-boms.md).

From a routing perspective, you can specify a lot size on routing lines so that the components of a BOM match the capacity of the machines that produce the items. The lot size allocates production capacity for production order. 

> [!NOTE]
> This works well when the quantity on a production order is a factor of the lot size on the route. For example, if your baking sheet can hold 10 muffins, you should bake 10, 20, 30, and so on, and not 5 nor 15. 
>
>The time specified in **Setup Time** field of the routing line will happen only one time, even if there are several lots. For example, so that you don’t need to warm the oven for the second lot of muffins. For more information, see [Create Routings](production-how-to-create-routings.md).

Do not confuse the lot size defined for routings with the lot sizes for items or stockkeeping units. Those values are used for a different purpose, and do not affect production capacity. 

For items and stockkeeping units, lot sizes have the following effects on cost calculation and resource planning:

* For standard cost calculation, if you enable **Cost Incl Setup** on the **Manufacturing Setup** page, the cost for the setup is added to the standard cost. If you specify a lot size, the setup cost for a single item will be reduced according to one lot size. For example, if your lot size is 10, and it takes 15 minutes to heat the oven, the cost of the fuel will be allocated to the 10 muffins as roughly 1.5 minutes. 

Setup costs are handled differently from a standard cost and capacity allocation perspectives. For example, if your production order calls for 20 muffins, the standard cost of each muffin includes 15 minutes divided by the lot size specified on the item. However, in reality you will heat oven only one time and bake all 20 muffins, so the real setup cost will be 15 minutes divided by the quantity on the order (20) and will lead to variation. For more information, see [Managing Inventory Costs](finance-manage-inventory-costs.md). <!--not sure that I got this part right seems to repeat the first example.-->

* For resource planning, the lot size setting on items works with the **Default Dampener %** on the **Manufacturing Setup** page. [!INCLUDE[d365fin](includes/d365fin_md.md)] will ignore changes in demand that are below the dampener percentage and will not create planning suggestions. For example, 15 is specified in the Default Dampener % field, and we have a production order for 20 muffins to feed 20 guests, but one guest cannot attend. [!INCLUDE[d365fin](includes/d365fin_md.md)] will ignore the single missing guest because it's only 10% of the order. However, if two guests cannot make it, [!INCLUDE[d365fin](includes/d365fin_md.md)] will suggest that we reduce the order quantity because two is 20% of the lot size 10 defined on the item. For more information about planning, see [Planning](production-planning.md).dr

## See Also
[Create Production BOMs](production-how-to-create-production-boms.md)  
[Create Routings](production-how-to-create-routings.md)  
[Managing Inventory Costs](finance-manage-inventory-costs.md)