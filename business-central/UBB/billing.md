---
title: Billing 
description: You can use billing in usage based billing.
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

# Billing

In principle, all usage data per contract line or Service Commitments are added together when billing. They form the basis for billing. Contract lines whose Service Commitments are marked as **Usage Based Billing**=*Yes*, but for which no usage data is available, are accordingly not taken into account when invoicing.


## Generate Purchase invoices
After the usage data has been imported and processed via the **Usage Data Imports** page, the invoicing towards the supplier can be started in the same page. The **Create Purchase Invoices** action (via *Process*) will create one or more Purchase invoices for the supplier based on the usage data from the current import. Whether this results in one or more Purchase invoices is controlled by the selection in the **Vendor Invoice per** field at the Supplier. When *Import* is selected, only one document (possibly a collective invoice for several Vendor Contracts) is created. If *End Customer* option is selected, one Vendor Contract invoice will be created for each related Customer Contract. Thereby - analogous to the [creation of a contract invoice](/docs/srb/working-with-contracts/vendor-contracts.md#create-invoice-per-contract) - first billing lines are created in the background, for which the [posting document](/docs/srb/posting-documents.md) is created immediately afterwards. When this document is deleted, the billing lines are also deleted immediately.

:::info Note
The Vendor Contract invoice(s) should exactly match the usage data previously imported. For this reason, only those contract lines for which usage data is available in the import will be considered.
:::

The unposted Vendor Contract invoice(s) generated in the transaction can then be accessed and further processed or posted via the **Vendor Contract Invoices** action (via *Related / Usage Based Billing*). In addition, the invoice can also be viewed at the respective Vendor Contract and **Usage Data Billing** (via the **Document Type** and **Document No.** fields).


## Generate Sales invoices
Customer usage data can also be billed to the Customer after processing via the **Usage Data Imports** page. The **Create Sales Invoices** action (via *Process*) creates one Contract invoice per Customer Contract based on the usage data of the current import. Thereby - analogous to the [creation of a contract invoice](/docs/srb/working-with-contracts/customer-contracts.md#create-invoice-per-contract) - first billing lines are created in the background, for which the [posting document](/docs/srb/posting-documents.md) is created immediately afterwards. When this document is deleted, the billing lines are also deleted immediately.

:::info Pause Billing
If no usage data is available for a billing period, this period will not be taken into account during billing. The next time usage data is billed, this pause will be skipped.
:::

The unposted Customer Contract invoice(s) generated during the process can subsequently be accessed and further processed or posted via the **Customer Contract Invoices** action (via *Related / Usage Based Billing*). In addition, the invoice can also be viewed at the respective Customer Contract and **Usage Data Billing** (via the **Document Type** and **Document No.** fields).

:::caution Note
When creating Customer Contract invoices, only those contract lines are considered for which usage data is available in the import.
:::


## Recurring Billing
As an alternative to the above way of creating contract invoices via the **Usage Data Imports** page, the two previous ways (via **DYCE Subscription & Recurring Billing**) are also available. On the one hand, a separate invoice can be created per contract using the **Create Contract Invoice** action (via *Process* in the respective Contract cards). On the other hand the [Recurring Billing](/docs/srb/recurring-billing.md) (incl. all known functions like filter e.g. on [Contract Types](/docs/srb/setup/contract-types.md) and [Billing Templates](/srb/recurring-billing.md#billing-templates)) can be used. <br/>
In addition, usage data for one particular billing line can be accessed or displayed using the **Usage Data** action (via *Navigate*).

:::info Credit Memos
It can happen that due to usage data in the billing period for a contract a Credit Memo has to be created instead of an invoice. In this case, the system recognizes which Document Type (invoice or credit memo) must be used based on the total amount per document.
:::