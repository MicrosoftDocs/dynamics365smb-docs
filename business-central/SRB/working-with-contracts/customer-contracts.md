---
title: Customer contracts
description: You can use customer contracts in subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Customer contracts

Customer contracts represent obligations to customers. The structure of contracts is similar to sales orders. On the **Customer Contract** page, the fields on the **General** FastTab contain information about the contractor, such as their contact person. The lines contain information about the billing of the components of the contract.

On the **Shipping and Billing** FastTab, you can specify ship-to and bill-to recipients for the contractor.

* **Alternate shipping address** or **Custom Address** for the **Ship-to** address.
   In the context of a contract, another word for *shipment recipient* could be *service recipient*. For example, you can use this concept in a partner model to record the end customer of the partner. Therefore, the ship-to information also serves as a visual indicator when assigning new contract elements. To learn more, go to [Assign service commitments to a customer contract](#assign-service-commitments-to-a-customer-contract).
* **Custom Address** or **Another Customer** for the **Bill-to** address.
   Similar to sales orders, a deviating invoice recipient can be entered here. This is taken into account when creating the contract invoices.

> [!NOTE]
> Contracts are available in the **Sell-to Customer Sales History** FactBox on the the **Customer Card**, **Vendor Card**, and **Contact Card** pages. Choose the respective cue to open an overview.

## Overview of the process for creating a customer contract

The following are the high-level steps to create a contract for a customer.

1. [Enter basic settings](#create-a-new-customer-contract).
2. [Assign service commitments](#assign-service-commitments-to-a-customer-contract).
3. [Create invoice per contract](#create-invoice-per-contract).

### Create a new customer contract

On the **Customers** page, use the **Contract** action to quickly create a new customer contract. The contact data for the customer transfers to the new contract.

To create a contract, follow these steps:

1. Choose the :::image type="content" source="../../media/ui-search/search_small.png" alt-text="Tell me what you want to do icon."::: icon, enter **Customers**, then choose the related link.
2. Select the customer, and then choose the **Contract** action.
3. Optionally, fill in the **Contract Type** and **Description** fields. To learn more about contract types, go to [Contract types](../setup/contract-types.md).
4. In the **Assigned User ID** field, choose the employee who's responsible for the contract.
5. If needed, change the values in the **Currency Code**, **Payment Terms Code**, and **Payment Method Code** fields on the **Invoice Details**. The values were copied from the customer in step 1.
6. Select whether a **Detail Overview** is to be output for invoices.
7. On the **Shipping and Billing** FastTab, verify the values in the **Ship-to** and **Bill-to** fields.
8. The next step is to assign service commitments. To learn more, go to [Assign service commitments to a customer contract](#assign-service-commitments-to-a-customer-contract).  

> [!TIP]
> You can use the **Contract Type** and **Assigned User ID** fields as filters in subscription billing to bill contracts separately based on type and clerk.

There are two ways to add service commitments to a contract. You can assign service commitments from released orders using the **Get Service Commitments** action on the customer contract, or you can also extend the a contract, if needed. To learn more, go to [Extend contract](#extend-contract).

### Assign service commitments to a customer contract

To bill service commitments, you must assign them to a contract. On the **Customer Contract** page, use the **Get Service Commitments** action to assign service commitments. The **Services Commitments without Customer Contract** page displays the service commitments for the customer that you invoice through a contract, but aren't yet assigned to a contract. The service commitments that display are based on the customer on the service object. To learn more, go to [Service objects](service-objects.md). When you open them in a contract, the **Contract No.** field is predefined in **Assign to Contract No.** on the service commitment.

If the **Ship-to Name** is the same in the service object and the contract, the field value displays in bold.

> [!TIP]
> You can also open the **Services Commitments without Customer Contracts** page by using the **Service Commitments without Contracts** part on the **Subscription & Recurring Billing** Role Center, or by using TellMe search. In this case, the service commitments aren't filtered and the contract number isn't predefined.
>
> In addition to the **Subscription & Recurring Billing**, the part is also available on the **Company Hub**, **Business Manager**, **Service Manager**, **Sales Order Processor**, **Project Manager** and **Sales & Relationship Manager** Role Centers.

When the service commitments in a contract transfer, contract lines are created with the content of the service commitments. Changes to contract lines transfer to the service commitments. The **Quantity** field displays the quantity of the related service object.

> [!NOTE]
> If an alternate ship-to party isn't entered in the contract when the first service is assigned to a customer contract, the contract uses the ship-to party assigned to the service object. This assignment makes it easier to create a contract when you map a partner model.
>
> Service commitments are usually created automatically when you post the shipment in the sales order. The requirement is a corresponding setup in the item or service commitment package.

> [!TIP]
> Editing contract lines instead of service commitments in the individual service objects makes work easier. Because the content of service commitments that are billed together are usually similar, making them part of the same contract can make it easier to access and edit them from the contract.

> [!CAUTION]
> You can only manually enter text lines on contract lines. Text lines are used as internal notes for the person processing the contract. The basis for billing is always a service commitment.

The next step is to create invoices for the contract.

## Create invoice per contract

In subscription billing, you typically create contract invoices from the **Recurring Billing** page. To learn more, go to [Recurring billing](../recurring-billing.md). Recurring billing is designed to generate billing proposals in batch. In addition, several options are available for creating posting documents, such as collective invoices. To learn more, go to [Posting documents](../posting-documents.md).

However, it might also be useful to create a contract invoice for a contract that you're working on, without first creating a billing proposal. In that case, you can use the **Create contract invoice** action on the **Customer Contracts** and **Customer Contract** pages. You can specify the key date for billing in the **Billing Date** field, and, optionally, the date up to which billing is to take place in the **Billing To** field. In addition, you can specify the **Document Date** and the **Posting Date** for the posting documents to create. If you turn on the **Open document** toggle, the created document opens. Optionally, you can turn on the **Post document** toggle to post the created document directly. Except for **Billing To**, all fields are predefined with the work date specified on the **My Settings** page.

> [!NOTE]
> Creating a contract invoice as described here is only useful in individual cases.

## Details for contract invoices

On the **Customer Contract** page, on the **Invoice Details** FastTab, the **Detail Overview** field controls whether invoices automatically contain billing details. You can specify whether the details should include prices. This field also serves as a criterion when you create collective invoices, and must have the same value for all contracts to combine.

The **Contractor Name in collective Invoice** and **Recipient Name in collective Invoice** fields determine whether and which customer names to transfer to collective invoices. When you create a new customer contract, the **Origin Name for collective Sales Invoice** field is filled in by the invoice details. To learn more, go to [Invoice details](../setup/general.md#invoice-details). However, you can also set this per contract.

## Extend contract

If you want to extend a contract with an additional component, use the **Extend Contract** action on the **Customer Contract** page. The action creates a service object and assigns the related service commitments to a customer and/or vendor contract.

The **Extend Contract** page has three FastTabs. On the **Vendor** FastTab, use the **Vendor Contract No.** field to select the vendor contract for the vendor-side service commitments. The field is only editable if you turn on the **Extend Vendor Contract** toggle. The **Customer** FastTab is similar. On the **Item** FastTab, in the **Item No.** field, specify the item that corresponds to the new contract element. You can also fill in the **Quantity** and **Provision Start Date** fields. The AssistEdit :::image type="content" source="../../media/assist-edit-icon.png" alt-text="AssistEdit icon."::: for the **Additional Service Commitments** field lets you specify optional service commitments for the selected item.

The **Extend Contract** page is slightly different, depending on how you open it. The values from the last time you opened it display the next time you open it. When you open it from the **Customer Contract** or **Vendor Contract** pages, the **Customer** or **Vendor** FastTabs shows information about the customer or vendor.

You can also open the page from the menu. In this case, the values of the last call are also used as default values. However, the **OK** button isn't available to run the action. To run the action, use the **Perform Extension** action. The **Perform Extension** action isn't available when you open the page from a customer or vendor contract.

## Invoice discounts

To learn more about mapping lump sum discounts for an entire contract, go to [Invoice discounts](contracts-services-mgmt.md#invoice-discounts).

## Closed contract lines

After you specify a service end date for a contract line, either manually or by using the [Job queue](../setup/job-queue.md), you can't bill the line. Lines that are ended don't display in the default view of the contract. However, on the **Customer Contract** page, the lines display on the **Closed Lines** FastTab. For example, if needed, you can use this information to recreate them on a contract.

With the exception of the **Closed** checkbox, you can edit fields on closed lines. If you clear the checkbox, the line moves back to the **Lines** FastTab and is editable. Then, for example, you can adjust the service end date. If you don't make a change, the line moves back to the **Closed Lines** FastTab the next time you use the **Update Service Dates** action. To learn more about updating cancellation dates and deadlines and ending contract lines, go to [Termination of contract components](service-commitment-cancellation.md).

## Merge contract lines

Over time, a customer might purchase similar or identical service commitments. For example, if they purchase additional users for an existing license. To invoice these service commitments together, on the **Customer Contract** card, select the lines, and then use the **Merge Contract Lines** to combine these service commitments.

You can only merge contract lines if all lines meet the following criteria:

* No billing proposal lines exist for any of the service commitments.
* The dimensions are identical.
* The end user details are identical.
* The items of the service objects are identical.
* The **Customer References** of the service objects are identical.
* Service objects aren't tracked by serial number.
* The **Next Billing Date** is identical. To learn more, go to [Harmonized billing](#harmonized-billing).

> [!NOTE]
> You can't use the action for text lines.

On the **Select Customer Contract line** page, select the contract line on which to combine the selected lines. Afterward, a new service object is created as a copy of the service object of the selected contract line, including service commitments and the total quantity. The service commitments to combine are closed, and the new service is added to the contract. To learn more, go to [Closed contract lines](#closed-contract-lines). In the original service objects, the **Provision End Date** field is set, if possible.

## Harmonized billing

If a customer purchases several service commitments with a longer billing rhythm (for example, 12 months) at different times and invoiced through the same contract, the invoicing date of the services is usually different. If the customer wants to align billing on a billing date, select the **Harmonized Billing Customer Contracts** checkbox on the **Contract Types** page. To learn more, go to [Contract types](../setup/contract-types.md).

If you select this checkbox for the contract type of the customer contract, you can edit the **Billing Base Date** and **Default Billing Rhythm** fields on the **Shipping and Billing** FastTab. When the first service commitment is added to the contract, the fields are predefined based on that data. However, you can change them if needed.

When you create the billing proposal lines, [!INCLUDE [prod_short](../../includes/prod_short.md)] checks whether each service commitment is connected to a contract that uses harmonized billing. If yes, the fields for harmonized billing are considered.

The harmonized billing fields update when when you add, delete, and change service commitments, if applicable.

> [!TIP]
> If you add service commitments with a longer billing rhythm (for example, 12 months) to a contract whose **Next Billing Date** is during the year, and these service commitments (and all those to come) should generally only be billed by the end of the year, you can reset the **Billing Base Date** field to January 1st of the year.

### Special case: Deletion of the first billing proposal

This section describes a special case that requires you to manually intervene.

A contract is to be billed harmonized (for example, per calendar year). Therefore, the **Billing Base Date** in the contract is set to *January 1st* of the current year. Service commitments are added during the course of the first year. If a billing proposal is now created within, and for, the first year and is later deleted, the **Billing Base Date** uses the *oldest* **Next Billing Date** from the contract lines (service commitments). This can't be avoided due to the automatic updating of service commitments and only occurs as long as the contract wasn't billed. After the first billing, the issue no longer occurs. In this case, you must manually reset the **Billing Base Date** to *January 1st* of the current year.

## Related information

You can open related information from the contract. For example, you can access related invoices and credit memos. If the postings in the contract are deferred periodically, use the **Contract Deferrals** action to view them.

For lines, you can use the **Billing Lines** and the **Archived Billing Lines** actions to access related information for the selected line. The **Archived Billing Lines** action opens the posted invoice and credit memo.

## Related information

[Contract renewal](contract-renewal.md)  
[Contract deferrals](contract-deferrals.md)  
