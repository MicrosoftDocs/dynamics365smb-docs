---
title: Contract renewal
description: You can renew contracts in subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
---

# Contract renewal

Some Contract lines are set to end at a certain date. These Contract lines can be extended with a Contract Renewal Quote. By using the Contract Renewal, a renewal period can be specified and a Sales Quote created subsequently. The **Service End Date** (in the Service Commitment / Contract line) will be extended once the Sales Quote is turned into a Sales Order and shipped.


## Creating a Contract Renewal Quote
A Contract Renewal Quote can be created on the **Contract Renewal** page and through the Customer Contracts. The **Contract Renewal** page can be used to create Contract Renewal Quotes for all Contract lines that are about to expire or have expired. <br/>
Open the search (*Alt+Q*) and type *Contract Renewal* to open the page. The action **Get Contract Lines** will open a filter page. On this page it is possible to filter for Contract lines that need to be renewed.


### Get Contract Lines
The action can be accessed in the **Contract Renewal** page and shows a filter page. On this filter page, set a date in the **Service End Date** field to specify the earliest **Service End Date** from which the Contract lines are to be considered. The **Add Vendor Contract Lines** field specifies whether to include the related vendor-side Contract lines. If so, the Service Objects of the relevant Vendor Contract lines are checked to see if any additional vendor-side Service Commitments exist. Any non-closed Vendor Service Commitments associated with a Vendor Contract that have a **Service End Date** will also be considered for Contract Renewals. <br/>
Thus, if you set **Add Vendor Contract Lines** to *Yes*, all vendor-side Service Commitments of the same Service Object will also be considered for renewal. <br/>
If additional filters are needed, you can filter by any field in Customer Contract and Service Commitments. <br/>
After confirming the filters entered, **Renewal lines** will be created for all valid Contract lines. A Contract line is *valid* if a **Service End Date** is set within the filter and the line is not closed, yet. All lines are displayed in the Contract Renewal page.

:::info Closed Contract Lines
Contract lines are closed when reaching the **Service End Date**. Closed Contract lines can be found in the fast tab **Closed Lines** in the Contract Card page. They can be reopened by changing **Closed** to *No*.
:::

In order to renew a Contract line, the **Renewal Term** has to have a value. It is prefilled from the **Initial Term** of the corresponding Contract line. The value can be changed to match the desired term of renewal.

:::caution Preventing duplicates
A Contract Renewal line can only be created if there is no line in a Sales Quote for renewal belonging to that Contract line.
:::


### Create Quotes
Calling the action **Create Quotes** on the Contract Renewal page will create new Sales Quotes. The user can perform the action either for all lines or for selected lines only. All Contract Renewal lines for which Sales Quotes have been created will be deleted. <br/>
If the **Renewal Term** field in the renewal line has no value, the renewal line will not be included in a quote and therefore will not be renewed. <br/>
The created lines in the Sales Quote are of type *Service Object* and are marked as **Contract Renewal**=*Yes*. The Sales Service Commitment can be changed and new items can be added in the Sales Quote. Adding new Service Commitments to the existing Sales lines (marked as **Contract Renewal**=*Yes*) is not possible. <br/>
Sales Quotes can be printed. The Sales lines marked as **Contract Renewal**=*Yes* are set (via formatting) to print only the quantity, to avoid confusion between renewing the Service Commitments and selling additional items. The price of Sales Service Commitments is printed. The total of the Sales Service Commitment to be renewed is printed separately and labeled *Contract Renewal*.


## Sales Order
In order to renew Contract lines, the Sales Quote has to be turned into a Sales Order and shipped (from the system's point of view). Sales lines marked as **Contract Renewal** can only be shipped in full or excluded from delivery. The *posting of shipment* serves as a standardized step to start processing. In this process, the line as such is not actually shipped, but only the Service Commitments for which the extension/renewal was offered is updated (see below). Therefore, there are neither posted shipments nor posted invoices for these renewals. Service Commitments are invoiced via the next Contract invoice. Nevertheless, shipments and invoices can be created for items that are not **Contract Renewals**. <br/>
On shipping the Sales Order, the Contract lines are either renewed or a **Planned Service Commitment** will be created. The Contract line will be renewed and the **Service End Date** changed, if none of the following fields have been changed in the Sales Service Commitment:
* Calculation Base Amount
* Calculation Base %
* Price
* Discount %
* Notice Period
* Calculation Base Period
* Billing Rhythm

If one of these fields have been changed and the Contract line has not been invoiced up to the **Service End Date**, a **Planned Service Commitment** will be created. The **Planned Service Commitment** saves the changes to the Contract line and thereby ensures that the Contract line can be invoiced with current conditions until the **Service End Date**. <br/>
If the Contract line is invoiced up to the **Service End Date**, the Contract line will be updated from associated **Planned Service Commitment**. The **Planned Service Commitment** is deleted after the update.

:::info Planned Service Commitments
**Planned Service Commitments** for specific Contract lines can be reviewed via the lookup in field **Planned Service Commitment exists** in the *Lines* fast tab of a Customer Contract card page. <br/>
By searching for *Planned Service Commitments* (*Alt+Q*), the page of the same name shows all **Planned Service Commitments** for all contracts. <br/>
Since **Planned Service Commitments** can also exist for Vendor Service Commitments, this field is also present in Vendor Contract lines.
:::


## Customer Contract
The renewal of a *specific* Customer Contract can be achieved by calling the action **Create Contract Renewal Quote** in the menu group *Home* of the Customer Contract card page. Subsequently, the page **Select Contract Lines for Renewal** is opened.

:::caution Existing Contract Renewal lines and Sales Quotes
Calling the action **Create Contract Renewal Quote** will delete already created Contract Renewal lines. <br/>
A new Sales Quote for a Contract line cannot be created if there is already a Sales Quote or Sales Order for that Contract line.
:::

In page **Select Contract Lines for Renewal** only *valid* Contract lines will be displayed. A Contract line is valid if a **Service End Date** is set and the line is not closed, yet. <br/>
In order to renew a Contract line, a value must be specified in **Renewal term**. This is predefined from the **Initial Term** of the corresponding Contract line. The value can be changed to achieve the desired renewal term. <br/>
If the **Renewal Term** in the Renewal line has no value, the Renewal line will not be included in the Sales Quote.

After closing page **Select Contract Lines for Renewal** with *OK*, a Sales Quote is created. The steps for [handling the Sales Quote](#create-quotes) and [preforming the Contract Renewal](#sales-order) are identical to already described process.