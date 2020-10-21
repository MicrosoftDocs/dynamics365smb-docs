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

Note: It works great, when quantity in production order is factor of Lot Size in routing, for example your baking sheet can held 10 muffins, then you should bake 10, 20, 30, etc. Not 5 nor 15.
Note2: The time defined into Setup Time  field of the Routing Line will happen only once even if there are several lots: you don’t need to warm the oven for the second lot of muffins.
Learn more about creation of routing here: https://docs.microsoft.com/en-us/dynamics365/business-central/production-how-to-create-routings


