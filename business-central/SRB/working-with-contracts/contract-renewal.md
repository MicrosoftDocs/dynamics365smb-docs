---
title: Subscription contract renewal
description: You can renew contracts in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 8052, 8053, 8071, 
ms.date: 07/11/2025
ms.service: dynamics-365-business-central
---

# Subscription contract renewal

Some contract lines are set to end at a certain date. On the **Customer Subscription Contract** and **Vendor Subscription Contract** pages, you can use the **Create Contract Renewal Quote** action to extend these contract lines. When you do, you can specify a renewal period and create a sales quote. The **Subscription Line End Date** (in the subscription line or subscription contract line) is extended when you convert the sales quote to a sales order and ship it.

## Create a subscription contract renewal quote

You can create a subscription contract renewal quote on the **Subscription Contract Renewal** and **Customer Subscription Contract** pages. Use the **Subscription Contract Renewal** page to create renewal quotes for all contract lines that are about to expire or have expired. Use the :::image type="content" source="../../LocalFunctionality/India/image/search_small.png" alt-text="TellMe search icon."::: TellMe search icon to open the **Subscription Contract Renewal** page. To filter for specific contract lines, use the **Get Contract Lines** action to open a filter page and filter for the contract lines to renew. To learn more, go to [Get contract lines](#get-contract-lines).

### Get contract lines

The **Get Contract Lines** action on the **Subscription Contract Renewal** page opens a filter page. On this filter page, set a date in the **Subscription Line End Date Period** field to specify the earliest end date from which to show contract lines. The **Add Vendor Subscription Contract Lines** field specifies whether to include the related vendor-side contract lines. If so, the subscriptions of the relevant lines are checked to see if any additional vendor-side subscription lines exist. Open vendor subscription lines associated with a vendor contract that have a subscription line end date are also considered for contract renewals.

Therefore, if you turn on **Add Vendor Subscription Contract Lines** toggle, all vendor-side subscription lines for the same subscription are also considered for renewal.

If you need more filters, you can filter by any field on the **Customer Subscription Contract** and **Subscription Lines** pages. After you confirm the filters, renewal lines are created for all valid contract lines. A contract line is valid if you specify a **Subscription Line End Date Period** for the filter and the line isn't closed. The **Contract Renewal** page shows all lines.

> [!NOTE]
> Contract lines are closed when they reach the date in the **Subscription Line End Date** field. You can access closed contract lines on the **Closed Lines** FastTab on the **Vendor Subscription Contract** or **Customer Subscription Contract** pages. To reopen closed lines, clear the **Closed** checkbox.

To renew a contract line, specify a value in the **Renewal Term** field. It is prefilled from the **Initial Term** of the corresponding contract line. You can change the value to match the term of renewal you want to use.

> [!CAUTION]
> You can only create a subscription contract renewal line if there isn't a line on a sales quote for renewing the contract line.

### Create quotes

Use the **Create Quotes** action on the **Subscription Contract Renewal** page to create sales quotes. You can create quotes for all lines, or selected lines. All subscription contract renewal lines for which sales quotes are created are deleted.

If the **Renewal Term** field on the renewal line is blank, the renewal line isn't included in a quote and won't be renewed.

The lines created on the sales quote have the **Subscription** type, and the **Contract Renewal** toggle is turned on. You can change the sales subscription lines and add new items to the sales quote. You can't add new sales subscription lines, though.

When printing sales quotes, lines with the **Contract Renewal** toggle turned on print only the quantity to avoid confusion between renewing the subscription lines and selling additional items. The prices of sales subscription lines are printed. The total of the sales subscription lines to renew is printed separately and labeled **Contract Renewal**.

## Sales orders

To renew contract lines, you must convert the sales quote into a sales order and ship the order. You can only ship sales lines marked as **Contract Renewal** in full or exclude them from delivery. Posting a shipment serves as a standard step to start processing. In this process, the line isn't actually shipped. Only the subscription lines for which the renewal was offered updates. Therefore, there are neither posted shipments nor posted invoices for these renewals. You invoice subscription lines in one of the next contract invoices. However, shipments and invoices can be created for items that aren't **Contract Renewals**.

When you ship a sales order, the contract lines are either renewed or a **Planned Subscription line** is created. If none of the following fields were changed in the sales subscription lines, the contract line is renewed and the date in the **Subscription Line End Date** field changes:

* Calculation Base Amount
* Calculation Base %
* Price
* Discount %
* Notice Period
* Calculation Base Period
* Billing Rhythm

If one of these fields was changed and the contract line isn't invoiced up to the **Subscription Line End Date**, a planned subscription line is created. The planned subscription line saves the changes to the contract line to ensure that you can invoice the contract line with the current conditions until the subscription line end date.

If you invoice the contract line up to the subscription line end date, the contract line updates from the associated planned subscription line automatically. The planned subscription line is deleted after the update.

> [!NOTE]
> You can review the planned subscription lines for specific contract lines by using the **Planned Subscription Line exists** field on the **Lines** FastTab on the **Customer Subscription Contract** page.

By opening **Planned Subscription Lines** page from TellMe search, all planned subscription lines for all contracts display. Because planned subscription lines can also exist for vendor subscription lines, this field is also available on vendor subscription contract lines.

## Customer subscription contract

Use the **Create Contract Renewal Quote** action on the **Customer Subscription Contract** page to renew a specific customer subscription contract. The action opens the **Subscription Contract Renewal** page.

> [!CAUTION]
> The **Create Contract Renewal Quote** action deletes existing subscription contract renewal lines. 
>
> You can't create a new sales quote for a contract line if there is a sales quote or sales order for the line.

To suggest contract lines for renewal, call **Get Contract Lines** action to open the **Select Subscription Contract Lines for Renewal** page. Only those contract lines are considered that have a **Subscription Line End Date** set and the line isn't closed.

To renew a contract line, specify a value in the **Renewal Term** field. The default value comes from the **Initial Term** field on the corresponding contract line. You can change the value to set the desired renewal term.

If the **Renewal Term** field on the renewal line is blank, the renewal line won't be included on the sales quote.

By calling **Create Quotes** action on the **Subscription Contract Renewal** page, sales quotes are created. The steps to [Create quotes](#create-quotes) and [Sales orders](#sales-orders) are the same as the steps described in this article.

## Related information

[Customer subscription contracts](customer-contracts.md)  
[Vendor subscription contracts](vendor-contracts.md)  
[Contract deferrals](contract-deferrals.md)  
