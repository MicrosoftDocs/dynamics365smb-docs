---
title: Customer Contracts
hide_title: true
sidebar_label: Customer Contracts
slug: /srb/working-with-contracts/customer-contracts
---

# Customer Contracts
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

:::tip Tip
Alternatively, the page **Services Commitments without Customer Contracts** can also be called up via the role center part **Service Commitments without Contracts** or via the search (*Alt+Q*). In this case, the Service Commitments are not filtered and the Contract No. is not predefined.

In addition to the DYCE Role Center **Subscription & Recurring Billing**, the Role Center part is also available in the Role Centers **Company Hub**, **Business Manager**, **Service Manager**, **Sales Order Processor**, **Project Manager** and **Sales & Relationship Manager**.
:::

When the Service Commitments in a contract are transferred, **Contract lines** are created. These reflect the content of the Service Commitments. Any changes to the contract lines are automatically reflected in the Service Commitments. The **Quantity** field displays the quantity of the related Service Object.

:::tip Tip
If no deviating ship-to party is entered in the contract at the time the first service is assigned to a Customer Contract, the ship-to party stored in the **Service Object** is transferred to the contract. This facilitates the contract creation when mapping a partner model.
:::

:::info
Service Commitments are usually created automatically when the shipment is posted in the sales order. The prerequisite for this is a corresponding setup in the item used or in the Service Commitment Package, respectively.
:::

:::tip Tip
Editing contract lines instead of Service Commitments in the individual Service Objects makes work easier. Since the Service Commitments that are to be billed together usually also belong together in terms of content, it makes sense that they are all part of the same contract. This way they can be quickly viewed and edited via the contract.
:::

:::caution Text lines
Manual entry of contract lines is only possible for text lines. These are only used as an internal note for the contract processor and are not processed further. The basis for a billing is always a Service Commitment.
Only text lines that are marked as [Bundle](/docs/srb/bundles.md) will be included in the invoice.
:::


## Extend Contract
If a contract is to be extended by an additional component as simply as possible, the action **Extend Contract** (under *Process*) is available for this purpose. It is used to create a Service Object in *only one step* and to assign the related Service Commitments to a Customer and/or Vendor Contract. <br/>
The page that opens is divided into three sections. In the first part (*Vendor*), the **Vendor Contract No.** field can be used to select the Vendor Contract that is to accommodate the (possible) vendor-side Service Commitments. The field is only editable if **Extend Vendor Contract** is activated at the same time. The second part of the page (*Customer*) behaves analogously to the first part. In the third part, in the **Item No.** field, the item corresponding to the new contract element must be specified. Further specifications can be made via **Quantity** and **Provision Start Date**. The AssistEdit at **Additional Service Commitments** allows to specify optional Service Commitments of the selected item.

The page behaves slightly differently depending on the way it is called. Basically, the values of the last call are saved (per user). They are used for presetting the next time the page is opened. When calling from a Customer Contract, the part *Customer* is predefined accordingly. The same applies analogously to the part *Vendor* for the call from a Vendor Contract. In both cases the contract extension is executed with a click on *OK*.

:::info Call from the menu
Besides the call from a Contract Card, the page can also be called directly from the menu. In this case, the values of the last call are also used as default values. However, there is no OK button available for the execution (due to system technical reasons). It is done by calling the action **Perform Extension**. This action is not visible when called from a Customer or Vendor Contract.
:::


