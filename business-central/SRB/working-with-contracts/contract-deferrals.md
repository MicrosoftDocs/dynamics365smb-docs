---
title: Contract deferrals
description: You can use contract deferrals in subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
---

# Contract Deferrals
The system provides a control option that when an invoice is prebilled, the customer-side revenues and vendor-side costs from future months are not yet posted to revenue or expense in the month the invoice is created. In this case, the net invoice amount is not posted to a revenue or expense account, but to an accrual account. This deferrals will later be released to income on a monthly basis.


## Prerequisite and setup
When posting a contract invoice, *Contract Deferrals* are automatically created if the **Without Contract Deferrals** indicator in the Contract Header is set to *No*. Contract Deferrals are used for Deferred Income (Customer Contracts) or Prepaid Expenses (Vendor Contracts).


## Contract Deferrals Customer Contract
Contract Deferrals from customer contracts are used for deferring revenues in sales invoices. <br/>
The G/L accounts that are posted to are those that have been defined in the <a href="https://learn.microsoft.com/en-us/dynamics365/business-central/finance-posting-groups" title="Setting up Posting Groups">Posting Matrix Setup</a> for each combination of Gen. Bus. Posting Group and Gen. Prod. Posting Group possible in a business transaction.
In the Customer Contract, this is the combination of the Customer's Gen. Bus. Posting Group in the Contact Header and the Gen. Prod. Posting Group of the [Invoicing Item](/docs/srb/masterdata/items.md). <br/>
By default, the account used per combination is the one stored in the **Customer Contract Deferral Account** field in the **General Posting Setup**. However, if the **Without Contract Deferrals** indicator is set to *Yes* in the Customer Contract Header, the invoice amount is immediately posted as revenue to the account defined in the **Customer Contract Account** field. Contract Deferrals will not be created in this case.


### Calling Contract Deferrals from Customer Contracts
Customer Contract Deferrals can be accessed in the Customer Contract Card using the **Customer Contract Deferrals** action. The page that opens displays the following information in detail:
* The **Posting Date** indicates per accrual for when it was created. For the first deferral (per document) the posting date of the document is used, for all further deferrals the first day of the respective month is used.
* The **Contract No.** indicates the number of the contract for which the deferrals were created.
* The **Document Type** indicates the Document Type used to create the deferrals.
* The **Document No.** indicates the Document No. with which the deferral was generated.
* The **Service Object Description** field contains the description of the associated Service Object that was Invoiced via the document line.
* The **Service Commitment Description** field contains the description of the associated Service Commitment that was invoiced via the document line.
* The **Bill-to Cust.-No.** is the number of the customer (invoice recipient) for which the deferrals were generated.
* The **Customer No.** is the number of the Customer (Contractor) for whom the deferrals were generated.
* The **Discount Amount** field contains the (pro-rata) discount amount of the deferrals.
* The basis for the deferrals for a document is represented in the **Deferral Base Amount** field.
* The **Discount %** field contains the percentage rate associated with the **Discount Amount**.
* The amount per deferrals is displayed in the **Amount** field.
* The **Released** field indicates whether the deferral has already been released.
* The **Contract Type** field displays the contract type of the associated contract.
* The **User ID** field displays the ID of the user who posted the document and thus created the deferrals.
* The **Document Posting Date** field contains the Posting Date of the document that was used to create the accrual.
* The **Release Posting Date** field contains the Posting Date on which the accrual was released.
* **Number of Days** displays the days belonging to each deferral.
* **General Ledger Entry No.** contains the number of the G/L item with which the deferral was released.
* The **Entry No.** is assigned when the deferrals are created from the specified number series.

:::tip Preview Posting
The deferrals to be created can also already be checked in the unposted contract invoices via the **Preview Posting**.
:::


## Contract Deferrals Vendor Contracts
Contract Deferrals from vendor contracts are used for deferring cost in purchase invoices. In the case of post-invoicing (i.e. the retroactive calculation of Service Commitments), on the other hand, postings are always made immediately with an immediate effect on costs. Since the period is already in the past, Contract Deferrals are not needed here and are not created. <br/>
Analogous to the Customer Contract, the G/L accounts to be posted to are determined using the <a href="https://learn.microsoft.com/en-us/dynamics365/business-central/finance-posting-groups" title="Posting Groups Setup">Posting General Posting Setup</a> for the respective business transaction. In the Vendor Contract, this is the combination of the Vendor's Gen. Bus. Posting Group in the Contract Header and the Gen. Prod. Posting Group of the [Invoicing Item](/docs/srb/masterdata/items.md).
By default, the account used is the one stored in the **Vendor Contract Deferral Account** field in the **General Posting Setup**. However, if the **Without Contract Deferrals** indicator is set to *Yes* in the Vendor Contract Header, the invoice amount is immediately posted as a cost to the account stored in the **Vendor Contract Account** field. Contract Deferrals will not be created in this case.


