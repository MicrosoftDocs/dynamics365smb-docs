---
title: Update prices
description: You can update prices in subscription and recurring billing.
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


# Update prices

Regular price updates for contractually agreed, recurring service commitments are typical in subscription models. With subscription billing, you can easily plan and apply price updates for contractual service commitments.

You can update contract prices in the following ways:

* Increase (or decrease) the price to a percentage.
* Increase or decrease the **Calculation Base %** field by a percentage.
* Update the prices of recurring service commitments with the list prices of the items.

You can filter the contract lines to update to all fields on the contract, service commitment, and service objects. You can use templates to:

* Save the filters and price update methods.
* Define when the price update is to take effect, until when contract lines are to be included.
* Define how long the price isn't to change after the update (price binding agreement).

On the **Contract Price Update** page, a price update proposal is created with the selected template. There, you can check all proposed price updates. Group the proposal lines by contract or customer to make the easier to review. Afterwared, you can apply all price updates.

Future planned price updates don't take effect immediately. A price increase on 01.01. should not change the price in December. Planned service commitments are created specifically for this purpose. The planned price update can be displayed, but it doesn't require any manual action. The price update takes effect automatically when the contract line is invoiced to the cut-off date.

If a period in which a price update was applied is credited, the price  automatically resets to the original price. At the same time, a planned service commitment is created, which saves the reset price update. If the period is invoiced again, the price update is re-applied. In this way, the prices of the periods are retained. Invoices and credit notes can be created with the original amounts.

## Templates

Use the **Contract Price Update** page to create price update proposals. To create a proposal, you must use a price update template. To access the list of templates, use the **Price Update Template** field.

### Filters

You can use templates to filter service commitments. The **Partner** specified in the template determines whether vendor contracts or customer contracts are included in the price update. Use the **Contract filter**, **Service filter**, and **Service Object filter** fields. Choose a field to opens the filter page.

> [!NOTE]
> When you create price update proposals, some filters are applied automatically:
>
> * Service commitments where the **Usage Based Billing** toggle is on aren't included.
> * Only service commitments with the **Invoicing via** field set to **Contract** are included.
> * Contract lines that are **Closed** aren't included.
> * Contract lines marked with **Exclude from Price Update** aren't included.

In addition to these automatic filters, we recommended that you enter `<>''` (not equal to empty) in the **Contract** service commitment filter. This settings prevents service commitments that aren't assigned to a contract, or have been deleted from the contract after being invoiced completely, from being included in the price update. The **Closed** field only exists in the contract lines. Accordingly, the automatic filter doesn't apply in these cases.

We also recommend that you exclude service commitments with the **Discount** toggle on in the service commitment filter. Discounts can be changed with the price update, if needed. However, this procedure is rather unusual.

If you want to exclude service commitments with a limited term that could potentially be the subject of contract renewal, filter service commitments for an empty **Service End Date**.

You might need to change filters after you change the template. For example, if a customer contract is filtered and the partner is changed to **Vendor**, the filter remains on the customer contract. When you create a proposal is created, no services are found as there are no services with partner **Vendor** in a customer contract.

### Price update method

There are three **Price Update Methods**:

* **Price by %**

   Increases or decreases the price of the contract lines by the percentage in **Update Value %**. The use of negative values is possible. A price update of 2% for a contract line with a price of 100,-, will increase the price to 102,-.
* **Calculation Base by %**

   Sets the **Calculation Base %** field to the value in **Update Value %**. A price update to 20% sets the **Calculation Base %** field to **20%**. With a filter on the old **Calculation Base %** field value, you can increase the percentages of all service commitments to the new value with just a few clicks.
**Recent Item Price**

   Updates the **Calculation Base %** field in the service commitments with prices from the **Sales Price List** page. The prices for the service commitments are determined for the items in the service objects and the date in **Perform Update on** field. Price updates planned for the future get the prices planned in the sales price list. The discount percentage in the sales price list is not taken into account in the query, because they're are often agreed on individually with customers.

> [!IMPORTANT]
> If a price would be set to zero or become negative due to a price update, a proposal line isn't created for the service commitment.

