---
title: Vendor contracts
description: You can use vendor contracts in subscription and recurring billing.
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

# Vendor contracts

A Vendor Contract maps liabilities to suppliers or manufacturers. It is structured similarly to a purchase order. The fields in the **General** fast tab contain information about the contract partner, i.e. the supplier's contact person for this contract. The lines contain detailed information about the billing of the components of the contract.

In the **Payment** info tab, a different payee (from the contract partner) can be stored.
* **Deviating payee** <br/>
Analogous to the purchase order, a deviating payee can be entered here. This is taken into account when creating the contract invoices.

:::info Contracts in master data
Contracts are visible in the fact box area at the Customer, Vendor and Contact. A click on the respective cue opens the corresponding overview.
:::


## Creation of a new Vendor Contract
A new Vendor Contract is most simply created via the Vendor list and the **Contract** action (under *New Document*). This method will also immediately copy the relevant contact information into the newly created Contract Header. Alternatively, enter the term *Vendor Contracts* in the search (*Alt+Q*) and open the list of **Vendor Contracts**. Use the **New** function to create a new Vendor Contract. <br/>
The procedure for creating a new Vendor Contract is similar to that for Customer Contracts. The following steps are necessary to create a contract:
1. Select the vendor.
2. Select the **[Contract Type](/docs/srb/setup/contract-types.md)** and enter a short **Description** (both entries are optional).
3. The employee responsible for the contract can be selected in the **Assigned User ID** field. The field is located in the **General** fast tab. Since it is hidden by default, it can be made visible via *Show more*. 
4. Change **Currency Code**, **Payment Terms Code** and **Payment Method Code** in the **Invoice Details** fast tab if required. The details were copied from the vendor in step 1.
5. If necessary, change the payee (**Pay-to**) in the Payment fast tab.


## Assigning Service Commitments to a Vendor Contract
In order to bill Service Commitments, they must be assigned to a contract. New contract lines (Service Commitments) can be added to the contract using the **Get Service Commitments** action (under *Process*). The **Services Commitments without Vendor Contract** page opens. Here, all the Service Commitments for vendors are listed, which are to be invoiced via a contract, but are not yet assigned to a contract. When called in a contract, the Contract No. and the vendor are predefined in the Service Commitments (in the **Assign to Contract No.** and **Vendor** field). When the Service Commitments are transferred into a contract, **Contract Lines** are created. These reflect the content of the Service Commitments. Any changes made to the contract lines are automatically reflected in the Service Commitments. The **Quantity** field displays the quantity of the related Service Object. <br/>
Alternatively, the **Services without Vendor Contracts** page can also be accessed via the Role Center or via the search (*Alt+Q*). In this case, the Contract No. and Vendor are not predefined.

:::info
Only Service Commitments that have *Vendor* as **Partner** can be transferred to Vendor Contracts.
Since no vendor can be stored in the Service Object, vendor-side Service Commitments can be assigned to any Vendor Contract.
:::

:::note Note
Service Commitments are usually created automatically when the shipment is posted in the sales order. The prerequisite for this is a corresponding setup in the item used or in the Service Commitment Package.
:::


## Extend contract
If a contract is to be extended by an additional component as simply as possible, the action **Extend Contract** (under *Process*) is available for this purpose. It is used to create a Service Object in *only one step* and to assign the related Service Commitments to a Customer and/or Vendor Contract. <br/>
The page that opens is divided into three sections. In the first part (*Vendor*), the **Vendor Contract No.** field can be used to select the Vendor Contract that is to accommodate the (possible) vendor-side Service Commitments. The field is only editable if **Extend Vendor Contract** is activated at the same time. The second part of the page (*Customer*) behaves analogously to the first part. In the third part, in the **Item No.** field, the item corresponding to the new contract element must be specified. Further specifications can be made via **Quantity** and **Provision Start Date**. The AssistEdit at **Additional Service Commitments** allows to specify optional Service Commitments of the selected item.

The page behaves slightly differently depending on the way it is called. Basically, the values of the last call are saved (per user). They are used for presetting the next time the page is opened. When calling from a Customer Contract, the part *Customer* is predefined accordingly. The same applies analogously to the part *Vendor* for the call from a Vendor Contract. In both cases the contract extension is executed with a click on *OK*.

