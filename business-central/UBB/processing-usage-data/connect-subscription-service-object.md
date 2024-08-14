---
title: Link subscription subsequently
hide_title: true
sidebar_label: Link subscription subsequently
slug: /ubb/processing-usage-data/connect-subscription-service-object
---

# Linking Subscription with Service Object
In case an already existing Service Object should only be connected to a Subscription afterwards (e.g. if the Service Object was shipped in advance via a Sales Order or created in another way), the functionality **Connect Subscriptions to Service Object** is available for this purpose.

The page of the same name shows all Subscriptions that are not yet connected to a Service Object. In addition to the familiar fields from the [Subscriptions overview](/docs/ubb/masterdata/customers-subscriptions.md), the Service Object to be linked can be selected via the **Link to Service Object** field. In the **Connect via** field, the system suggests whether this can be done on the basis of existing Service Commitments or new ones. The basis for this suggestion is whether the existing Service Commitments can be billed on a usage-dependent basis (**Usage Based Billing**=*Yes*) and are valid. Via **Connect to Date** the date can be specified for which new Service Commitments are to be created.

After setting the defaults, the Subscriptions to be processed are selected and then the action **Connect Subscriptions to Service Object** is called. If errors occur, they will be displayed in the **Reason** field. To correct the cause of the error, the processing status must first be reset using the separate **Reset Processing Status** action. After the error has been corrected, the Subscription can be reconnected.

:::caution New Service Objects
It is not possible to create new Service Objects using the method described here. If this is desired, the functionality **[Extend Contract](/docs/ubb/processing-usage-data/extend-contract.md)** can be used for this purpose.
:::