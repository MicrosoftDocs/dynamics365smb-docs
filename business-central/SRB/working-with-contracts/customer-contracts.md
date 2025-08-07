---
title: Customer subscription contracts
description: You can use customer subscription contracts in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 8053, 8071
ms.date: 05/06/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Customer subscription contracts

Customer subscription contracts represent obligations to customers. The structure of contracts is similar to sales orders. On the **Customer Subscription Contract** page, the fields on the **General** FastTab contain information about the contractor, such as their contact person. The lines contain information about the billing of the components of the contract.

On the **Shipping and Billing** FastTab, you can specify ship-to and bill-to recipients for the contractor.

* **Alternate shipping address** or **Custom Address** for the **Ship-to** address.
   In the context of a contract, another word for *shipment recipient* could be *subscription recipient*. For example, you can use this concept in a partner model to record the end customer of the partner. Therefore, the ship-to information also serves as a visual indicator when assigning new contract elements. To learn more, go to [Assign subscription lines to a customer subscription contract](#assign-subscription-lines-to-a-customer-subscription-contract).
* **Custom Address** or **Another Customer** for the **Bill-to** address.
   Similar to sales orders, a deviating invoice recipient can be entered here. This is taken into account when creating the contract invoices.

> [!NOTE]
> Contracts are available in the **Sell-to Customer Sales History** FactBox on the the **Customer Card**, **Vendor Card**, and **Contact Card** pages. Choose the respective cue to open an overview.

## Overview of the process for creating a customer subscription contract

The following are the high-level steps to create a contract for a customer.

1. [Create a new customer subscription contract](#create-a-new-customer-subscription-contract).
2. [Assign subscription lines to a customer subscription contract](#assign-subscription-lines-to-a-customer-subscription-contract)
3. [Create an invoice per contract](#create-an-invoice-per-contract).

### Create a new customer subscription contract

On the **Customers** page, use the **Subscription Contract** action to quickly create a new customer subscription contract. The contact data for the customer transfers to the new contract.

To create a contract, follow these steps:

1. Choose the :::image type="content" source="../../media/ui-search/search_small.png" alt-text="Tell me what you want to do icon."::: icon, enter **Customers**, then choose the related link.
2. Select the customer, and then choose the **Subscription Contract** action.
3. Optionally, fill in the **Contract Type** and **Description** fields. To learn more about subscription contract types, go to [Subscription contract types](../setup/contract-types.md).
4. In the **Assigned User ID** field, choose the employee who's responsible for the contract.
5. If needed, change the values in the **Currency Code**, **Payment Terms Code**, and **Payment Method Code** fields on the **Invoice Details**. The values were copied from the customer in step 1.
6. Select whether a **Detail Overview** is to be output for invoices.
7. On the **Shipping and Billing** FastTab, verify the values in the **Ship-to** and **Bill-to** fields.
8. The next step is to assign subscription lines. To learn more, go to [Assign subscription lines to a customer subscription contract](#assign-subscription-lines-to-a-customer-subscription-contract).  

> [!TIP]
> You can use the **Contract Type** and **Assigned User ID** fields as filters in subscription billing to bill contracts separately based on type and clerk.

There are two ways to add subscription lines to a contract. You can assign subscription lines from posted (delivered) sales orders using the **Get Subscription Lines** action on the customer subscription contract, or you can also extend the a contract, if needed. To learn more, go to [Extend contract](#extend-contract).

### Assign subscription lines to a customer subscription contract

To bill subscription lines, you must assign them to a contract. On the **Customer Subscription Contract** page, use the **Get Subscription Lines** action to assign subscription lines. The **Subscription Lines without Customer Subscription Contract** page displays the subscription lines for the customer that you invoice through a contract, but aren't yet assigned to a contract. The subscription lines that display are based on the customer on the subscription. To learn more, go to [Subscriptions](service-objects.md). When you open them in a contract, the **No.** field is predefined in **Assign to Contract No.** on the subscription line.

If the **Ship-to Name** is the same in the subscription and the contract, the field value displays in bold.

> [!TIP]
> You can also open the **Subscription Lines without Customer Subscription Contracts** page by using the **Subscription Lines without Contracts** part on the **Subscription Billing** Role Center, or by using TellMe search. In this case, the subscription lines aren't filtered and the contract number isn't predefined.
>
> In addition to **Subscription Billing**, the part is also available on the **Company Hub**, **Business Manager**, **Service Manager**, **Sales Order Processor**, **Project Manager** and **Sales & Relationship Manager** Role Centers.

When the subscription lines are assigned to a contract, contract lines are created with the content of the subscription lines. Changes to contract lines transfer to the subscription lines. The **Quantity** field displays the quantity of the related subscription.

> [!NOTE]
> If an alternate ship-to party isn't entered in the contract when the first service is assigned to a customer subscription contract, the contract uses the ship-to party assigned to the subscription. This assignment makes it easier to create a contract when you map a partner model.
>
> Subscription lines are usually created automatically when you post the shipment in the sales order. The requirement is a corresponding setup in the item or subscription package.

> [!TIP]
> Editing contract lines instead of subscription lines in the individual subscriptions makes work easier. Because the content of subscription lines that are billed together are usually similar, making them part of the same contract can make it easier to access and edit them from the contract.

> [!NOTE]
> You can manually enter text lines on contract lines. Text lines are used as internal notes for the person processing the contract. The basis for billing is always a subscription line.

The next step is to create invoices for the contract.

## Create an invoice per contract

In subscription billing, you typically create contract invoices from the **Recurring Billing** page. To learn more, go to [Recurring billing](../recurring-billing.md). This page is designed to generate billing proposals in batch. In addition, several options are available for creating posting documents, such as collective invoices. To learn more, go to [Posting documents](../posting-documents.md).

However, it might also be useful to create a contract invoice for a contract that you're working on, without first creating a billing proposal. In that case, you can use the **Create Contract Invoice** action on the **Customer Subscription Contracts** and **Customer Subscription Contract** pages. You can specify the key date for billing in the **Billing Date** field, and, optionally, the date up to which billing is to take place in the **Billing to Date** field. In addition, you can specify the **Document Date** and the **Posting Date** for the posting documents to create. If you turn on the **Open document** toggle, the created document opens. Optionally, you can turn on the **Post document** toggle to post the created document directly. Except for **Billing to Date**, all fields are predefined with the work date specified on the **My Settings** page.

> [!NOTE]
> Creating a contract invoice as described here is only useful in individual cases.

## Details for contract invoices

On the **Customer Subscription Contract** page, on the **Invoice Details** FastTab, the **Detail Overview** field controls whether invoices automatically contain billing details. You can specify whether the details should include prices. This field also serves as a criterion when you create collective invoices, and must have the same value for all contracts to combine.

The **Contractor Name in collective Invoice** and **Recipient Name in collective Invoice** fields determine whether and which customer names to transfer to collective invoices. When you create a new customer subscription contract, the **Origin Name for collective Sales Invoice** field is filled in by the invoice details. To learn more, go to [Invoice details](../setup/general.md#invoice-details). However, you can also set this per contract.

## Extend contract

If you want to extend a contract with an additional component, you can use the **Extend Contract** action on the **Customer Subscription Contract** page. The action creates a subscription and assigns the related subscription lines to a customer and/or vendor contract.

The **Extend Contract** page has three FastTabs. On the **Vendor** FastTab, use the **Vendor Subscription Contract No.** field to select the vendor contract for the vendor-side subscription lines. The field is only editable if you turn on the **Extend Vendor Contract** toggle. The **Customer** FastTab is similar. On the **Item** FastTab, in the **Item No.** field, specify the item that corresponds to the new contract element. You can also fill in the **Quantity** and **Provision Start Date** fields. The AssistEdit :::image type="content" source="../../media/assist-edit-icon.png" alt-text="AssistEdit icon."::: for the **Additional Subscription lines** field lets you specify optional subscription lines for the selected item.

The **Extend Contract** page is slightly different, depending on how you open it. The values from the last time you opened it display the next time you open it. When you open it from the **Customer Subscription Contract** or **Vendor Subscription Contract** pages, the **Customer** or **Vendor** FastTabs show information about the customer or vendor.

You can also open the page from the menu or via TellMe search. In this case, the values of the last call are also used as default values. However, the **OK** button isn't available to run the action. To run the action, use the **Perform Extension** action. The **Perform Extension** action isn't available when you open the page from a customer or vendor contract.

## Invoice discounts

To learn more about mapping lump sum discounts for an entire contract, go to [Invoice discounts](contracts-services-mgmt.md#invoice-discounts).

## Closed contract lines

After you specify an end date for a contract line, either manually or by using the [Job queue](../setup/job-queue.md), you can't bill the line. Lines that are ended don't display in the default view of the contract. However, on the **Customer Subscription Contract** page, the lines display on the **Closed Lines** FastTab. For example, if needed, you can use this information to recreate them on a contract.

With the exception of the **Closed** checkbox, you can edit fields on closed lines. If you clear the checkbox, the line moves back to the **Lines** FastTab and is editable. Then, for example, you can adjust the subscription line end date. If you don't make a change, the line moves back to the **Closed Lines** FastTab the next time you use the **Update Subscription Line Dates** action. To learn more about updating cancellation dates and deadlines and ending contract lines, go to [Termination of subscription contract components](service-commitment-cancellation.md).

## Merge contract lines

Over time, a customer might purchase similar or identical subscription lines. For example, if they purchase additional users for an existing license. To invoice these subscription lines together, on the **Customer Subscription Contract** card, select the lines, and then use the **Merge Subscription Contract Lines** action to combine the subscription lines.

You can only merge contract lines if all lines meet the following criteria:

* No billing proposal lines exist for any of the subscription lines.
* The dimensions are identical.
* The end user details are identical.
* The items of the subscriptions are identical.
* The **Customer References** of the subscriptions are identical.
* Subscriptions aren't tracked by serial number.
* The **Next Billing Date** is identical. To learn more, go to [Harmonized billing](#harmonized-billing).

> [!NOTE]
> You can't use the action for text lines.

On the **Select Customer Subscription Contract Line** page, select the contract line on which to combine the selected lines. Afterward, a new subscription is created as a copy of the subscription of the selected contract line, including subscription lines and the total quantity. The subscription lines to combine are closed, and the new line(s) is added to the contract. To learn more, go to [Closed contract lines](#closed-contract-lines). In the original subscriptions, the **Provision End Date** field is set, if possible.

## Harmonized billing

If a customer purchases several subscription lines with a longer billing rhythm (for example, 12 months) at different times and invoiced through the same contract, the invoicing date of the subscription lines is usually different. If the customer wants to align billing on a billing date, select the **Harmonized Billing Customer Subscription Contracts** checkbox on the **Subscription Contract Types** page. To learn more, go to [Subscription Contract Types](../setup/contract-types.md).

If you select this checkbox for the contract type of the customer subscription contract, you can edit the **Billing Base Date** and **Default Billing Rhythm** fields on the **Shipping and Billing** FastTab. When the first subscription line is added to the contract, the fields are predefined based on that data. However, you can change them if needed.

When you create the billing proposal lines, [!INCLUDE [prod_short](../../includes/prod_short.md)] checks whether each subscription line is connected to a contract that uses harmonized billing. If yes, the fields for harmonized billing are considered.

The harmonized billing fields update when when you add, delete, and change subscription lines, if applicable.

> [!TIP]
> If you add subscription lines with a longer billing rhythm (for example, 12 months) to a contract whose **Next Billing Date** is during the year, and these subscription lines (and all those to come) should generally only be billed by the end of the year, you can reset the **Billing Base Date** field to January 1st of the year.

### Special case: Deletion of the first billing proposal

This section describes a special case that requires you to manually intervene.

A contract is to be billed harmonized (for example, per calendar year). Therefore, the **Billing Base Date** in the contract is set to *January 1st* of the current year. Subscription lines are added during the course of the first year. If a billing proposal is now created within, and for, the first year and is later deleted, the **Billing Base Date** uses the *oldest* **Next Billing Date** from the contract lines (subscription lines). This can't be avoided due to the automatic updating of subscription lines and only occurs if the contract wasn't billed. After the first billing, the issue no longer occurs. In this case, you must manually reset the **Billing Base Date** to *January 1st* of the current year.

## Open related information

You can open related information from the contract. For example, you can access related invoices and credit memos. If the postings in the contract are deferred periodically, use the **Contract Deferrals** action to view them.

For lines, you can use the **Billing Lines** and the **Archived Billing Lines** actions to access related information for the selected line. The **Archived Billing Lines** action opens the posted invoice and credit memo.

## Related information

[Subscription contract renewal](contract-renewal.md)  
[Contract deferrals](contract-deferrals.md)  
