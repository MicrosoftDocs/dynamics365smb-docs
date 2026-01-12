---
title: Update prices
description: You can update prices in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 8025, 
ms.date: 07/11/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Update prices

Regular price updates for contractually agreed, recurring subscription lines are typical in subscription models. With subscription billing, you can easily plan and apply price updates for subscription contract lines.

On the **Customer Subscription Contract** and **Vendor Subscription Contract** pages, you can update contract prices in the following ways:

* Increase (or decrease) the **Price** by a percentage.
* Increase or decrease the **Calculation Base %** field by a percentage.
* Update the prices of recurring subscription lines with the list prices of the items.

You can filter the contract lines to update to all fields on the contract, subscription line, and subscriptions. You can use templates to:

* Save the filters and price update methods.
* Define when the price update is to take effect, until when contract lines are to be included.
* Define how long the price isn't to change after the update (price binding agreement).

On the **Subscription Contract Price Update** page, a price update proposal is created with the selected template. There, you can check all proposed price updates. Group the proposal lines by contract or customer to make them easier to review. Afterward, you can apply all price updates.

Future planned price updates don't take effect immediately. A price increase on 01.01.2026 shouldn't change the price in December 2025. Planned subscription lines are created for this purpose. The planned price update can be displayed, but it doesn't require any manual action. The price update takes effect automatically when the contract line is invoiced to the cut-off date.

If a period in which a price update was applied is credited, the price automatically resets to the original price. At the same time, a planned subscription line is created, which saves the reset price update. If the period is invoiced again, the price update is reapplied. In this way, the prices of the periods are retained. Invoices and credit memos can be created with the original amounts.

## Use price update templates

To create price update proposals, use the **Subscription Contract Price Update** page. To create a proposal, you must use a price update template. To access the list of templates, choose :::image type="content" source="../../media/assist-edit-icon.png" alt-text="Screenshot of the AssistEdit icon."::: in the **Price Update Template** field.

The following sections explain the settings on the **Price Update Templates** page.

### Filters

You can use templates to filter subscription lines. On the **Subscription Lines** page, the selection in the **Partner** field determines whether the price update includes vendor or customer subscription contracts. Use the **Contract Filter**, **Subscription Line Filter**, and **Subscription Filter** fields. Choose a field to open the filter page.

> [!NOTE]
> When you create price update proposals, some filters apply automatically:
>
> * Subscription lines where the **Usage Based Billing** toggle is turned on are excluded.
> * Only subscription lines with the **Invoicing via** field set to **Contract** are included.
> * Contract lines that are **Closed** are excluded.
> * Contract lines marked with **Exclude from Price Update** are excluded.

In addition to these automatic filters, we recommended that you enter `<>''` (not equal to empty) in the **Subscription Line Filter** field. This setting excludes subscription lines that aren't assigned to a contract, or were deleted from the contract after you invoiced them completely, from the price update. The **Closed** field only exists in the contract lines. Accordingly, the automatic filter doesn't apply in these cases.

We also recommend that you exclude subscription lines with the **Discount** toggle on in the **Subscription Line** filter. Discounts can be changed with the price update, if needed. However, this procedure is rather unusual.

If you want to exclude subscription lines with a limited term that could potentially be the subject of subscription contract renewal, filter subscription lines for an empty **Subscription Line End Date**.

You might need to change filters after you change the template. For example, if a customer subscription contract is the filter and you change the partner to **Vendor**, remember to apply the vendor filter. Otherwise, when you create a proposal, no subscription lines are found because there are no lines with **Vendor** as the partner in a customer subscription contract.

### Price update method

On the **Price Update Templates** page, the **Price Update Method** field offers three options. The following table describes the options.

|Option|Description|
|---------|---------|
|**Calculation Base by %**|Sets the **Calculation Base %** field to the value in **Update Value %**. A price update to 20% sets the **Calculation Base %** field to **20%**. With a filter on the old **Calculation Base %** field value, you can increase the percentages of all subscription lines to the new value.|
|**Price by %**|Increases or decreases the price of the contract lines by the percentage in the **Update Value %** field. You can also use negative values. A price update of 2% for a contract line with a price of 100,-, increases the price to 102,-.|
|**Recent Item Price**|Updates the **Calculation Base %** field in the subscription lines with prices from the **Sales Price List** page. The prices for the subscription lines are determined for the items in the subscriptions and the date in **Perform Update on** field. Price updates planned for the future get the prices planned in the sales price list. The discount percentage in the sales price list isn't taken into account in the query because they're often agreed on individually with customers.|

