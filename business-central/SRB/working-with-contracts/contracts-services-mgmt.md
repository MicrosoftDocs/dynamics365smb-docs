---
title: Managing contracts, subscriptions, and subscription lines
description: You can manage subscription contracts in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: 
ms.search.form: 8014, 8071, 8053, 8052, 8004, 8015
ms.date: 07/11/2025
ms.service: dynamics-365-business-central
---

# Managing contracts, subscriptions, and subscription lines

Contracts, subscriptions and subscription lines are required for recurring billing.

[Subscription lines in subscription billing](../masterdata/service-commitments.md) describe the monetary content of agreements with customers and suppliers, as well as termination dates. They can only be created in a [subscription](service-objects.md). The subscription defines the essential information about the end user and the actual content, which is to be billed on a recurring basis.

## Subscription contracts

Subscription contracts organize subscription lines for billing to customers and suppliers. If something is to be invoiced via a separate invoice, this can be set up via a separate contract. Subscription lines have as **Partners** either **Customer** or **Vendor**. Subscription lines with **Customer** go into customer subscription contracts, Subscription lines with **Vendor** go into vendor subscription contracts.

### Overview of the key fields on customer subscription contracts lines and subscription lines

The following table explains key fields on the **Lines** FastTab of the **Customer Subscription Contract** page. The data in customer subscription contracts lines and corresponding subscription lines are always in sync.

|Field|Description|
|---------|---------|
|**Subscription Line Start Date**|Describes the date from which the subscription line is valid and can be invoiced.|
|**Next Billing Date**|Specifies the due date of the next billing. The date is automatically recalculated during the billing proposal. The field isn't available if the line is invoiced to the subscription line end date.|
|**Calculation Base Amount**|Specifies the basis of valuation of the subscription line. When selling an item in conjunction with subscription lines, the **Calculation Base Amount** field shows the value of the item.|
|**Calculation Base %**|Specifies the percentage of the value in the **Calculation Base Amount** field to use to price the subscription line.|
|**Price**| Calculates the price from the **Calculation Base Amount** and the **Calculation Base %**. It's always valid for the entire calculation base amount. For example, it's an annual price if a year is entered in the **Billing Base Period** field and a monthly price if a month is entered.        |
|**Discount %**|Specifies the percentage discount for the subscription line.|
|**Discount Amount**|  Specifies the discount applied to the subscription line.|
|**Amount**|Shows the result of the price, discount, and quantity of the subscription line.|
|**Billing Base Period**|Specifies the period to which the amount applies. For example, enter 1M if the amount refers to one month or 12M if the amount refers to one year.|
|**Billing Rhythm**|Specifies the dateformula that determines how often to invoice the subscription line. The dateformula can be, for example, monthly, quarterly, or yearly.|
|**Subscription Line End Date**|Specifies the date the subscription line ends and can no longer be billed. The date can be entered manually when a subscription line is terminated.|
|**Planned Subscription Lines exist**|Indicates that a [Contract renewal](contract-renewal.md) has happened for this subscription line, but the renewal is not yet valid because the subscription line has not yet been fully invoiced.|
|**Cancellation Possible Until**|Specifies the last date for timely cancellation. The date is determined by the **Initial Term**, the **Subsequent Term**, and the **Cancellation Period**. A 12 month Initial Term with a 3 month notice period means that the due date for termination is 9 months. A Subsequent Term of 12 months postpones the deadline by 12 months when the **Cancellation Possible Until** date is reached.|
|**Invoicing via**|Specifies whether the subscription line is charged recurrently or only stores information about the sale (for example, for warranty extensions). Subscription lines with the **Subscription Contract** option can be called into contracts and billed on a recurring basis.|

The following table explains key fields on other pages related to subscription lines, such as the **Planned Subscription Lines** and **Sales Subscription Lines** pages.

|Field  |Description  |
|---------|---------|
|**Partner**|Specifies whether the subscription lines are meant for in accounts receivable or accounts payable. Accordingly, subscription lines can be added to customer or vendor subscription contracts and invoiced.|
|**Subscription Contract No.**|Specifies the contract through which the subscription lines will be billed.|
|**Initial Term**|Specifies the minimum term of the subscription lines. If the field is filled in and no **Subsequent Term** is entered, the **Subscription Line End Date** is automatically set to the end of the initial term. **Note:** By default, this field is hidden. You might need to personalize the page to add it. To learn more, go to [Personalize your workspace](../../ui-personalization-user.md).|
|**Subsequent Term**|Specifies the duration of the automatic extension after the initial term. It also determine how often to update the **Cancellation Possible Until** and **Term Until** fields. If the field is blank and either the initial term or the notice period are set at the same time, the **Subscription Line End Date** is automatically set to the expiration date of the initial term or the notice period.|

## Invoice discounts

You can grant a flat discount (invoice discount) for the entire contract permanently or for a limited period. This can be used, for example, if the customer changes the license model or if a permanent discount on the subscription line is agreed to.

The discount can only be defined in [Subscription package line templates​](../masterdata/service-commitments.md#subscription-line-templates) and [Subscription package lines​](../masterdata/service-commitments.md#subscription-line-packages). Amounts for subscription packages that allow discounts act as discounts in billing. The process of creating a subscription and billing is identical to the established processes. When creating the billing proposal via [Recurring billing](../recurring-billing.md), billing lines created for contract lines with discounts are created with a negative quantity and therefore a negative amount. The discount amount applies when posting documents.

> [!NOTE]
> A subscription package line in which an invoice discount is defined can only be assigned to subscription items (**Subscription Item** selected as **Subscription Option** on the **Item Card** page).

Invoice discounts are applicable to both customer and vendor subscription contracts. They're also used in credit memos and contract deferrals.

## Related information

[Customer subscription contracts](customer-contracts.md)  
[Vendor subscription contracts](vendor-contracts.md)  