### Perform update on (Dateformula)

The dateformula presets **Perform Update on** field on the **Contract Price Update** page. The date in the **Perform Update on** field determines when the price update should take effect. However, price updates can't take effect on any date. The price for periods already invoiced can't, and shouldn't be changed. Accordingly, the price change won't take effect until a later date. The price update takes effect on the last day of the last invoiced period. This means that the old price applies to the period already invoiced and the new price applies to the subsequent period that hasn't been invoiced. This avoids unnecessary discrepancies in billing and credit notes.

The same applies to periods that you haven't invoiced. For example if the date in the **Perform Update on** field is 15.01., then all days up to 15.01. must be charged at the old price. To learn more, go to [Update contract price](#update-contract-price).

> [!NOTE]
> If the date in the **Perform Update on** field is the same as the date in the **Next Billing Date** and **Next Price Update** fields, the price update applies immediately. In the archived service commitments, **Perform Update on** is saved as **Next Billing Date** minus one day. By placing the price update in the previous period, you can invoice and credit the current period with the new prices without resetting the price update.

### Include contract lines up to date (Dateformula)

The dateformula presets the date in the **Include Contract Lines Up To Date** field on the **Contract Price Update** page. The date in the **Include Contract Lines Up To Date** field is compared with the date in the **Next Price Update** field in the service commitments to determine whether the service commitment is eligible for a price update.

In each service commitment and contract line, the **Next Price Update** field indicates when you can apply the next price update. This displays the end of the price binding periods and prevents the price from being changed several times in succession by mistake.

The **Next Price Update** field is calculated from the **Service Start Date** and the **Price Binding Period** on the service commitment package line when the service commitment is created. In the event of a price update, the **Next Price Update** date recalculates with the **Price Binding Period** from the template and changed in the service commitment.

> [!NOTE]
> You can change the **Next Price Update** date manually at any time. The price of a service commitment can be changed at any time, regardless of the **Next Price Update** date.
> If a service commitment isn't eligible for a price update according to **Next Price Update**, a proposal line isn't created.

### Price binding period

The **Price Binding Period** determines how long the service commitment shouldn't be taken into account after a price update. If the price is only to increase one time within the a year, enter the Dateformula *1Y*. When the price update happens, the **Next Price Update** field is automatically changed in the service commitment. The new date in the **Next Price Update** field is calculated from from the **Perform Update on** plus **Price Binding period** fields. For example, 31.12.2023 + 1Y = 31.12.2024.

### Grouping

The **Grouping** determines how lines display on the **Contract Price Update** page. The price update proposals can display ungrouped, grouped by contract. or grouped by customer.

## Update contract price

Proposals for price updates can be created, checked, and carried out on the **Contract Price Update** page. To create a proposal, fill in the **Price Update Template**, **Include Contract Lines Up To Date** and **Execute update on** fields.

### Create proposal

The **Create proposal** action creates proposal lines for all service commitments in the filter. Each line contains the current price, amount, calculation base percentage, and the new values and the difference between the two. You can personalize the page to add fields such as **Calculation Base %**, **Quantity**, **Discount %**. When created, **Perform update on** and **Next Price Update** are entered in each proposal line. This means that you can extend the proposal with further templates before the price updates are applied.

If filtering the service commitments in a template is too complex or not possible, we recommend using several templates. The templates can be selected one after the other in order to add the additional service commitments to the proposal in the new template. For example, to specify that prices in service commitments younger then xx.xx. increase by 2%, but older service commitments only increase by 1%.

> [!IMPORTANT]
> A maximum of one proposal line is created per service commitments and it is not updated when the **Create proposal** action is used again. If the service commitment is the subject of several templates, the proposal for the price update from the first template is retained and is not overwritten by subsequent templates. This also applies to the **Perform Update on** and **Next Price Update** fields.

Proposal lines are proposals for a price update. No update of the service commitments or contract lines has been done at this point. Based on the data, the proposal might differ from the actual update in regards to the **Perform Update on** date. You can set a date in the past for **Perform Update on**. However, the price in periods already invoiced won't change.