### Calling Contract Deferrals from Vendor Contracts
Vendor Contract Deferrals can be accessed in the Vendor Contract Card using the **Vendor Contract Deferrals** action. The page that opens is the same as the one for [Customer Contract Deferrals](#calling-contract-deferrals-from-customer-contracts).


## Methodology for creating Contract Deferrals
When posting the contract invoice, Contract Deferrals are created using the following schema:
* The total amount (**Deferral Base Amount** field) is divided among the number of deferrals to be created.
* When the *first* deferral is created for the billing line, a check is made to see if the start of the billing period is the *first* day of a month. If not, the **Amount** is prorated to the day (using **Deferral Base Amount**) based on the *first* month.
* When the *last* deferral is created for the billing line, a check is made to see if the end of the billing period is the *last* day of a month. If not, the **Amount** is prorated to the day (using **Deferral Base Amount**) based on the *last* month.
* Line discounts are not included in the **Deferral Base Amount**.
* Rounding differences are added to the *last* deferral created for the invoice line.


## Release deferrals
The batch report **Contract Deferrals Release** is used to release invoice deferrals. This report runs through all contract deferrals (customer and vendor), filters using **Posting Until Date** from the report request page to the **Posting Date** and **Document Posting Date** fields, and reposts the items thus found from the accrual account to the cost or revenue account. The release takes place for debit-side and credit-side contract accruals at the same time. The **Posting Date** field from the report request page is used as the *Posting Date* for the closure. At the same time, the **Released** field in the Contract Deferrals is set to *Yes*. <br/>
It is therefore recommended to trigger the release of Contract Deferrals on a monthly basis (e.g. at the end of the month). In the future, it will also be possible to perform the release of Contract Deferrals automatically via the [Job Queue](/docs/srb/setup/job-queue.md).

When posting the release, the Source Code will be used, which is stored in the **Contract Deferrals Release** field in the **Source Code Setup** page.

:::caution Note
* If deferrals have been created by a contract invoice, they will automatically be fully released on the **Posting Date of Credit Memo** when the contract invoice is credited.

* Contract deferrals should not be released to **future periods**.

* Credit memos should not be posted to **past (supposedly closed) periods**. The release and correction of the contract deferrals occur on the document date of the credit memo. This could distort the reporting and the advance VAT return already created. If the credit memo was posted in past periods, these two points, among others, must be corrected in coordination with the departments (internal financial accounting/tax advisor).
:::


## Dimensions and updates
If a dimension is updated on a contract line for which deferrals exist, it makes sense to update the related deferrals as well, so that subsequent resolution postings use the same dimensions. For this purpose, the action **Update Dimensions in Deferrals** is available in the respective Customer or Vendor Contract card. It updates the dimensions in all Contract Deferrals not yet released for the respective contract. If there are no deferrals for a contract, the action is not available. After the action has been run, the user receives a corresponding message.


## Output of deferrals
For the control of the deferrals and for the submit for auditors it is possible to export the deferrals to Excel or to print them. For this purpose, the calls **Customers Contract Deferrals Analysis** and **Vendors Contract Deferrals Analysis** (*Alt+Q*) can be used.


## Examples
### Example 1: 1 year, full months
* Base amount for deferrals: 1,200.00
* Start date: 01.01.2021
* End date: 12/31/2021
* Basis monthly amount: 1,200.00
* Number of full months: 12
* Monthly amount: 100,00

Posting Date|Number of Days|Deferral Base Amount|Amount
|--:|--:|--:|--:
|01.01.2021|31|1.200,00|100,00
|01.02.2021|28|1.200,00|100,00
|01.03.2021|31|1.200,00|100,00
|01.04.2021|30|1.200,00|100,00
|01.05.2021|31|1.200,00|100,00
|01.06.2021|30|1.200,00|100,00
|01.07.2021|31|1.200,00|100,00
|01.08.2021|31|1.200,00|100,00
|01.09.2021|30|1.200,00|100,00
|01.10.2021|31|1.200,00|100,00
|01.11.2021|30|1.200,00|100,00
|01.12.2021|31|1.200,00|100,00


### Example 2: 1 year with subperiods
* Basis amount for deferrals: 1,200.00
* Start date: 01/15/2021
* End date: 01/14/2022
* Basis monthly amount: 1,098.08
* Number of full months: 11
* Monthly amount: 99.83

Posting Date|Number of Days|Deferral Base Amount|Amount
|--:|--:|--:|--:
|15.01.2021|17|1.200,00|55,89
|01.02.2021|28|1.200,00|99,83
|01.03.2021|31|1.200,00|99,83
|01.04.2021|30|1.200,00|99,83
|01.05.2021|31|1.200,00|99,83
|01.06.2021|30|1.200,00|99,83
|01.07.2021|31|1.200,00|99,83
|01.08.2021|31|1.200,00|99,83
|01.09.2021|30|1.200,00|99,83
|01.10.2021|31|1.200,00|99,83
|01.11.2021|30|1.200,00|99,83
|01.12.2021|31|1.200,00|99,83
|01.01.2022|14|1.200,00|45,98


### Example 3: less than 1 year with subperiods
* Basis amount for deferrals: 1,022.47
* Start date: 01/15/2021
* End date: 21.11.2021
* Basis monthly amount: 897.54
* Number of full months: 9
* Monthly amount: 99.73

Posting Date|Number of Days|Deferral Base Amount|Amount
|--:|--:|--:|--:
|15.01.2021|17|1.022,47|55,89
|01.02.2021|28|1.022,47|99,73
|01.03.2021|31|1.022,47|99,73
|01.04.2021|30|1.022,47|99,73
|01.05.2021|31|1.022,47|99,73
|01.06.2021|30|1.022,47|99,73
|01.07.2021|31|1.022,47|99,73
|01.08.2021|31|1.022,47|99,73
|01.09.2021|30|1.022,47|99,73
|01.10.2021|31|1.022,47|99,73
|01.11.2021|21|1.022,47|69,01