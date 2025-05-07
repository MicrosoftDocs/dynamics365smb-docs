---
title: Extend contract 
description: You can extend contracts in usage-based billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 
ms.search.form: 8042, 8053, 8041
ms.date: 05/07/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Extend a contract

To extend a contract, use the **Extend Subscription Contract** action on the **Customer Subscription Contract** page. The feature is part of subscription billing, but you also use it in usage-based billing. This article describes the differences. To learn more about extending contracts, go to [Extend subscription contracts](../../SRB/working-with-contracts/customer-contracts.md#extend-contract).

## Extend a contract based on a subscription

In addition to the **Customer Subscription Contract** page, the **Extend Contract** action is also available on the **Usage Data Subscriptions** page, and from the lookup in the **No. of Imported Lines** field on the **Usage Data Imports** page. This action is useful if errors occur when processing imported lines due to subscription lines and subscriptions that don't exist.

The **Subscription** field is available on the **Extend Contract** page on the **Vendor** FastTab. When you open the page from the **Usage Data Subscriptions** or **Imported Lines** pages, the subscription is automatically predefined. When you open the page from the menu, you can also select the subscription using the AssistEdit :::image type="content" source="../../media/assist-edit-icon.png" alt-text="AssistEdit icon."::: button. The **Quantity** and **Provision Start Date** fields are predefined based on the subscription. The item is also preselected if it was found through [references for products](../masterdata/references.md#references-for-products). If not, you can select it manually.

If you extend a contract, the created subscription lines automatically have a link to the [references for subscriptions](../masterdata/references.md#references-for-subscriptions), based on which the future usage data can be found and processed.

> [!NOTE]
> Because quantities in usage data can have decimal places, you can only use integer quantities in the subscription. Rounding happens when the field is preassigned.

## Related information

[Customer subscription contracts](../../SRB/working-with-contracts/customer-contracts.md)  
[Vendor subscription contracts](../../SRB/working-with-contracts/vendor-contracts.md)  