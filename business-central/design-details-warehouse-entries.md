---
title: Design Details - Creating warehouse entries
description: Learn how to allow concurrent numbering for warehouse register records and warehouse entries.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords:
ms.date: 06/11/2024
ms.service: dynamics-365-business-central

---

# Design details: Creating warehouse entries

Warehouse entries contain information about item movements within the warehouse. For example, you create entries when you post a warehouse journal, or any transaction that moves items from one place to another. Each transaction can create several warehouse entries and warehouse register records. Warehouse register records have the first and last warehouse entry numbers. This information lets you identify the warehouse entries that a particular action created. And, conversely, each warehouse entry has a field that points to the warehouse register.

The following image illustrates the relationship between warehouse registers and warehouse entries for three transactions.

:::image type="content" source="media/warehouse register and entries.png" alt-text="Diagram shows the relations between warehouse register records and warehouse entries.":::

## Creating warehouse transactions

When [!INCLUDE [prod_short](includes/prod_short.md)] creates warehouse transactions, it checks the `ConcurrentWarehousingPosting` feature key to determine how to assign entry numbers to warehouse register records and warehouse entries.

### If the feature key is turned off

If the feature key is turned off, both tables are locked. [!INCLUDE [prod_short](includes/prod_short.md)] finds the last entry in both tables and assigns a number that is one digit higher. For example, if the last entry number is 10, then it assigns the number 11. This method of assignment ensures that warehouse entry numbers are consecutive in the warehouse register, but it blocks other users from registering warehouse transactions.

### If the feature key is turned on

If the feature key is turned on, which it is by default, entry numbers in both tables are assigned from `SequenceNumbers` in the database to allow users to register warehouse transactions at the same time. Using sequence numbers might cause warehouse entry numbers from two or more transactions to overlap, as the following image shows.

:::image type="content" source="media/warehouse register and entries 2.png" alt-text="Diagram shows how warehouse register records and warehouse entries can overlap.":::

## When to turn off the feature key

You might want to turn off the `ConcurrentWarehousingPosting` feature key if you work with a feature or extension that extends warehouse management and the following are true:

* The feature relies on consecutive entry numbers.
* The feature locks tables during a process.

## Related information

[Application design details](design-details-application-design.md)  
[Set up nondeductible VAT](finance-setup-nondeductible-vat.md)  
[Use nondeductible VAT](finance-how-use-non-deductible-vat.md)  
