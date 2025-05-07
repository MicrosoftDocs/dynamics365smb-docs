---
title: Contract renewal
description: You can renew contracts in subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
---

# Contract renewal

Some contract lines are set to end at a certain date. On the **Customer Contract** and **Vendor Contract** pages, you can use the **Renewal Quote** action to extend these contract lines. When you do, you can specify a renewal period and create a sales quote. The **Service End Date** (in the Service Commitment / Contract line) is extended when you convert the sales quote to a sales order and ship it.

## Create a contract renewal quote

You can create a contract renewal quote on the **Contract Renewal** and **Customer Contract** pages. Use the **Contract Renewal** page to create contract renewal quotes for all contract lines that are about to expire or have expired. To filter for specific contract lines, choose the :::image type="content" source="../../LocalFunctionality/India/image/search_small.png" alt-text="TellMe search icon."::: TellMe search icon to open the **Contract Renewal** page. Use the **Get Contract Lines** action to open a filter page and filter for the contract lines to renew. To learn more, go to [Get contract lines](#get-contract-lines).

### Get contract lines

The **Get Contract Lines** action on the **Contract Renewal** page shows a filter page. On the filter page, set a date in the **Service End Date** field to specify the earliest **Service End Date** from which to show contract lines. The **Add Vendor Contract Lines** field specifies whether to include the related vendor-side contract lines. If so, the service objects of the relevant vendor contract lines are checked to see if any additional vendor-side service commitments exist. Open vendor service commitments associated with a vendor contract that have a **Service End Date** are also considered for contract fenewals.

Therefore, if you turn on **Add Vendor Contract Lines** toggle, all vendor-side service commitments for the same service object are also considered for renewal.

If you need more filters, you can filter by any field on the **Customer Contract** and **Service Commitments** pages. After you confirm the filters, renewal lines are created for all valid contract lines. A contract line is valid if you specify a **Service End Date** for the filter and the line isn't closed. The **Contract Renewal** page shows all lines.

> [!NOTE]
> Contract lines are closed when they reach the date in the **Service End Date** field. You can access closed contract lines on the **Closed Lines** FastTab on the **Contract Card** page. To reopen closed lines, clear the **Closed** checkbox.

To renew a contract line, specify a value in the **Renewal Term** field. It is prefilled from the **Initial Term** of the corresponding contract line. You can change the value to match the desired term of renewal.

> [!CAUTION]
> You can only create a contract renewal line if there isn't a line on a sales quote for renewal for the contract line.

### Create quotes

Use the **Create Quotes** action on the **Contract Renewal** page to create sales quotes. You can create quotes for all lines, or selected lines. All contract renewal lines for which sales quotes are created are deleted.

If the **Renewal Term** field on the renewal line is blank, the renewal line isn't included a quote and won't be renewed.

The lines created on the sales quote have the **Service Object** type, and the **Contract Renewal** toggle is turned on. You can change the sales service commitment and add new items to the sales quote. You can't add new service commitments to the sales lines.

You can print sales quotes. Sales lines with the **Contract Renewal** toggle turned on print only the quantity to avoid confusion between renewing the service commitments and selling additional items. The prices of sales service commitments are printed. The total of the sales service commitment to renew is printed separately and labeled **Contract Renewal**.

## Sales orders

To renew contract lines, you must convert the sales quote into a sales order and ship the order. You can only ship sales lines marked as **Contract Renewal** in full or exclude them from delivery. Posting a shipment serves as a standard step to start processing. In this process, the line isn't actually shipped. Only the service commitments for which the extension/renewal was offered updates. Therefore, there are neither posted shipments nor posted invoices for these renewals. You invoice service commitments in the next contract invoice. However, shipments and invoices can be created for items that aren't **Contract Renewals**.

When you ship a sales order, the contract lines are either renewed or a **Planned Service Commitment** is created. If none of the following fields have been changed in the sales service commitment, the contract line is renewed and the **Service End Date** changes:

* Calculation Base Amount
* Calculation Base %
* Price
* Discount %
* Notice Period
* Calculation Base Period
* Billing Rhythm

If one of these fields was changed and the contract line isn't invoiced up to the **Service End Date**, a **Planned Service Commitment** is created. The **Planned Service Commitment** saves the changes to the contract line to ensure that you can invoice the contract line with the current conditions until the **Service End Date**.

If you invoice the contract line up to the **Service End Date**, the contract line updates from the associated planned service commitment. The planned service commitment is deleted after the update.

> [!NOTE]
> You can review the planned service commitments for specific contract lines by using the **Planned Service Commitment exists** field on the **Lines** FastTab on the **Customer Contract** page.

The **Planned Service Commitments** page shows all planned service commitments for all contracts. Because planned service commitments can also exist for vendor service commitments, this field is also available on vendor contract lines.

## Customer contract

Use the **Create Contract Renewal Quote** action on the **Customer Contract** page to renew a specific customer contract. The action opens the **Select Contract Lines for Renewal** page.

> [!CAUTION]
> The **Create Contract Renewal Quote** action deletes existing contract renewal lines. 
>
> You can't create a new sales quote for a contract line if there is a sales quote or sales order for the line.

The **Select Contract Lines for Renewal** page only shows valid contract lines. A contract line is valid if a **Service End Date** is set and the line isn't closed.

To renew a contract line, specify a value in the **Renewal Term** field. The default value comes from the **Initial Term** field on the corresponding contract line. You can change the value to set the desired renewal term.

If the **Renewal Term** field on the renewal line is blank, the renewal line won't be included on the sales quote.

when you choose**OK** to close the **Select Contract Lines for Renewal** page, a sales quote is created. The steps to [Create quotes](#create-quotes) and [Sales orders](#sales-orders) are the same as the steps described in this article.

## Related information

[Customer contracts](customer-contracts.md)  
[Vendor contracts](vendor-contracts.md)  
[Contract deferrals](contract-deferrals.md)  
