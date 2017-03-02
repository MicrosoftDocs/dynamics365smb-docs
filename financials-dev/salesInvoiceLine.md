---
title: salesInvoiceLine resource type | Microsoft Docs
description: A sales invoice line.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/02/2017
ms.author: solsen
---

# salesInvoiceLine resource type

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
||||

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|sequence|||
|itemDisplayName||Specifies a name of the entry.|
|itemDescription||Specifies a description of the entry, which is based on the contents of the Type and No. fields.|
|quantity||Specifies how many units are being sold.|
|unitPrice||Specifies the price for one unit on the sales line.|
|discountAmount||Specifies the net amount, excluding any invoice discount amount, that must be paid for products on the line.|
|discountPercent||Specifies the discount percentage that is granted for the item on the line.|
|discountAppliedBeforeTax|Specifies the total discount applied before tax.|
|lineAmount|||
|expectedShipDate||Specifies the date the items on the sales document are expected to ship.|
|totalTaxAmount||Specifies the sum of tax amounts on all lines in the document|
|amountExcludingTax|||
|amountIncludingTax||Specifies the sum of the amounts in the Amount Including Tax fields on the associated sales lines.|
|itemNumber|||
|taxPercentage|||
|itemId|||
|expectedShipDates|||

## Relationships
None

## JSON representation

Here is a JSON representation of the resource.


```json
{
  
}

```

## See Also
[Graph Reference](graph-reference.md)  
