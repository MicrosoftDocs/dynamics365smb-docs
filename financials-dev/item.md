---
title: item resource type | Microsoft Docs
description: An item.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: project-madeira
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
|displayName|string|The item description.|
|id|string||
|type|numeric||
|blocked|boolean||
|baseUnitOfMeasure|string||
|gtin|string||
|itemCategoryCode|numeric||
|inventory|numeric||
|unitPrice|numeric||
|priceIncludesTax|boolean||
|unitCost|numeric||
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