If a planned service commitment has **Price update** or **Contract extension** selected in the **Type of update** field, a proposal line isn't created for the service commitment. The planned service commitments would overwrite the price update in any case. It would come down to the sequence of execution, which is avoided at this point of time. A price update and contract renewal are potentially binding agreements, which is why the combination is currently avoided when you run the **Create Proposal** action.

### Delete proposal lines

The template used to create the proposal line is saved in the line. you can delete the selected or all proposal lines, and the lines that were created with a specific template. This is particularly helpful if, for example, the **Perform Update on** date was set incorrectly.

Use the **Delete Line** action to delete all selected lines. The **Delete Proposal** action opens a page that asks whether the entire proposal or only the lines belonging to the current template should be deleted.

Heading lines are automatically deleted if there are no more related proposal lines.

### Perform price update

Use the **Perform price update** action to apply the price update and delete all proposal lines afterwards. If the price update can apply immediately, the following fields are updated in the service commitment and contract lines:

* Calculation Base %
* Calculation Base
* Discount %
* Price (is recalculated from Calculation Base Amount and Calculation Base %)
* Service Amounts (recalculated from price and quantity)
* Next Price Update
* Price Binding Period

Changes that were made to these fields in the meantime are overwritten. Changes made to other fields are retained.

If the price update can't apply immediately, planned service commitments are created. The price update can potentially not be applied immediately for the following reasons:

* There are billing lines for a contract line.

   The price update never intervenes in the current invoice run.
* There is an unposted invoice or credit note.

   The price update does not change any documents.
* **Next Billing Date** is before **Next Price Update**.

   If the **Next Billing Date** is before **Next Price Update** (for example, 22.11.2023 is before 31.12.2023), there is a period that must be invoiced with the old price.

The planned service commitment is a copy of the service commitment with a few differences. The fields that are overwritten immediately are taken from the proposal line. In addition, the dates in the **Perform update on**, **Perform update on**, and **Price Binding Period** fields are copied from the proposal line. The planned service commitment is created with **Price update** in the **Type of update** field.

> [!NOTE]
> In the **Planned Service Commitments** list, use the **Type of Update** field to filter to get a list of price updates that were created or performed but aren't yet in effect.

The price update of the planned service commitments is automatically applied as soon as possible. When contract invoices are posted, [!INCLUDE [prod_short](../../includes/prod_short.md)] checks whether there are planned service commitments for the contract lines invoiced and whether it can apply their price updates. If an invoice is posted, there can no longer be any billing lines or unposted documents.
The only remaining condition is that you must invoice the service commitments until the date in the **Next Price Update** field. The date in the **Next Billing Date** field must not be before the date in the **Next Price Update** field. If this condition is met, the same fields are updated in the service commitment as when the price update is applied immediately.

An archived service commitment is created for every applied price update.
The archived service commitment is a copy of the service commitment before the price update with some differences worth mentioning.

The date in the **Perform update on** field corresponds to the date in the **Next Billing Date** field minus one day. Regardless of the original **Perform update on** date, the update was performed at the end of the last invoiced period and is valid with the new period. Archiving exactly when the price update actually came into effect is essential for maintaining period-accurate prices. If the last period is credited, the price update must be canceled in order to be able to use the prices of the last period. The **Type of update** is set to **Price update** on the archived service commitment.

> [!IMPORTANT]
> If the date in the **Perform Update on** field is before the date in the **Next Price Update** field, the price update can still be applied if the service commitment has been invoiced until or beyond **Next Price Update**. The **Perform Update on** date is changed to **Next Billing Date** - 1D in the archived service commitment because the price update only came into effect at the end of the last period. In this case, the decisive factor as to whether the price update can be applied is that the complete period for which the old price applies is invoiced.

If the price update wasn't applied, due to existing billing lines or unposted invoices (planned service commitments created), the price update won't be applied if the invoice or billing lines are deleted. The price update in the planned service commitments is only applied when an invoice is posted.

**Example 1**

The price update can take effect immediately.