:::info Call from the menu
Besides the call from a Contract Card, the page can also be called directly from the menu. In this case, the values of the last call are also used as default values. However, there is no OK button available for the execution (due to system technical reasons). It is done by calling the action **Perform Extension**. This action is not visible when called from a Customer or Vendor Contract.
:::


## Invoice discounts
Mapping lump sum discounts for an entire contract is explained in more detail in [this](/docs/srb/working-with-contracts/contracts-services-mgmt.md#invoice-discounts) part of the DYCE documentation.


## Closed contract lines
If the Service End Date was entered for a contract line or it was [automatically updated](/docs/srb/setup/job-queue.md), this line can no longer be billed in the future. Therefore, ended lines will no longer be displayed in the default view of the contract card. However, via the **Closed Lines** fast tab, it is possible to continue to view these lines and thus to reconstruct at a later date what was once part of the contract. <br/>
The fields of a terminated line are not editable except for **Closed**. If the check mark in this field is removed, the line is moved back to the **Lines** fast tab and is thus editable again. Then, for example, the Service End Date can be adjusted. If no change is made, the line will be moved back to the **Closed Lines** fast tab the next time **Update Service Dates** is called. For more information on updating cancellation dates and deadlines and ending contract lines, please see [here](/docs/srb/working-with-contracts/service-commitment-cancellation.md).


## Merge Contract lines
In the course of time, it may happen that similar or identical Service Commitments are purchased from a supplier, e.g. as additional purchase of further users to an already existing license. In order to be able to invoice these Service Commitments together, it is possible to combine these Service Commitments using the action **Merge Contract Lines** in the line menu of the Vendor Contract.

Before calling the action, the contract lines to be merged must be selected. Contract lines can only be merged if the following criteria are met for all lines:
* No Billing Proposal lines may exist for any of the Service Commitments.
* The dimensions must be identical.
* The end user details must be identical.
* The items of the Service Objects must be identical.
* The **Customer References** of the Service Objects must be identical.
* Service Objects must not be tracked by serial number.
* The **Next Billing Date** must be identical.

However, the following must not be identical:
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

:::note Note
The function cannot be called for text lines.
:::

The **Select Vendor Contract line** page opens, in which the contract line must be selected to which the previously selected lines are to be combined. Then a new Service Object (as a copy of the Service Object of the selected contract line) including Service Commitments will be created. The total quantity is taken over. The Service Commitments to be combined are [terminated](#closed-contract-lines) and the new service is added to the contract. In the old Service Objects, the **Provision End Date** field is set, if possible.


## Create invoice per contract
Normally, contract invoices in **DYCE Subscription & Recurring Billing** are created via **[Recurring Billing](/docs/srb/recurring-billing.md)**. This feature is designed to generate Billing Proposals in batch. In addition, several options are available for creating the [Posting Documents](/docs/srb/posting-documents.md) (e.g., collective invoices, etc.). <br/>
Nevertheless, it may also be useful or necessary to create a contract invoice for the one contract that is currently being worked on - without first creating a Billing Proposal for it. For this use case the action **Create contract invoice** can be used. It is available both in the Vendor Contracts overview and in the Vendor Contract card. <br/>
In the query that opens, the key date for billing (**Billing Date**) and, optionally, the date up to which billing is to take place (**Billing To**) can be specified. In addition, the **Document Date** and the **Posting Date** can be specified for the [Posting Document](/docs/srb/posting-documents.md) to be created. If the **Open document** flag is set, the created document will be opened directly afterwards. Optionally, the created document can also be posted directly (**Post document**). Except for **Billing To**, all fields are predefined with the workdate (see page **My Settings**).

:::note Note
The creation of a contract invoice via the method described here is only useful in individual cases.
:::


## Linked information
Linked information can be called in the contract. In the menu (in the *Related* group) all invoices and credit memos can be accessed. In the menu group *Related / Vendor Contract* the **Contract Deferrals** can be viewed if the postings in the contract are deferred periodically.

Using the line menu *Contract Line* the **Billing Lines** and the **Archived Billing Lines** can be displayed. The information is opened for the selected contract line. The **Archived Billing Lines** can be opened in the posted invoice and credit memo as well.