---
title: Price update
description: You can update prices in subscription and recurring billing.
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


# Price update

Regular price updates of contractually agreed, recurring Service Commitments are completely normal in times of subscription models. With subscription billing, price updates for contractual Service Commitments can be easily planned and applied.

Contract prices can be updated in three different ways:

* Increase (or decrease) the price to a percentage
* Increasing or decreasing the Calculation Base % by a percentage
* Updating the prices of recurring Service Commitments with the list prices of the items

The Contract lines that are to receive a price update can be filtered according to all fields in the Contract, Service Commitment and Service Objects. Templates can be used to save the filters and price update methods, predefine when the price update is to take effect, until when Contract lines are to be included and how long the price is not to be changed after the update (price binding agreement).

On the **Contract Price Update** page, a price update proposal is created with the selected template. All proposed price updates can be checked here. Grouping the proposal lines by contract or customer increases readability. After checking, all price updates can be applied with one click.

Future **planned price updates** do not take effect immediately. A price increase on 01.01. should not change the price in December. **Planned Service Commitments** are created specifically for this purpose. The planned price update can be displayed to the user, but it does not require any manual intervention. The price update will take effect automatically as soon as the Contract line has been invoiced to the cut-off date.

If a period in which a price update was applied is credited, the price is automatically reset to the original price. At the same time, a **Planned Service Commitment** is automatically created, which saves the reset price update. If the period is invoiced again, the price update is re-applied. In this way, the prices of the periods are retained. Invoices and credit notes can be created with the original amounts.

## Templates

The **Contract Price Update** page (*Alt+Q*) is used to create price update proposals. In order to create a proposal, a template must be used. The list of **Price Update Templates** can be opened via the AssistEdit in the **Price Update Template** field.

### Filters

Templates can be used to filter Service Commitments. The **Partner** specified in the template determines whether Vendor Contracts or Customer Contracts are included in the price update. The filters are created using the **Contract filter**, **Service filter** and **Service Object filter** fields. Clicking on one of the fields opens the filter page.

> [!NOTE]
> When creating price update proposals, some filters are applied automatically:
>
> * Service Commitments with the **Usage Based Billing** indicator are not taken into account.
> * Only Service Commitments with **Invoicing via** *Contract* are taken into account.
> * Contract lines that have been **Closed** are not taken into account.
> * Contract lines marked with **Exclude from Price Update** are not taken into account.

In addition to these automatic filters, it is recommended to enter `<>''` (not equal to empty) in the Service Commitment filter **Contract**. This prevents Service Commitments, that are not yet assigned to a contract or have been deleted from the contract after being invoiced completely, from being included in the price update. The **Closed** field only exists in the Contract lines. Accordingly, the automatic filter does not apply in these cases.

It is also advisable to exclude Service Commitments with the **Discount** indicator in the Service Commitment filter. Discounts can be changed with the price update if so desired. However, this procedure is rather unusual.

If Service Commitments with a limited term that could potentially be the subject of contract renewal are to be excluded, Service Commitments must be filtered for an empty Service End Date.

Filters may need to be changed after changes have been made to the template. For example, if a Customer Contract is filtered and the partner is changed to *Vendor*, the filter will remain on the Customer Contract. When a proposal is created, no services are found as there are no services with partner *Vendor* in a Customer Contract.
:::


### Price Update Method
There are three **Price Update Methods**
* **Price by %** <br/>
Increases or decreases the price of the Contract lines by the percentage in **Update Value %**. The use of negative values is possible. A price update of 2% for a Contract line with a price of 100,-, will increase the price to 102,-.
* **Calculation Base by %** <br/>
Sets the Calculation Base % to the value in **Update Value %**. A price update to 20% sets the Calculation Base % to 20%. With a filter on the old Calculation Base %, the percentages of all Service Commitments can be increased to the new value with just a few clicks.
**Recent Item Price** <br/>
Updates the Calculation Base % in the Service Commitments with prices from the Sales Price List. The prices for the Service Commitments are determined for the items in the Service Objects and the date in **Perform Update on**. Price updates planned for the future thus receive the prices planned in the Sales Price List. The discount % in the Sales Price List is not taken into account in the query, as these are often agreed on individually with customers.

