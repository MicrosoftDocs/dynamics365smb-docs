---
title: vendor resource type | Microsoft Docs
description: A vendor.
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

# vendor resource type

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|Get vendor|vendor|Get vendor object.|
|Create vendor|vendor|Create vendor object.|
|Update vendor|vendor|Update vendor object.|
|Delete vendor|none|Delete vendor object.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|GUID|The vendor id.|
|number|string|The vendor number.|
|displayName|string|The vendor description.|
|address|complex|The vendor's address.|
|zipCode|numeric|The zip code of the address.|
|phoneNumber|string|The vendor's telephone number.|
|email|string|The vendor's email address.|
|website|string|The vendor's website address.|
|taxRegistrationNumber|string|The vendor's tax registration number.|
|currencyCode|string|The default currency code for the vendor.|
|irs1099Code|string||
|paymentTerms|complex|The default payment terms for the vendor.|
|paymentMethod|complex|The default payment method for the vendor.|
|taxLiable|boolean|Specifies if the vendor is liable for tax.|
|blocked|string|Specifies which transactions with the vendor that cannot be posted.|
|balance|decimal|The vendor's balance.|
|lastModifiedDateTime|datetime||  


## Relationships
None

## JSON representation

Here is a JSON representation of the resource.


```json
{
      "id": "GUID",
      "number": "String",
      "displayName": "String",
      "address": {NAV.PostalAddress}
      "phoneNumber": "String",
      "email": "String",
      "website": "String",
      "taxRegistrationNumber": "String",
      "currencyCode": "String",
      "irs1099Code": "String",
      "paymentTerms": {NAV.PaymentTerms},
      "paymentMethod": {NAV.PaymentMethod},
      "taxLiable": Boolean,
      "blocked": "String",
      "balance": decimal,
      "lastModifiedDateTime": "DateTime",
}

```

## See Also
[Graph Reference](graph-reference.md)  