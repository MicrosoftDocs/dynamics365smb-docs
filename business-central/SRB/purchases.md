---
title: Purchasing
hide_title: true
sidebar_label: Purchasing
slug: /srb/purchases
---

# Purchasing
The unique [purchase](https://learn.microsoft.com/en-us/dynamics365/business-central/purchasing-manage-purchasing) of items with Service Commitments is no different than that in Microsoft Dynamics 365 Business Central. <br/>
Recurring purchasing (e.g., rental, maintenance, or subscription) is mapped with Service Commitments. Service Commitments receive *Vendor* as **Partner** in the Service Commitment Package. A Service Commitment Package can have both Customer and Vendor Service Commitments.


## Sales Quote and Sales Order
Service Commitments behave in [Sales](/docs/srb/sales/sales-service-commitments.md) in the same way as Service Commitments that have *Customer* entered as **Partner**. Depending on the **Calculation Base Type**, the **Calculation Base Amount** is determined from the **Unit Cost** field in sales lines or the **Last Direct Cost** field in the item. For more details, see [price calculation](/docs/srb/sales/price-calculation.md). 


## Service Object
When the item is delivered from the order, the Service Object and its Service Commitments are created. Both Customer and Vendor Service Commitments can be entered in the Service Object.


## Assignment to a Vendor Contract
Vendor Commitments can be assigned to any Vendor Contract. Unlike Customer Service Commitment, a Vendor Service Commitment can be assigned to any Vendor Contract.

:::info
In the **[Role Center](/docs/srb/first-steps.md)** you can see if there are any Vendor Service Commitments that have not been assigned to any contracts yet.
:::