:::caution Important
If a price would be set to 0 or become negative due to a price update, no proposal line is created for the Service Commitment.
:::


### Perform update on (Dateformula)
The dateformula presets **Perform Update on** in the **Contract Price Update** page. The date **Perform Update on** determines when the price update should take effect. However, price updates cannot take effect on any date. The price for periods already invoiced cannot and should not be changed. Accordingly, the price change will not take effect until a later date. The price update takes effect on the last day of the last invoiced period. This means that the old price applies to the period already invoiced and the new price applies to the subsequent period that has not been invoiced. This avoids unnecessary discrepancies in billing and credit notes.

The same applies to periods that have not yet been invoiced. If **Perform Update on** is 15.01., then all days up to 15.01. must be charged at the old price. How exactly the date determination works is explained in more detail in the paragraph **[Contract Price Update](#contract-price-update)**.

:::note Note
If **Perform Update on** equals **Next Billing Date** (and **Next Price Update**), the price update is applied out immediately. In the archived Service Commitments, **Perform Update on** is saved as **Next Billing Date** minus 1 day. By placing the price update in the previous period, the current period can be invoiced and credited with the new prices without the price update being reset.
:::


### Include Contract Lines Up To Date (Dateformula)
The dateformula presets **Include Contract Lines Up To Date** in the **Contract Price Update** page. The date in **Include Contract Lines Up To Date** is compared with the date in **Next Price Update** in the Service Commitments to determine whether the Service Commitment is eligible for a price update.

In each Service Commitment / Contract line, the **Next Price Update** field indicates when the next price update can be applied. This displays the end of the price binding periods and prevents the price from being changed several times in succession by mistake. <br/>
The **Next Price Update** is calculated from the **Service Start Date** and the **Price Binding Period** in the line Service Commitment Package line when the Service Commitment is created. In the event of a price update, the **Next Price Update** date is recalculated with the **Price Binding Period** from the template and changed in the Service Commitment.

:::info Info
The **Next Price Update** date can be changed manually at any time. The price of a Service Commitment can be changed at any time regardless of the **Next Price Update** date.
If a Service Commitment is not yet eligible for a price update again according to **Next Price Update**, no proposal line is created.
:::


### Price Binding Period
The **Price Binding Period** determines how long the Service Commitment should not be taken into account after a price update. If the price is only to be increased once within the a year, the Dateformula *1Y* is entered. When the price update is carried out, the **Next Price Update** is automatically changed in the Service Commitment. The new date **Next Price Update** is calculated from **Perform Update on** plus **Price Binding period** (e.g. 31.12.2023 + 1Y = 31.12.2024).


### Grouping
The **Grouping** determines how lines are displayed in the **Contract Price Update** page. The price update proposals can be displayed *ungrouped*, grouped by *Contract* or grouped by *Customer*.


## Contract Price Update
Proposals for price updates can be created, checked and carried out on the **Contract Price Update** page. The page can be opened via the search (*Alt+Q*). The **Price Update Template**, **Include Contract Lines Up To Date** and **Execute update on** must be entered in order to create a proposal.


### Create proposal
The **Create proposal** action creates proposal lines for all Service Commitments in the filter. Each line contains the current price, amount, Calculation Base % as well as the new values and the difference between the two. Fields such as Calculation Base %, Quantity, Discount %, etc. can be displayed using **Personalization**. When created, **Perform update on** and **Next Price Update** are entered in each proposal line. This means that the proposal can easily be extended with further templates before the price updates are applied.

If filtering the Service Commitments in a template is too complex or not possible, we recommend using several templates. The templates can be selected one after the other in order to add the additional Service Commitments to the proposal in the new template (e.g. prices in Service Commitments younger then xx.xx. will be increased by 2% but older Service Commitments are only increased by 1%).

:::caution Important
A maximum of one proposal line is created per Service Commitments and it is not updated when the **Create proposal** action is used again. If the Service Commitment is the subject of several templates, the proposal for the price update from the first template is retained and is not overwritten by subsequent templates. This also applies to the **Perform Update on** and **Next Price Update** fields.

Proposal lines are proposals for a price update. No update of the Service Commitments / Contract lines has been done at this point. Based on the data, the proposal may differ from the actual update in regards to the date **Perform Update on**. It is therefore possible to set a date in the past for **Perform Update on**. However, the price in periods already invoiced will not be changed.

If a planned Service Commitment with **Type of update** *Price update* or *Contract extension* exists, no proposal line is created for this Service Commitment. The planned Service Commitments would overwrite the price update in any case. I would come down to the sequence of execution, which is avoided at this point of time. A price update and contract renewal are potentially binding agreements, which is why the combination is currently avoided when **Create Proposal** is executed.
:::

### Delete proposal lines
The template used to create the proposal line is saved in the line. Accordingly, it is not only possible to delete the selected or all proposal lines, but also the lines that were created with a specific template. This is particularly helpful if, for example, the **Perform Update on** was set incorrectly. <br/>
The **Delete Line** action deletes all selected lines. The **Delete Proposal** action opens a page that asks whether the entire proposal or only the lines belonging to the current template should be deleted. <br/>
Heading lines are automatically deleted if there are no more related proposal lines.


### Perform price update
The **Perform price update** action performs the price update and deletes all proposal lines afterwards. If the price update can be applied immediately, the following fields are updated in the Service Commitment/ Contract lines:
* Calculation Base %
* Calculation Base
* Discount %
* Price (is recalculated from Calculation Base Amount and Calculation Base %)
* Service Amounts (recalculated from price and quantity)
* Next Price Update
* Price Binding Period

Changes, that have been made to these fields in the meantime, are overwritten. <br/>
Changes made to other fields are retained.

If the price update cannot be applied immediately, planned Service Commitments are created. The price update can potentially not be applied immediately for the following reasons:
* There are billing lines for a Contract line. <br/>
The price update never intervenes in the current invoice run.
* There is an unposted invoice or credit note. <br/>
The price update does not change any documents.
* **Next Billing Date** is before **Next Price Update**. <br/>
If the **Next Billing Date** is before **Next Price Update** (e.g. 22.11.2023 is before 31.12.2023), there is a period that must be invoiced with the old price.

The planned Service Commitment is a copy of the Service Commitment with a few deviations. The fields that are overwritten immediately are taken from the proposal line (listed above: Calculation Base %, etc.). In addition, the dates in **Perform update on**, **Perform update on** and **Price Binding Period** are copied from the proposal line. The planned Service Commitment is created with the **Type of update** *Price update*.

:::info Note
In the **Planned Service Commitments** list, the **Type of Update** field can be ued for filtering to obtain a list of price updates that have already been created/performed but have not yet come into effect.
:::

The price update of the planned Service Commitments is automatically applied as soon as possible. When contract invoices are posted, the system checks whether there are planned Service Commitments for the contract lines invoiced and whether their price updates can be applied. If an invoice is posted, there can no longer be any billing lines or unposted documents.
Accordingly, the only remaining condition is that the Service Commitments must be invoiced until the **Next Price Update** date *(Next Billing Date must not be before Next Price Update)*.
If this condition is met, the same fields are updated in the Service Commitment as when the price update is applied immediately.

An **Archived Service Commitment** is created for every applied price update.
The archived Service Commitment is a copy of the Service Commitment before the price update with some differences worth mentioning.
**Perform update on** corresponds to the **Next Billing Date** minus one day. Regardless of when the original **Perform update on** was, the update was performed at the end of the last invoiced period and is valid with the new period. Archiving exactly when the price update actually came into effect is essential for maintaining period-accurate prices. If the last period is credited, the price update must be canceled in order to be able to use the prices of the last period. The **Type of update** is set to *Price update* in the **Archived Service Commitment**.


:::caution Important
If the date in **Perform Update on** is before **Next Price Update**, the price update can still be applied, if the Service Commitment has been invoiced until or beyond **Next Price Update**. The **Perform Update on** date is changed to **Next Billing Date** - 1D in the archived Service Commitment because the price update only came into effect at the end of the last period. The decisive factor as to whether the price update can be applied in this case, is that the complete period for which the old price applies has been invoiced.

If the price update was not applied due to existing billing lines or unposted invoices (planned Service Commitments created), the price update will not be applied if the invoice or billing lines are deleted. The price update in the planned Service Commitments is only applied when an invoice is posted.
:::

**Example 1** <br/>
The price update can take effect immediately.

|Type|Next Billing Date|Next Price Update|Perform Update on|Price Binding Period|Price|
|:--|:--|:--|:--|:--|:--|
|Service Commitment before price update|01.01.2024|31.12.2023|-|1Y|Old|
|Proposal Price update|-|31.12.2024|31.12.2023|1Y|Neu|
|`Immediate execution`|||31.12.2023 equal to or after 31.12.2023||
|Service Commitment after price update|01.01.2024|31.12.2024|-|1Y|New|
|Archived Service Commitments|01.01.2024|31.12.2023|31.12.2023|1Y|Old|

:::caution Important
The price update would not have been performed if the **Perform update on** date had been 02.01.2024. The **Next Billing Date** describes the next day that can be calculated. This includes this day. This means that 01.01.2024 would have to be invoiced at the old price before the price update can take effect.
:::

**Example 2** <br/>
The price update cannot take effect immediately. A planned Service Commitment is created to save the price update and apply it later automatically (when posting an invoice as soon as the conditions are met).

|Type|Next Billing Date|Next Price Update|Perform Update on|Price Binding Period|Price|
|:--|:--|:--|:--|:--|:--|
|Service Commitment before price update|01.01.2024|31.12.2023|-|1Y|Old|
|Proposal Price update|-|31.12.2024|15.01.2024|1Y|Neu|
|`Planned Service Commitments necessary`|||01.01.2024 is before 15.01.2024||
|`Planned Service Commitment|01.01.2024|31.12.2024|15.01.2024|1Y|New|
|`Invoice 01.01.2024 - 31.12.2024`||||Old|
|Service Commitment after price update|01.01.2025|31.12.2024|-|1Y|New|
|Archived Service Commitments|01.01.2025|31.12.2024|31.12.2024|1Y|Old|

:::caution Important
Price updates and **Perform Update on** in planned Service Commitments do not affect the invoicing of Service Commitment. The price update will be applied automatically after invoicing it as soon as this is possible.

The **Next Price Update** date will not be adjusted to the changed date when the price update actually came into effect.
:::


## Reset price update / Credit Memo
Regardless of price updates, a credit memo is always created with the same amount as the invoice. In addition, price updates are reset to ensure that prices stay correct in each period.

When a contract invoice is credited, the system checks whether a price update has taken place in the credited period. If a price update has taken place, it is reset.

Price updates never take effect in the middle of invoiced periods. A Service Commitment is calculated at exactly one price. If a price update falls within the invoice period, it will not actually take effect until after the invoiced period.

Example
**Perform Update on** 15.01.2024 <br/>
Invoice 01.01.2024 - 31.01.2024 <br/>
The period 01.01. - 14.01.2024 must be invoiced at the old price. As price updates do not affect invoicing, the entire period will be invoiced at the old price.
The price update will take effect at the end of the invoiced period (31.01.2024).

When this invoice is credited again, the **Next Billing Date** will again be 01.01.2024. On this date, the old price was originally valid and the price update had not yet come into effect. Accordingly, the price update will be canceled and the original prices as of 01.01.2024 will be restored. The contract invoices can be issued with the original prices without the user having to do anything.

When the price update is withdrawn, a planned Service Commitment is created at the same time, which reapplies the price update (31.01.2024) when the period is invoiced again.

:::caution Important
The planned Service Commitment that is created together with a credit memo has the date 31.01.2024 in **Perform update on** in the example above. The reason for this is that the price update did not actually come into effect until 31.01.2024 and only applies to the next period. For **Perform Update on**, the **Next Billing Date** after the invoice is never used, as otherwise the price update would be incorrectly canceled in the following period.

Example
**Perform Update on** 15.01.2024 <br/>
Invoice 01.01.2024 - 31.01.2024 <br/>
Archived Service Commitment **Perform Update on** 01.02.2024 <br/>
Invoice 01.02.2024 - 29.02.2024 (new price applies without restriction for the period) <br/>
Credit Memo --> The price update should not be canceled.

If prices have been edited manually, they will be used when the price update is canceled and re-applied. In this case, however, it is more difficult to trace the steps using archived and planned Service Commitments.

If the prices were changed after the credit memo, they will be overwritten by the price update.

The price update can be canceled/deleted after the credit memo by deleting the planned Service Commitments.
:::