## Invoice discounts
Mapping lump sum discounts for an entire contract is explained in more detail in [this](/docs/srb/working-with-contracts/contracts-services-mgmt.md#invoice-discounts) part of the DYCE documentation.


## Closed Contract lines
If the Service End Date was entered for a contract line or it was [automatically updated](/docs/srb/setup/job-queue.md), this line can no longer be billed in the future. Therefore, ended lines will no longer be displayed in the default view of the contract card. However, via the **Closed Lines** fast tab, it is possible to continue to view these lines and thus to reconstruct at a later date what was once part of the contract. <br/>
The fields of a terminated line are not editable except for **Closed**. If the check mark in this field is removed, the line is moved back to the **Lines** fast tab and is thus editable again. Then, for example, the Service End Date can be adjusted. If no change is made, the line will be moved back to the **Closed Lines** fast tab the next time **Update Service Dates** is called. For more information on updating cancellation dates and deadlines and ending contract lines, please see [here](/docs/srb/working-with-contracts/service-commitment-cancellation.md).


## Merge Contract lines
In the course of time, it may happen that a customer purchases similar or identical Service Commitments, e.g. as a subsequent purchase of additional users to an already existing license. In order to be able to invoice these Service Commitments together, it is possible to combine these Service Commitments using the action **Merge Contract Lines** in the line menu of the Customer Contract.

Before calling the action, the contract lines to be merged must be selected. Contract lines can only be merged if the following criteria are met for all lines:
* No Billing Proposal lines may exist for any of the Service Commitments.
* The dimensions must be identical.
* The end user details must be identical.
* The items of the Service Objects must be identical.
* The **Customer References** of the Service Objects must be identical.
* Service Objects must not be tracked by serial number.
* The **Next Billing Date** must be identical (see also the option for [harmonization of Contract elements](#harmonized-billing)).

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

:::note Note
The function cannot be called for text lines.
:::

The **Select Customer Contract line** page opens, in which the contract line must be selected to which the previously selected lines are to be combined. Afterwards a new Service Object (as a copy of the Service Object of the selected contract line) including Service Commitments will be created. The total quantity is taken over. The Service Commitments to be combined are [terminated](#closed-contract-lines) and the new service is added to the contract. In the old Service Objects, the **Provision End Date** field is set, if possible.


## Create invoice per Contract
Normally, contract invoices in **DYCE Subscription & Recurring Billing** are created via **[Recurring Billing](/docs/srb/recurring-billing.md)**. This feature is designed to generate Billing Proposals in batch. In addition, several options are available for creating the [Posting Documents](/docs/srb/posting-documents.md) (e.g., collective invoices, etc.). <br/>
Nevertheless, it may also be useful or necessary to create a contract invoice for the one contract that is currently being worked on - without first creating a Billing Proposal for it. For this use case the action **Create contract invoice** can be used. It is available both in the Customer Contracts overview and in the Customer Contract card. <br/>
In the query that opens, the key date for billing (**Billing Date**) and, optionally, the date up to which billing is to take place (**Billing To**) can be specified. In addition, the **Document Date** and the **Posting Date** can be specified for the [Posting Document](/docs/srb/posting-documents.md) to be created. If the **Open document** flag is set, the created document will be opened directly afterwards. Optionally, the created document can also be posted directly (**Post document**). Except for **Billing To**, all fields are predefined with the workdate (see page **My Settings**).

:::note Note
The creation of a contract invoice via the method described here is only useful in individual cases.
:::


## Details for Contract invoices
In the **Invoice Details** fast tab, the **Detail Overview** field per contract controls whether billing details are automatically output for each invoice. It can be differentiated whether the details should be output with or without prices (Complete / Without prices). In addition, this field serves as a criterion with regard to the creation of collective invoices, as it must have the same value for all contracts to be combined. <br/>
The fields **Contractor Name in collective Invoice** and **Recipient Name in collective Invoice** determine whether and if so, which customer names are transferred to collective invoices and output there. When creating a new Customer Contract, the **Origin Name for collective Sales Invoice** field from [setup](/docs/srb/setup/general.md#invoice-details) is interpreted. However, the setting can be made per contract. Decisive for the creation of the collective invoice are the fields of the respective Customer Contract.


## Harmonized Billing
If several Service Commitments with a longer Billing Rhythm (e.g. 12 months) are purchased by the customer at different times and invoiced via the same contract, the invoicing date of the services is usually different. If the customer wishes to have aligned billing on a *billing date*, the **Harmonized Billing Customer Contracts** indicator from the [Contract Type](/docs/srb/setup/contract-types.md) can be used for this purpose. <br/>
If this flag is set for the Contract Type of the Customer Contract, the **Billing Base Date** and **Default Billing Rhythm** fields (in the *Harmonized Billing* group in the **Shipping and Billing** fast tab) are editable. When the first Service Commitment is added to the contract, the fields are predefined based on that data. However, they can be changed manually. <br/>
When creating the Billing Proposal lines, a check is made for each Service Commitment to see if it is connected to a contract being billed in a harmonized manner. If yes, the *harmonization fields* will be considered accordingly. <br/>
The *harmonization fields* will be updated when adding, deleting and modifying a Service Commitments, if applicable.

:::tip Tip
If Service Commitments with a longer Billing Rhythm (e.g. 12 months) are added to a contract whose **Next Billing Date** is during the year, and these Service Commitments (and all those to come) should generally only be billed by the end of the year, the **Billing Base Date** can be reset to January 1st of the year.
:::


### Special case: Deletion of the first Billing Proposal
There is a well-known special case in which manual intervention by the user is required: <br/>
A contract is to be billed harmonized (e.g. per calendar year). Therefore, the **Billing Base Date** in the Contract header (in the *Shipping and Billing* fast tab) is set to *January 1st* of the current year. Service Commitments will be added during the course of the first year. If a Billing Proposal is now created within and for the first year *and subsequently deleted*, the **Billing Base Date** will be overwritten with the *oldest* **Next Billing Date** from the Contract lines (Service Commitments). This cannot be avoided due to the automatic updating of Service Commitments and only occurs as long as the contract has never been billed. After the first billing, the behavior then no longer occurs. In this case, the **Billing Base Date** must be manually reset to *January 1st* of the current year.


## Linked information
Linked information can be called from the contract. In the menu (in the *Related* group) all invoices and credit memos can be accessed. In the menu group *Related / Customer Contract* the **Contract Deferrals** can be viewed if the postings in the contract are deferred periodically.

Using the line menu *Contract Line* the **Billing Lines** and the **Archived Billing Lines** can be displayed. The information is opened for the selected contract line. The **Archived Billing Lines** can be opened in the posted invoice and credit memo as well.