---
title: Subscription contract deferrals
description: You can use contract deferrals in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 8059, 8079, 8071, 314,
ms.date: 07/11/2025
ms.service: dynamics-365-business-central
---

# Subscription contract deferrals

In subscription billing, managing the timing of revenue and expense recognition is important. [!INCLUDE [prod_short](../../includes/prod_short.md)] offers contract deferrals that let you defer customer-side revenues and vendor-side costs to future periods. These amounts don't post to revenue or expense accounts when you post the invoice. Instead, they post to accrual accounts and release to income on a monthly basis.

## Prerequisites and setup

When you post a contract invoice, contract deferrals are automatically created if the **Create Contract Deferrals** toggle is activated on the contract. Use contract deferrals to defer income for customer subscription contracts or prepaid expenses for vendor subscription contracts.

## Deferrals for customer subscription contracts

To defer revenues in sales invoices, use contract deferrals from customer subscription contracts.

You define the G/L accounts to post to in posting groups for each combination of general business posting group and general product posting group possible in a business transaction. To learn more, go to [Set up posting groups](../../finance-posting-groups.md). In the customer subscription contract, this setup combines:

* The customer's general business posting group in the contract header.
* The general product posting group of the items.

To learn more, go to [Subscription lines for items](../masterdata/items.md).

By default, the account used per combination is stored in the **Customer Subscription Contract Deferral** field on the **General Posting Setup** page. However, if the **Create Contract Deferrals** toggle is deactivated on the customer subscription contract, the invoice amount is immediately posted as revenue to the account defined in the **Customer Subscription Contract Account** field. In this case, contract deferrals aren't created.

### Opening contract deferrals from customer subscription contracts

You can access customer subscription contract deferrals from the **Customer Subscription Contract** page using the **Customer Subscription Contract Deferrals** action. The **Customer Subscription Contract Deferrals** page displays the following details:

* The **Posting Date** indicates per accrual for when it was created. For the first deferral (per document) the posting date of the document is used, for all further deferrals the first day of the respective month is used.
* The **Contract No.** indicates the number of the contract for which the deferrals were created.
* The **Document Type** indicates the document type used to create the deferrals.
* The **Document No.** indicates the document number with which the deferral was generated.
* The **Subscription Description** field contains the description of the associated subscription that was invoiced via the document line.
* The **Subscription Line Description** field contains the description of the associated subscription line that was invoiced via the document line.
* The **Bill-to Customer No.** is the number of the customer (invoice recipient) for which the deferrals were generated.
* The **Customer No.** is the number of the customer (Contractor) for whom the deferrals were generated.
* The **Discount Amount** field contains the (pro-rata) discount amount of the deferrals.
* The basis for the deferrals for a document is represented in the **Deferral Base Amount** field.
* The **Discount %** field contains the percentage rate associated with the **Discount Amount**.
* The amount per deferrals is displayed in the **Amount** field.
* The **Released** field indicates whether the deferral was already released.
* The **Contract Type** field displays the contract type of the associated contract.
* The **User ID** field displays the ID of the user who posted the document and thus created the deferrals.
* The **Document Posting Date** field contains the posting date of the document that was used to create the accrual.
* The **Release Posting Date** field contains the posting date on which the accrual was released.
* **Number of Days** displays the days belonging to each deferral.
* **General Ledger Entry No.** contains the number of the G/L item with which the deferral was released.
* The **Entry No.** is assigned when the deferrals are created from the specified number series.

> [!TIP]
> The deferrals to create can also already be checked in the unposted contract invoices via **Preview Posting**.

## Deferrals vendor subscription contracts

Contract deferrals from vendor subscription contracts defer cost in purchase invoices. For post-invoicing (for example, the retroactive calculation of subscription lines), posting happens immediately with an immediate effect on costs. Because the period is already in the past, contract deferrals aren't needed so they aren't created.

Similar to the customer subscription contract, the G/L accounts to post to are determined using posting groups for the business transaction. In the vendor contract, this setup combines:

* The vendor's general business posting group.
* The item's general product posting group.

By default, the account used is the **Vendor Subscription Contract Deferral** field on the **General Posting Setup** page. However, if the **Create Contract Deferrals** toggle is activated on the vendor subscription contract, the invoice amount is immediately posted as a cost to the account in the **Vendor Subscription Contract Account** field. In this case, contract deferrals aren't created.

### Opening subscription contract deferrals from vendor subscription contracts

