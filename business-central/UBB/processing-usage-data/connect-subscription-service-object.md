---
title: Link subscriptions with subscriptions
description: You can subscriptions with subscriptions in usage-based billing.
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

# Link subscriptions with subscriptions

In case an already existing subscription should only be connected to a subscription afterwards (for example, if the subscription was shipped in advance with a sales order or created in another way), the functionality **Connect Supplier Subscription to Subscription** is available for this purpose.

The **Connect Supplier Subscription to Subscription** page shows all supplier subscriptions that aren't connected to a subscription. In addition to the fields from [Usage-based billing customers and subscriptions](../masterdata/customers-subscriptions.md), you can select the subscription to link by using the **Connect to Subscription** field. In the **Connect to SO Method** field, [!INCLUDE [prod_short](../../includes/prod_short.md)] suggests whether you can create the link on the basis of existing service commitments or new ones. The basis for this suggestion is whether the existing service commitments can be billed on a usage basis (the **Usage-Based Billing** checkbox is selected for the subscription) and are valid. Via **Connect to SO at Date** field, you can specify the date on which to create new service commitments.

After setting the defaults, the subscriptions to process are selected, and you can run the **Connect Supplier Subscriptions to Subscriptions** action. If errors occur, they display in the **Reason (Preview)** field. To correct the cause of the error, use the **Reset Processing Status** action to reset the processing status. After you correct the error, you can reconnect the subscription.

> [!CAUTION]
> You can't create new subscriptions using the method described here. To create new subscriptions, use the **Extend Contract** action. To learn more, go to [Extend contract](extend-contract.md).

## Related information

[Usage-based billing customers and subscriptions](../masterdata/customers-subscriptions.md)