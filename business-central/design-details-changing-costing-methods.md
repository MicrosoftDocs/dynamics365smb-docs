---
    title: Design Details - Changing Costing Methods
    description: Learn how to assign a different costing method to an item, although you have already used the item in transactions.
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: bholtorf

---

# Design Details - How to Change a Costing Method for an Item
in Business Central, you cannot change a costing method for an item after you have included the item in a transaction. For example, after you have bought or sold the item. If an incorrect costing method was assigned to the item or items, you might not discover the issue until you do your financial reporting.

This topic describes how to recover from this situation. The recommended approach is to replace the item that has the incorrect costing method with a new item, and use an assembly order to transfer the inventory from the old item to the new.

> [!NOTE]
> Information the user should notice even if skimming