> [!IMPORTANT]
> If a price would be set to zero or become negative due to a price update, a proposal line isn't created for the subscription line.

### Perform Update on Formula (Dateformula)

The dateformula presets the **Perform Update on** field on the **Subscription Contract Price Update** page. The date in the **Perform Update on** field determines when the price update should take effect. However, price updates can't take effect on any date. The price for periods already invoiced can't be, and shouldn't be, changed. Accordingly, the price change takes effect on a later date. The price update takes effect on the last day of the last invoiced period. The old price applies to the period already invoiced and the new price applies to the subsequent period that isn't invoiced. This split avoids unnecessary discrepancies in billing and credit notes.

The same applies to periods that aren't invoiced. For example, if the date in the **Perform Update on** field is 01.15.25, then all days up to 01.15.25 must be charged at the old price. To learn more, go to [Update contract price](#update-contract-price).

> [!NOTE]
> If the date in the **Perform Update On** field is the same as the date in the **Next Billing Date** and **Next Price Update** fields, the price update applies immediately. In the archived subscription lines, **Perform Update On** is saved as **Next Billing Date** minus one day. By placing the price update in the previous period, you can invoice and credit the current period with the new prices without resetting the price update.

### Include Subscription Contract Lines up to Date Formula

The date formula presets the date in the **Include Subscription Contract Lines up to Date Formula** field on the **Subscription Contract Price Update** page. The date in the **Include Contract Lines Up To Date** field is compared with the date in the **Next Price Update** field in the subscription lines to determine whether the subscription line is eligible for a price update.

In each subscription line and contract line, the **Next Price Update** field indicates when you can apply the next price update. This displays the end of the price binding periods and prevents the price from being changed several times in succession by mistake.

The **Next Price Update** field is calculated from the **Subscription Line Start Date** and the **Price Binding Period** fields on the subscription package line when the subscription line is created. For a price update, the **Next Price Update** date recalculates with the **Price Binding Period** from the template and changed in the subscription line.

> [!NOTE]
> You can change the **Next Price Update** date manually at any time and you can change the price of a subscription line at any time, regardless of the **Next Price Update** date.
>
> If a subscription line isn't eligible for a price update according to **Next Price Update**, a proposal line isn't created.

### Price Binding Period

The **Price Binding Period** field determines how long the subscription line shouldn't be taken into account after a price update. If the price is only to increase one time within a year, enter the date formula **1Y**. When the price update happens, the **Next Price Update** field is automatically changed on the subscription line. The new date in the **Next Price Update** field is calculated from the **Perform Update on** plus **Price Binding period** fields. For example, 12.31.2025 + 1Y = 12.31.2026.

### Grouping

The **Grouping** determines how lines display on the **Subscription Contract Price Update** page. The price update proposals can display ungrouped, grouped by contract, or grouped by customer.

## Update contract price

Proposals for price updates can be created, checked, and carried out on the **Subscription Contract Price Update** page. To create a proposal, fill in the **Price Update Template**, **Include Contract Lines Up To Date**, and **Execute Update On** fields.

### Create proposal

The **Create Proposal** action creates proposal lines for all subscription lines in the filter. Each line contains the current price, amount, calculation base percentage, and the new values and the difference between the two. You can personalize the page to add fields such as **Calculation Base %**, **Quantity**, **Discount %**. When created, **Perform Update On** and **Next Price Update** are entered in each proposal line. This means that you can extend the proposal with further templates before the price updates are applied.

If filtering the subscription lines in a template is too complex or not possible, we recommend using several templates. The templates can be selected one after the other in order to add the other subscription lines to the proposal in the new template. For example, to specify that prices in subscription lines younger than a certain date increase by two percent, but older subscription lines only increase by one percent.

> [!IMPORTANT]
> A maximum of one proposal line is created per subscription lines and it isn't updated when the **Create Proposal** action is used again. If the subscription line is the subject of several templates, the proposal for the price update from the first template is kept and subsequent templates don't overwrite it. The same applies to the **Perform Update On** and **Next Price Update** fields.