|Type|Next Billing Date|Next Price Update|Perform Update on|Price Binding Period|Price|
|:--|:--|:--|:--|:--|:--|
|Service commitment before price update|01.01.2024|31.12.2023|-|1Y|Old|
|Proposal Price update|-|31.12.2024|31.12.2023|1Y|Neu|
|`Immediate execution`|||31.12.2023 equal to or after 31.12.2023||
|Service commitment after price update|01.01.2024|31.12.2024|-|1Y|New|
|Archived service commitments|01.01.2024|31.12.2023|31.12.2023|1Y|Old|

> [!IMPORTANT]
> The price update wouldn't have happened if the **Perform update on** date was 02.01.2024. The **Next Billing Date** field describes the next day that can be calculated, which includes this day. This means that 01.01.2024 would have to be invoiced at the old price before the price update can take effect.

**Example 2**

The price update can't take effect immediately. A planned service commitment is created to save the price update and apply it later automatically (when posting an invoice as soon as the conditions are met).

|Type|Next Billing Date|Next Price Update|Perform Update on|Price Binding Period|Price|
|:--|:--|:--|:--|:--|:--|
|service commitment before price update|01.01.2024|31.12.2023|-|1Y|Old|
|Proposal Price update|-|31.12.2024|15.01.2024|1Y|Neu|
|`Planned service commitments necessary`|||01.01.2024 is before 15.01.2024||
|`Planned service commitment|01.01.2024|31.12.2024|15.01.2024|1Y|New|
|`Invoice 01.01.2024 - 31.12.2024`||||Old|
|Service commitment after price update|01.01.2025|31.12.2024|-|1Y|New|
|Archived service commitments|01.01.2025|31.12.2024|31.12.2024|1Y|Old|

> [!IMPORTANT]
> Price updates and the date in the **Perform Update on** field in planned service commitments don't affect the invoicing of service commitment. The price update applies automatically after invoicing as soon as this is possible.

The **Next Price Update** date won't adjust to the changed date when the price update actually came into effect.

## Reset price update / credit memo

Regardless of price updates, a credit memo is always created with the same amount as the invoice. In addition, price updates reset to ensure that prices stay correct in each period.

When a contract invoice is credited, [!INCLUDE [prod_short](../../includes/prod_short.md)] checks whether a price update happened in the credited period. If a price update happened, it resets.

Price updates never take effect in the middle of invoiced periods. A service commitment is calculated at exactly one price. If a price update falls within the invoice period, it won't take effect until after the invoiced period.

**Example**

The date in the **Perform Update on** field is 15.01.2024.
Invoice 01.01.2024 - 31.01.2024.
The period 01.01. - 14.01.2024 must be invoiced at the old price. Because price updates don't affect invoicing, the entire period is invoiced at the old price.
The price update take effect at the end of the invoiced period (31.01.2024).

When this invoice is credited again, the date in the **Next Billing Date** field will again be 01.01.2024. On this date, the old price was originally valid and the price update hadn't come into effect. The price update is canceled and the original prices as of 01.01.2024 are restored. The contract invoices can be issued with the original prices.

When the price update is withdrawn, a planned service commitment is created at the same time, which reapplies the price update (31.01.2024) when the period is invoiced again.

The planned service commitment that is created together with a credit memo has the date 31.01.2024 in **Perform update on** in the example above. The reason for this is that the price update did not actually come into effect until 31.01.2024 and only applies to the next period. For **Perform Update on**, the **Next Billing Date** after the invoice is never used, as otherwise the price update would be incorrectly canceled in the following period.

**Example**

The date in the **Perform Update on** field is 15.01.2024.
Invoice 01.01.2024 - 31.01.2024
Archived service commitment **Perform Update on** 01.02.2024
Invoice 01.02.2024 - 29.02.2024 (new price applies without restriction for the period)
Credit Memo --> The price update shouldn't be canceled.

If prices were edited manually, they're used when the price update is canceled and re-applied. In this case, however, it's more difficult to trace the steps using archived and planned service commitments.

If the prices were changed after the credit memo, the price update overwrites them.

The price update can be canceled/deleted after the credit memo by deleting the planned service commitments.

## Related information

[Currencies](../sales/dealing-with-currencies.md)
