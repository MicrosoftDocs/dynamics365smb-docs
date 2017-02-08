---
title: customer resource type | Microsoft Docs
description: A customer.
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

# customer resource type

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|Get customer|customer|
|Create customer|customer|
|Update customer|customer|
|Delete customer|none|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|number|string|The customer number.|
|displayName|string|The customer description.|
|address|string|The customer address.|
|address2|string|The customer address.|
|city|string||
|state|string||
|countryRegionCode|numeric||
|zipCode|numeric||
|phoneNumber|numeric||
|email|string||
|website|string||
|taxLiable|boolean||
|currencyCode|numeric||
|paymentTerms|numeric||
|paymentMethod|numeric||
|shipmentMethod|numberic||
|blocked|boolean||
|balance|numeric||
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
      "address": {NAV.PostalAddress},
      "phoneNumber": "String",
      "email": "String",
      "website": "String",
      "taxLiable": boolean,
      "currencyCode": "String",
      "paymentTerms": {NAV.PaymentTerms},
      "shipmentMethod": {NAV.ShipmentMethod},
      "paymentMethod": {NAV.PaymentMethod},
      "blocked": "String",
      "balance": Decimal,
      "lastModifiedDateTime": "DateTime",
    }


```