---
title: Contract types
description: You can use different types of contracts in subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
---

# Contract types

Use the **Contract Types** page to set up the types of contracts you use to manage and organize customer and vendor contracts. You can also use contract types as filters for billing. For example, maintenance or support contracts, insurance, or other types of incoming and outgoing recurring invoices.

For each contract type, you should enter a description and a unique code. The description is further used as an info line in the posting documents for the contracts.

> [!NOTE]
> You can define translations for contract types, and specify the language code. The language is used when you create [Posting documents](../posting-documents.md).

## Harmonized billing

The **Harmonized Billing Customer Contracts** field controls whether you bill the contract elements of customer contracts on a common due date. If it's selected, you can edit the corresponding fields in the **Harmonized Billing** group in the **Shipping and Billing** FastTab of the **Customer Contracts Card** page. If the field is reset, the fields on the customer contracts also reset and can be disabled upon request. To learn more, go to [Harmonized billing](../working-with-contracts/customer-contracts.md#harmonized-billing).

## Default without contract deferrals

Use the **Default Without Contract Deferrals** field to define the default value for the corresponding field in the contract. This makes it easier to create contracts and reduces handling errors. When you select the contract type, the value is copied to the field in the contract. You can change the value manually, if needed.

## Related information

[General setup](general.md)  