You can access vendor subscription contract deferrals on the **Vendor Subscription Contract** page using the **Vendor Subscription Contract Deferrals** action. The **Vendor Subscription Contract Deferrals** page is the same as the **Customer Subscription Contract Deferrals** page. To learn more, go to [Opening contract deferrals from customer subscription contracts](#opening-contract-deferrals-from-customer-subscription-contracts).

## Methodology for creating subscription contract deferrals

When you post the contract invoice, contract deferrals are created using the following schema:

* The total amount in the **Deferral Base Amount** field is divided among the number of deferrals to be created.
* When the first deferral is created for the billing line, a check is made to see whether the start of the billing period is the first day of a month. If not, the **Amount** is prorated to the day (using **Deferral Base Amount**) based on the first month.
* When the last deferral is created for the billing line, a check is made to see whether the end of the billing period is the last day of a month. If not, the **Amount** is prorated to the day using the **Deferral Base Amount** based on the last month.
* Line discounts aren't included in the **Deferral Base Amount**.
* Rounding differences are added to the last deferral created for the invoice line.

## Release deferrals

Use the **Subscription Contract Deferrals Release** report to release invoice deferrals. This report: 

* Runs through all customer and vendor contract deferrals, and filters using **Posting Until Date** from the report request page to the **Posting Date** and **Document Posting Date** fields
* Reposts the items found from the accrual account to the cost or revenue account.

The release takes place for debit-side and credit-side contract deferrals at the same time. The **Posting Date** field from the report request page is used as the posting date for the closure. At the same time, the status in **Released** field in the contract deferrals is set to **Yes**.

> [!TIP]
> You can set up report 8051, **Subscription Contract Deferrals Release**, as an entry in the job queue. If you do that, the work date will be used for the two fields, **Posting Date** and **Post Until Date**.

It's recommend to you run the release of contract deferrals on a monthly basis (for example, at the end of the month).

When you post the release, the source code is used. The source code is in the **Subscription Contract Deferrals Release** field in the **Source Code Setup** page.

> [!NOTE]
> * If deferrals were created by a contract invoice, they're automatically released fully on the **Posting Date of Credit Memo** when the contract invoice is credited.
> * Contract deferrals shouldn't be released to future periods.
> * Credit memos shouldn't post to past (supposedly closed) periods. The release and correction of the contract deferrals happen on the document date of the credit memo. This mismatch could distort the reporting and the advance VAT return already created. If the credit memo was posted in a past period, these two points, among others, must be corrected in coordination with the departments, such as internal financial accounting or your tax advisor.

## Dimensions and updates

If you change a dimension on a contract line for which deferrals exist, also update the related deferrals so that resolution postings use the same dimensions. Use the **Update Dimensions in Deferrals** action on the customer and vendor contract. The action updates the dimensions in all contract deferrals not yet released for the respective contract. If there are no deferrals for a contract, the action isn't available.

## Output of deferrals

To control deferrals and submissions to auditors, you can export deferrals to Excel or print them. Use the **Customer Contract Deferrals Analysis** and **Vendor Contract Deferrals Analysis** pages.

## Examples

### Example 1: 1 year, full months

* **Base amount for deferrals:** 1,200.00
* **Start date:** 01.01.2025
* **End date:** 12/31/2025
* **Basis monthly amount:** 1,200.00
* **Number of full months:** 12
* **Monthly amount:** 100,00

|Posting Date|Number of Days|Deferral Base Amount|Amount|
|--|--|--|--|
|01/01/2025|31|1,200.00|100.00|
|01/02/2025|28|1,200.00|100.00|
|01/03/2025|31|1,200.00|100.00|
|01/04/2025|30|1,200.00|100.00|
|01/05/2025|31|1,200.00|100.00|
|01/06/2025|30|1,200.00|100.00|
|01/07/2025|31|1,200.00|100.00|
|01/08/2025|31|1,200.00|100.00|
|01/09/2025|30|1,200.00|100.00|
|01/10/2025|31|1,200.00|100.00|
|01/11/2025|30|1,200.00|100.00|
|01/12/2025|31|1,200.00|100.00|

### Example 2: 1 year with subperiods

* **Basis amount for deferrals:** 1,200.00
* **Start date:** 01/15/2025
* **End date:** 01/14/2026
* **Basis monthly amount:** 1,098.08
* **Number of full months:** 11
* **Monthly amount:** 99.83

|Posting Date|Number of Days|Deferral Base Amount|Amount|
|--|--|--|--|
|15/01/2025|17|1,200.00|55.89|
|01/02/2025|28|1,200.00|99.83|
|01/03/2025|31|1,200.00|99.83|
|01/04/2025|30|1,200.00|99.83|
|01/05/2025|31|1,200.00|99.83|
|01/06/2025|30|1,200.00|99.83|
|01/07/2025|31|1,200.00|99.83|
|01/08/2025|31|1,200.00|99.83|
|01/09/2025|30|1,200.00|99.83|
|01/10/2025|31|1,200.00|99.83|
|01/11/2025|30|1,200.00|99.83|
|01/12/2025|31|1,200.00|99.83|
|01/01/2026|14|1,200.00|45.98|

### Example 3: less than 1 year with subperiods

* **Basis amount for deferrals:** 1,022.47
* **Start date:** 01/15/2025
* **End date:** 21.11.2025
* **Basis monthly amount:** 897.54
* **Number of full months:** 9
* **Monthly amount:** 99.73

|Posting Date|Number of Days|Deferral Base Amount|Amount|
|--|--|--|--|
|15/01/2025|17|1,022.47|55.89|
|01/02/2025|28|1,022.47|99.73|
|01/03/2025|31|1,022.47|99.73|
|01/04/2025|30|1,022.47|99.73|
|01/05/2025|31|1,022.47|99.73|
|01/06/2025|30|1,022.47|99.73|
|01/07/2025|31|1,022.47|99.73|
|01/08/2025|31|1,022.47|99.73|
|01/09/2025|30|1,022.47|99.73|
|01/10/2025|31|1,022.47|99.73|
|01/11/2025|21|1,022.47|69.01|

## Related information

[Subscription contract renewal](contract-renewal.md)  
[Managing contracts, subscriptions, and subscription lines](contracts-services-mgmt.md)  
