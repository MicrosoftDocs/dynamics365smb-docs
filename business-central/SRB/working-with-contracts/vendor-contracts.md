---
title: Vendor subscription contracts
description: You can use vendor subscription contracts in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 8071,
ms.date: 07/11/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Vendor subscription contracts

A vendor contract maps liabilities to suppliers or manufacturers. The structure of vendor subscription contracts is similar to purchase orders. The fields in the **General** FastTab contain information about the contract partner. For example, the supplier's contact person for this contract. The lines contain detailed information about the billing of the components of the contract.

On the **Payment** tab, you can specify a different payee (from the contract partner) in the **Pay-to** field. Similar to purchase orders, this setting is used when creating the contract invoices.

> [!NOTE]
> Contracts display on the FactBox pane for customers, vendors, and contacts. Choose the cue to open the corresponding overview.

## Create a new vendor contract

Use the **Subscription Contract** action on the **Vendors** list page to create a new vendor contract. The action copies the relevant contact information to the contract. Alternatively, enter *vendor subscription contracts* in the TellMe search (*Alt+Q*) and open the list of vendor subscription contracts. Use the **New** action to create a new vendor contract.

The procedure for creating a new vendor contract is similar to that for customer subscription contracts. The following steps are necessary to create a contract.

1. Select the vendor.
2. Select the contract type, and enter a short **Description** (both entries are optional). To learn more about subscription contract types, go to [Subscription contract types](../setup/contract-types.md).
3. On the **General** FastTab, in the **Assigned User ID** field, choose the employee who's responsible for the contract. The field is hidden by default, so you might need to choose **Show more**. 
4. If needed, on the **Invoice Details** FastTab, change or fill in the **Currency Code**, **Payment Terms Code** and **Payment Method Code** fields. The details were copied from the vendor in step 1.
5. If needed, on the **Payment** FastTab, in the **Pay-to** field, change the payee.

## Assign subscription lines to a vendor subscription contract

To bill subscription lines, they must be assigned to a contract. Use the **Get Subscription lines** action (under *Process*) to add new contract lines (subscription lines) to the contract. The **Subscription Lines without Vendor Subscription Contract** page opens. The page lists all subscription lines for vendors that you invoice via a contract, but aren't assigned to a contract. When called in a contract, the contract number and the vendor are predefined in the subscription lines (in the **Assign to Contract No.** and **Vendor** fields). When you transfer subscription lines to a contract, **Contract Lines** are created. The lines reflect the content of the subscription lines. Changes to the contract lines are reflected in the subscription lines. The **Quantity** field displays the quantity of the related subscription.
Alternatively, the **Subscription Lines without Vendor Subscription Contract** page can also be accessed via the Role Center or via TellMe search (*Alt+Q*). In this case, the contract number and vendor are not predefined.

> [!TIP]
> You can only transfer subscription lines that have the **Vendor** as **Partner** to vendor subscription contracts. Because you can't store a vendor in the subscription, you can assign vendor-side subscription lines to any vendor contract.

> [!NOTE]
> Subscription lines are usually created automatically when the shipment is posted in the sales order. The prerequisite for this is a corresponding setup in the item used or the subscription package.

## Extend contract

If you want to extend a contract by an additional component, you can use the **Extend Contract** action. The action creates a subscription and assigns the related subscription lines to a customer and/or vendor contract.

The page is divided into three sections. In the first part, **Vendor**, use the **Vendor Subscription Lines without Vendor Subscription Contract Contract No.** field to select the vendor contract that is to accommodate the (possible) vendor-side subscription lines. The field is only editable if **Extend Vendor Contract** is active. The second part of the page, **Customer**, is similar. In the third part, in the **Item No.** field, specify the item that corresponds to the new contract element. You can use the **Quantity** and **Provision Start Date** fields to add more detail. The AssistEdit :::image type="content" source="../../media/assist-edit-icon.png" alt-text="The AssistEdit icon."::: on **Additional Subscription lines** allows you to specify optional subscription lines for the selected item.

