---
title: Customer contracts
description: You can use customer contracts in subscription and recurring billing.
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

# Customer contracts

A Customer Contract represents the obligations towards a customer. It is structured similarly to a sales order. The fields in the **General** fast tab contain information about the Contractor, i.e. the contact person for this contract. The lines contain detailed information about the billing of the components of the contract.
In the **Delivery and Billing** fast tab, different delivery and billing recipients (from the Contractor) can be stored.

* **Deviating Shipment Recipient** <br/>
Another word for "shipment recipient" can also be "service recipient" in the contract context. This can be used, for example, in a partner model to record the end customer of the partner. Therefore, the Ship-to information also serves as a visual indicator when assigning new contract elements (see [Assign Service Commitments to a Customer Contract](#assign-service-commitments-to-a-customer-contract)).
* **Different invoice recipient** <br/>
Analogous to the sales order, a deviating invoice recipient can be entered here. This is taken into account when creating the contract invoices.

:::info Contracts in master data
Contracts are visible in the fact box area at the Customer, Vendor and Contact. A click on the respective cue opens the corresponding overview.
:::


## Creating a new Customer Contract
A new Customer Contract is most easily created via the Customer list and the **Contract** action (under *New Document*). With this method, the relevant contact data is also immediately transferred to the newly created Contact Header. Alternatively, enter the term *Customer Contracts* in the search (*Alt+Q*) and open the list of **Customer Contracts**. A new Customer Contract can be created using the **New** function. <br/>
The following steps are necessary to create a contract:
1. Select the customer.
2. Select the **[Contract Type](/docs/srb/setup/contract-types.md)** and enter a short **Description** (both entries are optional).
3. The employee responsible for the contract can be selected in the **Assigned User ID** field. The field is located in the **General** fast tab. Since it is hidden by default, it can be made visible via *Show more*. 
4. Change **Currency Code**, **Payment Terms Code** and **Payment Method Code** in the **Invoice Details** fast tab if required. The details were copied from the customer in step 1.
5. Select whether a **Detail Overview** is to be output for invoices.
6. Check and, if necessary, change the details in the **Shipping and Billing** fast tab regarding the shipping recipient (**Ship-to**) and the invoice recipient (**Bill-to**).

:::tip Tip
**Contract Type** and **Assigned User ID** can be used as filters in **[Recurring Billing](/docs/srb/recurring-billing.md)**. Using these (and other) filters, contracts can be billed separately based on type and clerk.
:::


## Assign Service Commitments to a Customer Contract
In order to bill Service Commitments, they must be assigned to a contract. New contract lines (Service Commitments) can be added to the contract using the **Get Service Commitments** action (under *Process*). The **Services Commitments without Customer Contract** page opens. Here, all Service Commitments for the customer are listed, which are to be invoiced via a contract, but are not yet assigned to a contract. The determination, which Service Commitments are shown, is based on the customer in the Service Object (see fast tab **End User** in [Service Object](/docs/srb/working-with-contracts/service-objects.md)). When called in a contract, the Contract No. is predefined in the Service Commitments (in the **Assign to Contract No.** field). <br/>
If the **Ship-to Name** is the same in the Service Object and the contract, the field will be displayed formatted **boldly**.

> [!TIP]
> The page **Services Commitments without Customer Contracts** can also be called up via the role center part **Service Commitments without Contracts** or via the search (*Alt+Q*). In this case, the service commitments are not filtered and the contract number is not predefined.
>
> In addition to the Role Center **Subscription & Recurring Billing**, the Role Center part is also available in the Role Centers **Company Hub**, **Business Manager**, **Service Manager**, **Sales Order Processor**, **Project Manager** and **Sales & Relationship Manager**.

When the service commitments in a contract are transferred, **Contract lines** are created. These reflect the content of the service commitments. Any changes to the contract lines are automatically reflected in the service commitments. The **Quantity** field displays the quantity of the related service object.

> [!NOTE]
> If no deviating ship-to party is entered in the contract at the time the first service is assigned to a customer contract, the ship-to party stored in the **Service Object** is transferred to the contract. This facilitates the contract creation when mapping a partner model.
>
> Service commitments are usually created automatically when the shipment is posted in the sales order. The prerequisite for this is a corresponding setup in the item used or in the service commitment package, respectively.

> [!TIP]
> Editing contract lines instead of service commitments in the individual service objects makes work easier. Since the service commitments that are to be billed together usually also belong together in terms of content, it makes sense that they are all part of the same contract. This way they can be quickly viewed and edited via the contract.

> [!CAUTION]
> Manual entry of contract lines is only possible for text lines. These are only used as an internal note for the contract processor and are not processed further. The basis for a billing is always a service commitment.
Only text lines that are marked as [Bundle](/docs/srb/bundles.md) will be included in the invoice.

## Extend contract

If a contract is to be extended by an additional component as simply as possible, the action **Extend Contract** (under *Process*) is available for this purpose. It is used to create a service object in *only one step* and to assign the related service commitments to a customer and/or vendor contract.

The page that opens is divided into three sections. In the first part (*Vendor*), the **Vendor Contract No.** field can be used to select the vendor contract that is to accommodate the (possible) vendor-side service commitments. The field is only editable if **Extend Vendor Contract** is activated at the same time. The second part of the page (*Customer*) behaves analogously to the first part. In the third part, in the **Item No.** field, the item corresponding to the new contract element must be specified. Further specifications can be made via **Quantity** and **Provision Start Date**. The AssistEdit at **Additional Service Commitments** allows to specify optional service commitments of the selected item.

The page behaves slightly differently depending on the way it is called. Basically, the values of the last call are saved (per user). They are used for presetting the next time the page is opened. When calling from a customer contract, the part *Customer* is predefined accordingly. The same applies analogously to the part *Vendor* for the call from a vendor contract. In both cases the contract extension is executed with a click on *OK*.

Besides the call from a Contract Card, the page can also be called directly from the menu. In this case, the values of the last call are also used as default values. However, there is no OK button available for the execution (due to system technical reasons). It is done by calling the action **Perform Extension**. This action is not visible when called from a customer or vendor contract.

## Invoice discounts

Mapping lump sum discounts for an entire contract is explained in more detail in [this](/docs/srb/working-with-contracts/contracts-services-mgmt.md#invoice-discounts).

## Closed contract lines

If the service end date was entered for a contract line or it was [automatically updated](../setup/job-queue.md), this line can no longer be billed in the future. Therefore, ended lines will no longer be displayed in the default view of the contract card. However, via the **Closed Lines** FastTab, it is possible to continue to view these lines and thus to reconstruct at a later date what was once part of the contract.

The fields of a terminated line are not editable except for **Closed**. If the check mark in this field is removed, the line is moved back to the **Lines** FastTab and is thus editable again. Then, for example, the service end date can be adjusted. If no change is made, the line will be moved back to the **Closed Lines** FastTab the next time **Update Service Dates** is called. For more information on updating cancellation dates and deadlines and ending contract lines, go to [Termination of contract components](service-commitment-cancellation.md).

## Merge contract lines

In the course of time, it may happen that a customer purchases similar or identical service commitments, for example, as a subsequent purchase of additional users to an already existing license. In order to be able to invoice these service commitments together, it is possible to combine these service commitments using the action **Merge Contract Lines** in the line menu of the Customer Contract.

Before calling the action, the contract lines to be merged must be selected. Contract lines can only be merged if the following criteria are met for all lines:

* No billing proposal lines exist for any of the service commitments.
* The dimensions are identical.
* The end user details are identical.
* The items of the service objects are identical.
* The **Customer References** of the service objects are identical.
* Service objects are not tracked by serial number.
* The **Next Billing Date** is identical (see also the option for [harmonization of Contract elements](#harmonized-billing)).

However, the following do not have to be identical:

* Service Objects
    * Quantity
    * Description
    * Provision Start Date
    * Provision End Date
* Service Commitments
    * Description
    * Service Start Date
    * Cancellation possible until
    * Term until

> [!NOTE]
> The function cannot be called for text lines.

The **Select Customer Contract line** page opens, in which the contract line must be selected to which the previously selected lines are to be combined. Afterwards a new service object (as a copy of the service object of the selected contract line) including service commitments will be created. The total quantity is taken over. The service commitments to be combined are [terminated](#closed-contract-lines) and the new service is added to the contract. In the old service objects, the **Provision End Date** field is set, if possible.

## Create invoice per contract

Normally, contract invoices in **Subscription & Recurring Billing** are created via [Recurring billing](../recurring-billing.md). This feature is designed to generate billing proposals in batch. In addition, several options are available for creating the [Posting documents](../posting-documents.md) (for example, collective invoices).

Nevertheless, it may also be useful or necessary to create a contract invoice for the one contract that is currently being worked on - without first creating a billing proposal for it. For this use case the action **Create contract invoice** can be used. It is available both in the customer contracts overview and in the customer contract card.

In the query that opens, the key date for billing (**Billing Date**) and, optionally, the date up to which billing is to take place (**Billing To**) can be specified. In addition, the **Document Date** and the **Posting Date** can be specified for the [Posting documents](../posting-documents.md) to be created. If the **Open document** flag is set, the created document will be opened directly afterwards. Optionally, the created document can also be posted directly (**Post document**). Except for **Billing To**, all fields are predefined with the work date (see page **My Settings**).

> [!NOTE]
> The creation of a contract invoice via the method described here is only useful in individual cases.

## Details for contract invoices

In the **Invoice Details** fast tab, the **Detail Overview** field per contract controls whether billing details are automatically output for each invoice. It can be differentiated whether the details should be output with or without prices (Complete / Without prices). In addition, this field serves as a criterion with regard to the creation of collective invoices, as it must have the same value for all contracts to be combined.

The fields **Contractor Name in collective Invoice** and **Recipient Name in collective Invoice** determine whether and if so, which customer names are transferred to collective invoices and output there. When creating a new customer contract, the **Origin Name for collective Sales Invoice** field from [Invoice details](../setup/general.md#invoice-details) is interpreted. However, the setting can be made per contract. Decisive for the creation of the collective invoice are the fields of the respective customer contract.

## Harmonized billing

If several Service Commitments with a longer billing rhythm (for example, 12 months) are purchased by the customer at different times and invoiced via the same contract, the invoicing date of the services is usually different. If the customer wishes to have aligned billing on a *billing date*, the **Harmonized Billing Customer Contracts** indicator from the [Contract types](../setup/contract-types.md) can be used for this purpose.

If this flag is set for the contract type of the customer contract, the **Billing Base Date** and **Default Billing Rhythm** fields (in the *Harmonized Billing* group in the **Shipping and Billing** fast tab) are editable. When the first service commitment is added to the contract, the fields are predefined based on that data. However, they can be changed manually.

When creating the billing proposal lines, a check is made for each service commitment to see if it is connected to a contract being billed in a harmonized manner. If yes, the *harmonization fields* will be considered accordingly.

The harmonization fields will be updated when adding, deleting and modifying a service commitments, if applicable.

> [!TIP]
> If service commitments with a longer billing rhythm (for example, 12 months) are added to a contract whose **Next Billing Date** is during the year, and these service commitments (and all those to come) should generally only be billed by the end of the year, the **Billing Base Date** can be reset to January 1st of the year.

### Special case: Deletion of the first billing proposal

There is a well-known special case in which manual intervention by the user is required:

A contract is to be billed harmonized (e.g. per calendar year). Therefore, the **Billing Base Date** in the contract header (in the *Shipping and Billing* fast tab) is set to *January 1st* of the current year. Service commitments will be added during the course of the first year. If a billing proposal is now created within and for the first year *and subsequently deleted*, the **Billing Base Date** will be overwritten with the *oldest* **Next Billing Date** from the contract lines (service commitments). This cannot be avoided due to the automatic updating of service commitments and only occurs as long as the contract has never been billed. After the first billing, the behavior then no longer occurs. In this case, the **Billing Base Date** must be manually reset to *January 1st* of the current year.

## Linked information

Linked information can be called from the contract. In the menu (in the *Related* group) all invoices and credit memos can be accessed. In the menu group *Related / Customer Contract* the **Contract Deferrals** can be viewed if the postings in the contract are deferred periodically.

Using the line menu *Contract Line* the **Billing Lines** and the **Archived Billing Lines** can be displayed. The information is opened for the selected contract line. The **Archived Billing Lines** can be opened in the posted invoice and credit memo as well.