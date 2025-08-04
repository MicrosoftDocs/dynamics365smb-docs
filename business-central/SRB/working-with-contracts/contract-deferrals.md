---
title: Contract deferrals
description: You can use contract deferrals in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
---

# Contract deferrals

In subscription billing, managing the timing of revenue and expense recognition is important. [!INCLUDE prod_short] offers contract deferrals, which allow you to defer customer-side revenues and vendor-side costs to future periods. These amounts aren't posted to revenue or expense accounts at the time of invoicing but are instead posted to accrual accounts and released to income on a monthly basis.

## Prerequisites and setup

When posting a contract invoice, contract deferrals are automatically created if the **Without Contract Deferrals** toggle is off on the contract. Contract deferrals are used for deferred income (customer contracts) or prepaid expenses (vendor contracts).

## Contract deferrals customer contract

Use contract deferrals from customer contracts to defer revenues in sales invoices.

The G/L accounts that are posted to are those that have been defined in posting groups for each combination of general business posting group and general product posting group possible in a business transaction. To learn more, go to [Set up posting groups](../../finance-posting-groups.md). In the customer contract, this is the combination of the customer's general business posting group in the contract header and the general product posting group of the items. To learn more, go to [Service Commitments at Items](../masterdata/items.md).

By default, the account used per combination is the one stored in the **Customer Contract Deferral Account** field in the **General Posting Setup**. However, if the **Without Contract Deferrals** toggle is on on the **Customer Contract** page, the invoice amount is immediately posted as revenue to the account defined in the **Customer Contract Account** field. In this case, contract deferrals aren't created.

### Opening contract deferrals from customer contracts

You can access customer contract deferrals from the **Customer Contract** page using the **Customer Contract Deferrals** action. The **Customer Contract Deferrals** page displays the following details:

* The **Posting Date** indicates per accrual for when it was created. For the first deferral (per document) the posting date of the document is used, for all further deferrals the first day of the respective month is used.
* The **Contract No.** indicates the number of the contract for which the deferrals were created.
* The **Document Type** indicates the document type used to create the deferrals.
* The **Document No.** indicates the document number with which the deferral was generated.
* The **Service Object Description** field contains the description of the associated service object that was invoiced via the document line.
* The **Service Commitment Description** field contains the description of the associated service commitment that was invoiced via the document line.
* The **Bill-to Cust.-No.** is the number of the customer (invoice recipient) for which the deferrals were generated.
* The **Customer No.** is the number of the customer (Contractor) for whom the deferrals were generated.
* The **Discount Amount** field contains the (pro-rata) discount amount of the deferrals.
* The basis for the deferrals for a document is represented in the **Deferral Base Amount** field.
* The **Discount %** field contains the percentage rate associated with the **Discount Amount**.
* The amount per deferrals is displayed in the **Amount** field.
* The **Released** field indicates whether the deferral has already been released.
* The **Contract Type** field displays the contract type of the associated contract.
* The **User ID** field displays the ID of the user who posted the document and thus created the deferrals.
* The **Document Posting Date** field contains the posting date of the document that was used to create the accrual.
* The **Release Posting Date** field contains the posting date on which the accrual was released.
* **Number of Days** displays the days belonging to each deferral.
* **General Ledger Entry No.** contains the number of the G/L item with which the deferral was released.
* The **Entry No.** is assigned when the deferrals are created from the specified number series.

> [!TIP]
> The deferrals to create can also already be checked in the unposted contract invoices via the **Preview Posting**.

## Contract deferrals vendor contracts

Contract deferrals from vendor contracts defer cost in purchase invoices. In the case of post-invoicing (for example, the retroactive calculation of service commitments), on the other hand, postings are always made immediately with an immediate effect on costs. Since the period is already in the past, contract deferrals are not needed here and are not created.

Similar to the customer contract, the G/L accounts to post to are determined using posting groups for the respective business transaction. In the vendor contract, this is the combination of the vendor's general business posting group in the Contract Header and the general product posting group of the item.

By default, the account used is the **Vendor Contract Deferral Account** field in the **General Posting Setup**. However, if the **Without Contract Deferrals** toggle is on on the **Vendor Contract** page, the invoice amount is immediately posted as a cost to the account in the **Vendor Contract Account** field. In this case, contract deferrals aren't created.

### Calling contract deferrals from vendor contracts

You can access vendor contract deferrals on the **Vendor Contract Card** page using the **Vendor Contract Deferrals** action. The **Vendor Contract Deferrals** page is the same as the **Customer contract deferrals** page.

## Methodology for creating contract deferrals

When posting the contract invoice, contract deferrals are created using the following schema:

* The total amount in the **Deferral Base Amount** field is divided among the number of deferrals to be created.
* When the first deferral is created for the billing line, a check is made to see whether the start of the billing period is the first day of a month. If not, the **Amount** is prorated to the day (using **Deferral Base Amount**) based on the first month.
* When the last deferral is created for the billing line, a check is made to see whether the end of the billing period is the last day of a month. If not, the **Amount** is prorated to the day using the **Deferral Base Amount** based on the last month.
* Line discounts are not included in the **Deferral Base Amount**.
* Rounding differences are added to the last deferral created for the invoice line.

