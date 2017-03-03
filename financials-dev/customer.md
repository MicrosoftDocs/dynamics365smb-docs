---
title: customer resource type | Microsoft Docs
description: A customer.
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

# customer resource type

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|Get customer|customer|Get customer object.|
|Create customer|customer|Create customer object.|
|Update customer|customer|Update customer object.|
|Delete customer|none|Delete customer object.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|number|string|The customer number.|
|displayName|string|The customer description.|
|address|string|The customer address.|
|address2|string|The customer address.|
|city|string|The city of the address.|
|state|string|The state of the address.|
|countryRegionCode|numeric|The country/region of the address.|
|zipCode|numeric|The zip code of the address.|
|phoneNumber|numeric|The customer's telephone number.|
|email|string|The customer's email address.|
|website|string|The customer's website address.|
|taxLiable|boolean|Specifies if the customer is liable for tax.|
|currencyCode|numeric|The default currency code for the customer.|
|paymentTerms|numeric|The default payment terms for the customer.|
|paymentMethod|numeric|The default payment method for the customer.|
|shipmentMethod|numberic|The default shipment method for the customer.|
|blocked|boolean|Specifies which transactions cannot be blocked for the customer.|
|balance|numeric|The customer's balance.|
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