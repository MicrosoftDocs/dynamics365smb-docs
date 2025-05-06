---
title: Setting up Posting No. Series
description: Specifies Posting No. series required

author: v-debapd

    
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 09/20/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Setting up Posting No. Series

[!INCLUDE[vnext_preview](../../includes/vnext_preview.md)]

## Overview

Business Central has included Posting No. Series feature to Indian Localization.

Posting No. series functionality enables you to maintain the different number series of below sales, purchase, and transfer orders for different locations.

- Purchase Receipt

- Purchase Invoice 

- Sales Shipment

- Sales Invoice

- Purchase Credit Memo

- Sales Return Receipt

- Sales Credit Memo

- Purchase Return Shipment

- Transfer Shipment

- Transfer Receipt

- GST Distribution

- Service Transfer Shipment

- Service Transfer Receipt

- Gate Entry

Following comprehensive functionalities are covered under Posting No. Series:

  - Provision to define different number series for different types of sales and purchase documents for different Locations.
  - After posting of sales and purchase documents, the program will store the number series assigned in Posting No. Series page for specified filters.
  - Provision to define separate number series in sales and purchase documents in case of trading activity.
  - Provision to define separate number series for the locations used in transfer orders.


## Setting up Posting No. Series
You need to create a set up for posting of documents. The following procedure shows how to set up posting number series.
1. Choose the :::image type="content" source="../../media/ui-search/search_small.png" alt-text="Icon that opens the TellMe search."::: icon, enter **Posting No. Series**, and then choose the related link.
2. Click on **New**.
3. Fill in the fields as described in the following table.

    |Field|Description|  
    |-----|:----------|
    |**Document Type**|Specify the number series for Purchase, Sales & Transfer documents. |
    |**Condition**|Specifies the filters for type of record selected in the Document Type. For example, if Document Type is Posted Sales Invoice and Condition is Location Code as BLUE, then system will update the document number of posted sales invoices for BLUE location with code specified in the Posting No. series field. |
    |**Posting No. Series**| Specifies the desired number series for each document type and defined filters.

> [!Note]
>
> Program will record the number series for posted documents based on number specified in the above Posting No. Series field.