## Release deferrals

The **Contract Deferrals Release** batch report is used to release invoice deferrals. This report runs through all contract deferrals (customer and vendor), filters using **Posting Until Date** from the report request page to the **Posting Date** and **Document Posting Date** fields, and reposts the items thus found from the accrual account to the cost or revenue account. The release takes place for debit-side and credit-side contract accruals at the same time. The **Posting Date** field from the report request page is used as the posting date for the closure. At the same time, the status in **Released** field in the contract deferrals is set to **Yes**.
We recommend that you run the release of contract deferrals on a monthly basis (for example, at the end of the month).

When posting the release, the source code is used, which is stored in the **Contract Deferrals Release** field in the **Source Code Setup** page.

> [!NOTE]
> * If deferrals were created by a contract invoice, they are automatically fully released on the **Posting Date of Credit Memo** when the contract invoice is credited.
> * Contract deferrals should not be released to **future periods**.
> * Credit memos should not be posted to **past (supposedly closed) periods**. The release and correction of the contract deferrals occur on the document date of the credit memo. This could distort the reporting and the advance VAT return already created. If the credit memo was posted in past periods, these two points, among others, must be corrected in coordination with the departments (internal financial accounting/tax advisor).

## Dimensions and updates

If a dimension is updated on a contract line for which deferrals exist, it makes sense to update the related deferrals as well, so that subsequent resolution postings use the same dimensions. For this purpose, the action **Update Dimensions in Deferrals** is available in the respective customer or vendor contract. It updates the dimensions in all contract deferrals not yet released for the respective contract. If there are no deferrals for a contract, the action is not available. After the action has been run, the user receives a corresponding message.

## Output of deferrals

To control deferrals and for submissions to auditors, you can export the deferrals to Excel or print them. Use the **Customers Contract Deferrals Analysis** and **Vendors Contract Deferrals Analysis** pages.

## Examples

### Example 1: 1 year, full months

* **Base amount for deferrals:** 1,200.00
* **Start date:** 01.01.2021
* **End date:** 12/31/2021
* **Basis monthly amount:** 1,200.00
* **Number of full months:** 12
* **Monthly amount:** 100,00

|Posting Date|Number of Days|Deferral Base Amount|Amount|
|--|--|--|--|
|01/01/2021|31|1,200.00|100.00|
|01/02/2021|28|1,200.00|100.00|
|01/03/2021|31|1,200.00|100.00|
|01/04/2021|30|1,200.00|100.00|
|01/05/2021|31|1,200.00|100.00|
|01/06/2021|30|1,200.00|100.00|
|01/07/2021|31|1,200.00|100.00|
|01/08/2021|31|1,200.00|100.00|
|01/09/2021|30|1,200.00|100.00|
|01/10/2021|31|1,200.00|100.00|
|01/11/2021|30|1,200.00|100.00|
|01/12/2021|31|1,200.00|100.00|

### Example 2: 1 year with subperiods

* **Basis amount for deferrals:** 1,200.00
* **Start date:** 01/15/2021
* **End date:** 01/14/2022
* **Basis monthly amount:** 1,098.08
* **Number of full months:** 11
* **Monthly amount:** 99.83

|Posting Date|Number of Days|Deferral Base Amount|Amount|
|--|--|--|--|
|15/01/2021|17|1,200.00|55.89|
|01/02/2021|28|1,200.00|99.83|
|01/03/2021|31|1,200.00|99.83|
|01/04/2021|30|1,200.00|99.83|
|01/05/2021|31|1,200.00|99.83|
|01/06/2021|30|1,200.00|99.83|
|01/07/2021|31|1,200.00|99.83|
|01/08/2021|31|1,200.00|99.83|
|01/09/2021|30|1,200.00|99.83|
|01/10/2021|31|1,200.00|99.83|
|01/11/2021|30|1,200.00|99.83|
|01/12/2021|31|1,200.00|99.83|
|01/01/2022|14|1,200.00|45.98|

### Example 3: less than 1 year with subperiods

* **Basis amount for deferrals:** 1,022.47
* **Start date:** 01/15/2021
* **End date:** 21.11.2021
* **Basis monthly amount:** 897.54
* **Number of full months:** 9
* **Monthly amount:** 99.73

|Posting Date|Number of Days|Deferral Base Amount|Amount|
|--|--|--|--|
|15/01/2021|17|1,022.47|55.89|
|01/02/2021|28|1,022.47|99.73|
|01/03/2021|31|1,022.47|99.73|
|01/04/2021|30|1,022.47|99.73|
|01/05/2021|31|1,022.47|99.73|
|01/06/2021|30|1,022.47|99.73|
|01/07/2021|31|1,022.47|99.73|
|01/08/2021|31|1,022.47|99.73|
|01/09/2021|30|1,022.47|99.73|
|01/10/2021|31|1,022.47|99.73|
|01/11/2021|21|1,022.47|69.01|

## Related information

[Contract renewal](contract-renewal.md)