Proposal lines are suggestions for a price update. The subscription lines or contract lines aren't updated at this point. Based on the data, the proposal might differ from the actual update in regards to the **Perform Update On** date. You can set a date in the past for **Perform Update On**. However, the price in periods already invoiced doesn't change.

If a planned subscription line has **Price Update** or **Contract Extension** selected in the **Type of Update** field, a proposal line isn't created for the subscription line. The planned subscription lines would overwrite the price update in any case. It would come down to the sequence of execution, which is avoided at this point of time. A price update and subscription contract renewal are potentially binding agreements, which is why the combination is currently avoided when you run the **Create Proposal** action.

### Delete proposal lines

The template used to create the proposal line is saved in the line. You can delete the selected or all proposal lines, and the lines that were created with a specific template. This flexibility is helpful if, for example, the **Perform Update On** date was set incorrectly.

Use the **Delete Line** action to delete all selected lines. The **Delete Proposal** action opens a page that asks whether to delete the entire proposal or only the lines that belong to the current template.

Heading lines are automatically deleted if there are no related proposal lines.

### Perform price update

Use the **Perform Price Update** action to apply the price update and delete all proposal lines afterwards. If the price update can apply immediately, the following fields are updated in the subscription line and contract lines:

* Calculation Base %
* Calculation Base
* Discount %
* Price (is recalculated from Calculation Base Amount and Calculation Base %)
* Amount (recalculated from price and quantity)
* Next Price Update
* Price Binding Period

Changes that were made to these fields in the meantime are overwritten. Changes made to other fields are kept.

If the price update can't apply immediately, planned subscription lines are created. For example, you might not be able to apply a price update for the following reasons:

* There are billing lines for a contract line.

   The price update never intervenes in the current invoice run.
* An unposted invoice or credit memo exists.

   The price update doesn't change any documents.
* **Next Billing Date** is before **Next Price Update**.

   If the **Next Billing Date** is before **Next Price Update** (for example, 01.12.2025 is before 01.01.2026), there's a period that must be invoiced with the old price.

The planned subscription line is a copy of the subscription line with a few differences. The fields that are overwritten immediately are taken from the proposal line. In addition, the dates in the **Perform Update On** and **Price Binding Period** fields are copied from the proposal line. The planned subscription line is created with **Price Update** in the **Type of Update** field.

> [!NOTE]
> On the **Planned Subscription Lines** page, use the **Type of Update** field to filter to get a list of price updates that were created or performed but aren't yet in effect. By default, the field is hidden, so you might need to use personalization to add it to the page. To learn more, go to [Personalize your workspace](../../ui-personalization-user.md).

The price update of the planned subscription lines is automatically applied as soon as possible. When you post contract invoices, [!INCLUDE [prod_short](../../includes/prod_short.md)] checks whether there are planned subscription lines for the contract lines and whether it can apply their price updates. If an invoice is posted, there can no longer be any billing lines or unposted documents.

The only remaining condition is that you must invoice the subscription lines until the date in the **Next Price Update** field. The date in the **Next Billing Date** field must not be before the date in the **Next Price Update** field. If this condition is met, the same fields are updated in the subscription line as when the price update is applied immediately.

An archived subscription line is created for every applied price update. The archived subscription line is a copy of the subscription line before the price update with some differences worth mentioning.

The date in the **Perform Update On** field corresponds to the date in the **Next Billing Date** field minus one day. Regardless of the original **Perform Update On** date, the update was performed at the end of the last invoiced period and is valid with the new period. Archiving exactly when the price update actually came into effect is essential for maintaining period-accurate prices. If the last period is credited, the price update must be canceled in order to be able to use the prices of the last period. The **Type of Update** is set to **Price update** on the archived subscription line.

> [!IMPORTANT]
> If the date in the **Perform Update On** field is before the date in the **Next Price Update** field, the price update can still be applied if the subscription line was invoiced until or beyond **Next Price Update**. The **Perform Update On** date is changed to **Next Billing Date** - 1D in the archived subscription line because the price update only came into effect at the end of the last period. In this case, the decisive factor as to whether the price update can be applied is that the complete period for which the old price applies is invoiced.

The price update in the planned subscription lines applies when an invoice is posted.

