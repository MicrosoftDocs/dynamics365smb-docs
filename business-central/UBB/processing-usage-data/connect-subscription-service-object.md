---
title: Link subscriptions with service objects
description: You can subscriptions with service objects in usage based billing.
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

# Link subscriptions with service objects

In case an already existing service object should only be connected to a subscription afterwards (for example, if the service object was shipped in advance with a sales order or created in another way), the functionality **Connect Subscriptions to Service Object** is available for this purpose.

The **Connect Subscriptions to Service Object** page shows all subscriptions that aren't connected to a service object. In addition to the familiar fields from the [Usage based billing customers and subscriptions](../masterdata/customers-subscriptions.md), you can select the service object to link by using the **Link to Service Object** field. In the **Connect via** field <!--don't see this field on the **Connect Subscriptions to Service Object** page-->, [!INCLUDE [prod_short](../../includes/prod_short.md)] suggests whether you can create the link on the basis of existing service commitments or new ones. The basis for this suggestion is whether the existing service commitments can be billed on a usage-dependent basis (the **Usage Based Billing** checkbox is selected <!--selected where? this seems to talk about service commitments, but the checkbox is on the service object. -->) and are valid. Via **Connect to Date** the date can be specified for which new Service Commitments are to be created.

After setting the defaults, the subscriptions to process are selected and then the action **Connect Subscriptions to Service Object** runs <!--there was "is called". Automatically, or is this saying that the user should run the action-->. If errors occur, they display in the **Reason** field. To correct the cause of the error, use the **Reset Processing Status** action to reset the processing status. After you correct the, you can reconnect the subscription.

> [!CAUTION]
> You can't create new service objects using the method described here. To create new service objects, use the **Extend Contract** action. To learn more go to [Extend contract](extend-contract.md).

## See also

[Usage based billing customers and subscriptions](../masterdata/customers-subscriptions.md)