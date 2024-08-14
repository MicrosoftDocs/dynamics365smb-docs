---
title: Contrat Types
hide_title: true
sidebar_label: Contract Types
slug: /srb/setup/contract-types
---

# Contract Types
The **Contract Types** page defines which different types of contracts exist. They are used to manage and organize Customer and Vendor Contracts and can be used as filters for this purpose - e.g. also for billing. Examples can be maintenance or support contracts, but also insurances or other types of recurring incoming and outgoing invoices.

For each Contract Type, an appropriate description should be entered in addition to a unique code. The description is further used as an info line in the posting documents for the contracts.

:::info Translations
The action of the same name can be used to define translations for the Contract Type, specifying the corresponding language code. These will be taken into account when creating the [contract invoices](/docs/srb/posting-documents.md).
:::


## Harmonized Billing
The **Harmonized Billing Customer Contracts** indicator controls whether the contract elements of related Customer Contracts are billed on a common due date. If it is set, the corresponding fields in the *Harmonized Billing* group in the **Shipping and Billing** fast tab of the Customer Contracts card are editable. If the field is reset, the fields on the affected Customer Contracts will also be reset and disabled upon request. For more details on how this works, please refer to the [Harmonization of Contract elements](/docs/srb/working-with-contracts/customer-contracts.md#harmonized-billing) part.


## Default Without Contract Deferrals
This field can be used to predefine the default value for the corresponding field in the Contract Header. This simplifies contract creation and reduces handling errors. When the Contract Type is selected, the value is copied to the field in the contract. The value can be changed manually if necessary.