The page behaves slightly differently, depending on how it's called. Basically, the values of the last call are saved (per user). The settings are used to preset the next time the page is opened. When calling from a customer subscription contract, the **Customer** part is predefined accordingly. The same applies to the **Vendor** part for the call from a vendor contract. In both cases, the contract extension runs when you choose **OK**.

> [!NOTE]
> In addition to the **Contract Card** page, you can also open the page from the menu. In this case, the values of the last call are also used as default values. However, there isn't an OK button to run the action. Instead, use the **Perform Extension** action. This action isn't available when you open the page from a customer or vendor contract.

## Invoice discounts

To learn more about mapping lump sum discounts for an entire contract, go to [Invoice discounts](contracts-services-mgmt.md#invoice-discounts).

## Closed contract lines

If the service end date was entered for a contract line, or it was automatically updated in the [Job queue](../setup/job-queue.md), you can't bill the line. Therefore, ended lines won't display in the default view of the **Contract Card** page. However, the **Closed Lines** FastTab continues to show these lines. You can use the lines at a later date to reconstruct what was once part of the contract.

The fields on a terminated line aren't editable, except for **Closed**. If you clear the checkbox, the line is moved back to the **Lines** FastTab and you can edit it. Then, for example, you can adjust the service end date. If no change is made, the line moves back to the **Closed Lines** FastTab the next time **Update Subscription Line Dates** is called. To learn more about updating cancellation dates and deadlines and ending contract lines, go to [Termination of contract components](service-commitment-cancellation.md).

## Merge contract lines

Over time, you might purchase similar or identical subscription lines from a supplier. For example, when you buy additional users for an existing license. To invoice these subscription lines together, you can use the **Merge Contract Lines** action in the line menu of the vendor contract to combine these subscription lines.

Before you use the action, select the contract lines to merged. You can merge contract lines only if all lines meet the following criteria:

* Billing proposal lines don't exist for any of the subscription lines.
* The dimensions are identical.
* The end user details are identical.
* The items of the subscriptions are identical.
* The customer references of the subscriptions are identical.
* Subscriptions aren't tracked by serial numbers.
* The next billing date is identical.

However, the following can't be identical:

* Subscriptions
    * Quantity
    * Description
    * Provision Start Date
    * Provision End Date
* Subscription lines
    * Description
    * Service Start Date
    * Cancellation possible until
    * Term until

> [!NOTE]
> You can't use the action for text lines.

Use the **Select Vendor Subscription Contract Line** page to select the contract line on which to combine the selected lines. A new subscription (as a copy of the subscription of the selected contract line), including subscription lines, is created with the total quantity. The subscription lines to combine are [closed](#closed-contract-lines), and the new lines are added to the contract. In the old subscriptions, the **Provision End Date** field is set, if possible.

## Create an invoice per contract

Typically, you create contract invoices through recurring billing. To learn more, go to [Recurring billing](../recurring-billing.md). Recurring billing is designed to generate billing proposals in batches. In addition, there are several options for creating posting documents, such as collective invoices. To learn more, go to [Posting documents](../posting-documents.md).

Recurring billing can be useful for creating a contract invoice for a contract that you're working on, without first creating a billing proposal. In this scenario, use the **Create Contract Invoice** action on the **Vendor Subscription Contracts** or **Vendor Subscription Contract Card** pages. You can specify the key date for billing (**Billing Date**) and, optionally, the date up to which billing is to take place (**Billing To**). In addition, you can also specify the **Document Date** and the **Posting Date** can be specified for the posting document. If the **Open document** checkbox is selected, the document opens immediately. Except for the **Billing To** field, all fields are predefined with the work date. The work date is defined on the **My Settings** page.

> [!NOTE]
> Creating a contract invoice as described here is only useful in individual cases.

## Access related information

You can access related information from a contract, and you can access all invoices and credit memos. You can view **Contract Deferrals** if the postings in the contract are deferred periodically.

For lines, you can use the **Billing Lines** and the **Archived Billing Lines** actions to access related information for the selected line. You can also open **Archived Billing Lines** in the posted invoice and credit memo.

## Related information

[Customer subscription contracts](customer-contracts.md)
