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
|displayName|string|Specifies the customer's name. This name will appear on all sales documents for the customer. You can enter a maximum of 50 characters, both numbers and letters.|
|address|string|Specifies the customer's address. This address will appear on all sales documents for the customer.|
|address2|string|Specifies additional address information.|
|city|string|Specifies the customer's city.|
|state|string|Specifies the state as a part of the address.|
|countryRegionCode|numeric|Specifies the country/region of the address.|
|zipCode|numeric|Specifies the ZIP code.|
|phoneNumber|numeric|Specifies the customer's telephone number.|
|email|string|Specifies the customer's email address.|
|website|string|Specifies the customer's home page address.|
|taxLiable|boolean|Specifies if the customer or vendor is liable for sales tax.|
|currencyCode|numeric|The default currency code for the customer.|
|paymentTerms|numeric|Specifies a code that indicates the payment terms that you require of the customer.|
|paymentMethod|numeric|Specifies how the customer usually submits payment, such as bank transfer or check.|
|shipmentMethod|numberic|Specifies which shipment method to use when you ship items to the customer.|
|blocked|boolean|Specifies which transactions with the customer that cannot be blocked, for example, because the customer is insolvent.|
|balance|numeric|Specifies the payment amount that the customer owes for completed sales. This value is also known as the customer's balance.|
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
## See Also
[Graph Reference](graph-reference.md)  