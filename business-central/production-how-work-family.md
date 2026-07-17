---
title: Work with Production Families in Manufacturing 
description: Learn how to group items that share a manufacturing process so you can produce them together and reduce material scrap and repeated setup work.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.form: 99000790, 99000791, 99000792, 99000793
ms.date: 07/15/2026
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Work with Production Families

Production families group items that you can produce together because they share a manufacturing process. Use a family production order when one operation yields multiple related items, such as different parts cut from the same sheet. Producing the items together can reduce material scrap and repeated setup work.

In the **Quantity** field on the **Family** page, you enter the quantity that will be produced when the whole family has been manufactured once.

## Example

In punching processes, four pieces of the same item can be produced from one sheet and 10 pieces of another, different, item at the same time. The punching machine will punch all 14 pieces in one step.

Forming production families reduces the scrap quantity because what would normally be leftover scrap, when producing big pieces, will be used instead to produce small items.

## To set up a production family

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Families**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To produce based on a production family

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Firm Planned Prod. Orders**, and then choose the related link.
2. Create a new production order. For more information, see [Create Production orders](production-how-to-create-production-orders.md).
3. In the **Source Type** field, select **Family**.  
4. In the **Source No.** field, select the relevant production family.

## Related information

[Create Production BOMs](production-how-to-create-production-boms.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)
[Planning](production-planning.md)   
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
