---
title: item resource type | Microsoft Docs
description: An item.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/08/2017
ms.author: solsen
---

# item resource type

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|Get item|item|Get item object.|
|Create item|item|Create item object.|
|Update item|item|Update item object.|
|Delete item|none|Delete item object.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|number|string|The item number.|
|displayName|string|Specifies a description of the item.|
|id|string||
|type|numeric||
|blocked|boolean|Specifies that transactions with the item cannot be posted, for example, because the item is in quarantine.|
|baseUnitOfMeasure|string|Specifies the unit in which the item is held in inventory.|
|gtin|string||
|itemCategoryCode|numeric|Specifies the category that the item belongs to. Item categories also contain any assigned item attributes.|
|inventory|numeric|Specifies how many units, such as pieces, boxes, or cans, of the item are in inventory.|
|unitPrice|numeric|Specifies the price for one unit of the item in the specified currency.|
|priceIncludesTax|boolean||
|unitCost|numeric|Specifies the cost per unit of the item.|
|taxGroupCode|numeric||
|lastModifiedDateTime|datetime||  


## Relationships
None

## JSON representation

Here is a JSON representation of the resource.


```json
{
      "id": "GUID",
      "number": "string",
      "displayName": "string",
      "type": "String",
      "blocked": boolean,
      "baseUnitOfMeasure": {NAV.UnitOfMeasure},
      "gtin": "String",
      "itemCategory": NAV.ItemCategory,
      "inventory": Decimal,
      "unitPrice": Decimal,
      "priceIncludesTax": Boolean,
      "unitCost": Decimal,
      "taxGroupCode": "String",
      "lastModifiedDateTime": "DateTime",
}

```

## See also
[Graph Reference](graph-reference.md)  