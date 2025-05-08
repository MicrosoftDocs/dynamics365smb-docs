---
title: Extend contract 
description: You can extend contracts in usage based billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Extend contract

To extend a contract, use the **Extend Contract** action on the **Customer Contract** or **Vendor Contract** pages. The feature is part of subscription billing, but you also use it in usage based billing. This article describes the differences. To learn more about extending contracts, go to [Extend contract](../../SRB/working-with-contracts/customer-contracts.md#extend-contract).

## Extend a contract based on a subscription

In addition to the **Customer Contract** or **Vendor Contract** pages, the **Extend Contract** action is also available on the **Usage Data Subscriptions** page, and fro the lookup in the **No. of Imported Lines** field on the **Usage Data Imports** page. This is particularly useful if errors occur when processing imported lines due to service commitments and service objects that don't exist.

The **Subscription** field is available on the **Extend Contract** page on the **Vendor** FastTab. When you open the page from the **Usage Data Subscriptions** or **Imported Lines** pages, the subscription is automatically predefined. When you open the page from the menu, the you can also select the subscription using the AssistEdit :::image type="content" source="../../media/assist-edit-icon.png" alt-text="AssistEdit icon."::: button. The **Quantity** and **Provision Start Date** fields are predefined based on the subscription. The item will also be preselected if it's found through the [references for products](../masterdata/references.md#references-for-products). If not, you can select it manually.

If you extend a contract, the created service commitments automatically have a link to the [references for subscriptions](../masterdata/references.md#references-for-subscriptions), based on which the future usage data can be found and processed.

> [!NOTE]
> Because quantities in usage data can have decimal places, but you can only use integer quantities in the service object, (commercial) rounding takes place when the field is preassigned.

## Related information

[Customer contracts](../../SRB/working-with-contracts/customer-contracts.md)  
[Vendor contracts](../../SRB/working-with-contracts/vendor-contracts.md)  
