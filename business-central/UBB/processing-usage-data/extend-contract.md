---
title: Extend contract 
description: You can extend contracts in usage based billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Extend contract

To be able to extend a contract quickly and easily, the action **Extend Contract** is available. The basic functionality is explained in [this](/docs/srb/working-with-contracts/customer-contracts.md#extend-contract) part of the DYCE documentation. Therefore, only the differences or the extensions are discussed here.


## Extending a contract based on a subscription
In addition to the existing calls via the menu and the Customer Contract, the action is also available in the **Usage Data Subscriptions** and **Imported Lines** pages (lookup in the field of the same name on the **Usage Data Imports** page). This is particularly useful if errors occur during the processing of Imported Lines due to Service Commitments and Service Objects that do not yet exist.

Additionally, the extension field **Subscription** can be found in the page in the *Vendor* area. When the page is called up via the **Usage Data Subscriptions** or **Imported Lines**, the Subscription is automatically predefined. When calling up the page via the menu, the Subscription can be selected via the AssistEdit. The **Quantity** and **Provision Start Date** fields are predefined based on the Subscription. The item will also be preselected if it is found via the [product reference](/docs/ubb/masterdata/references.md#references-for-products). If not, it can also be selected manually.

:::note Unique product reference missing in usage data
If the unique product reference is missing or incomplete in the usage data, the item to be used for the contract extension cannot be suggested by the system. Currently, this is the case in the Microsoft reconciliation file (CSV). This therefore affects Microsoft Tier 1 partners.
:::

If the contract extension is executed, the created Service Commitments will automatically receive a link to the [Subscription reference](/docs/ubb/masterdata/references.md#references-for-subscriptions) based on which the future usage data can be found and processed.

:::info Rounding of the quantity
Since the quantity in the usage data can have decimal places, but only integer quantities can be stored in the Service Object, (commercial) rounding takes place when the field is preassigned.
:::