**Example 1**

The price update can take effect immediately.

|Type|Next Billing Date|Next Price Update|Perform Update on|Price Binding Period|Price|
|:--|:--|:--|:--|:--|:--|
|Subscription line before price update|01.01.2024|12.31.2023|-|1Y|Old|
|Proposal Price update|-|12.31.2024|12.31.2023|1Y|New|
|`Immediate execution`|||12.31.2023 equal to or after 23.31.2023||
|Subscription line after price update|01.01.2024|12.31.2024|-|1Y|New|
|Archived subscription lines|01.01.2024|12.31.2023|12.31.2023|1Y|Old|

> [!IMPORTANT]
> The prices wouldn't update if the **Perform Update On** date was 02.01.2024. The **Next Billing Date** field describes the next day that can be calculated, which includes this day. 01.01.2024 would have to be invoiced at the old price before the price update can take effect.

**Example 2**

The price update can't take effect immediately. A planned subscription line is created to save the price update and apply it later automatically (when posting an invoice as soon as the conditions are met).

| Type|Next Billing Date|Next Price Update|Perform Update on|Price Binding Period|Price |
|:--|:--|:--|:--|:--|:--|
|subscription line before price update|01.01.2024|12.31.2023|-|1Y|Old|
|Proposal Price update|-|12.31.2024|01.15.2024|1Y|New|
|Planned Subscription Lines necessary|||01.01.2024 is before 01.15.2024||
|Planned subscription line|01.01.2024|12.31.2024|01.15.2024|1Y|New|
|Invoice 01.01.2024 - 12.31.2024||||Old|
|Subscription line after price update|01.01.2025|12.31.2024|-|1Y|New|
|Archived subscription lines|01.01.2025|12.31.2024|12.31.2024|1Y|Old|

> [!IMPORTANT]
> Price updates and the date in the **Perform Update On** field in planned subscription lines don't affect the invoicing of subscription line. The price update applies automatically after invoicing.

The **Next Price Update** date doesn't adjust to the changed date when the price update actually took effect.

## Reset price update / credit memo

Regardless of price updates, a credit memo is always created with the same amount as the invoice. In addition, price updates reset to ensure that prices stay correct in each period.

When a contract invoice is credited, [!INCLUDE [prod_short](../../includes/prod_short.md)] checks whether a price update happened in the credited period. If a price update happened, it resets.

Price updates never take effect in the middle of invoiced periods. A subscription line is calculated at exactly one price. If a price update falls within the invoice period, it won't take effect until after the invoiced period.

**Example**

* The date in the **Perform Update On** field is 01.15.2024.
* Invoice period is 01.01.2024 - 01.31.2024.
* The period 01.01.24 - 01.14.2024 must be invoiced at the old price. Because price updates don't affect invoicing, the entire period is invoiced at the old price.
* The price update take effect at the end of the invoiced period (01.31.2024).

When this invoice is credited again, the date in the **Next Billing Date** field is again 01.01.2024. On this date, the old price was originally valid and the price update wasn't in effect. The price update is canceled and the original prices as of 01.01.2024 are restored. The contract invoices can be issued with the original prices.

When the price update is withdrawn, a planned subscription line is created to reapply the price update (01.31.2024) when you invoice the period again.

The planned subscription line that is created together with a credit memo has the date 01.31.2024 in **Perform Update On** in the example. The reason for this is that the price update didn't come into effect until 01.31.2024 and only applies to the next period. For **Perform Update On**, the **Next Billing Date** after the invoice is never used, as otherwise the price update would be incorrectly canceled in the following period.

**Example**

The date in the **Perform Update On** field is 01.15.2024.
Invoice 01.01.2024 - 01.31.2024
Archived subscription line **Perform Update On** 02.01.2024
Invoice 02.01.2024 - 02.29.2024 (new price applies without restriction for the period)
Credit Memo --> The price update shouldn't be canceled.

If prices were edited manually, they're used when the price update is canceled and reapplied. In this case, however, it's more difficult to trace the steps using archived and planned subscription lines.

If the prices were changed after the credit memo, the price update overwrites them.

The price update can be canceled/deleted after the credit memo by deleting the planned subscription lines.

## Related information

[Currencies](../sales/dealing-with-currencies.md)
