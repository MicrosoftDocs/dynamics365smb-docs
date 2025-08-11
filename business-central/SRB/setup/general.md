---
title: General setup
description: There are a few general things to set up for subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: install-set-up-deploy
ms.search.keywords: 
ms.search.form: 8059, 8054, 8051_Primary
ms.date: 07/11/2025
ms.service: dynamics-365-business-central
---

# General setup

## Subscription contract setup

Use the **Subscription Contract Setup** page to enter settings and defaults for creating and managing customer and vendor subscription contracts. For example, use the page to specify the default number series and invoice details.

### General

If a location requires a dedicated warehouse activity when picking items (The **Require Pick** toggle is turned on on the **Location Card** page on the **Warehouse** FastTab), the item is subsequently delivered via commission. To handle the base date for the calculation of the service start differently, the reference date can be specified via the **Service Start Date for Warehouse Picking**. It is used when the item is shipped from a commission or warehouse pick. To learn more about warehouse and logistics features, go to [Set up locations](../../inventory-how-setup-locations.md).

You can set a date formula in the **Overdue Date Formula** field that filters for overdue subscription lines in the **Subscription lines - Overdue** cue in the **Subscription Billing** Role Center. For example, you can enter **3D** if you want the cue to count a subscription line as overdue if the subscription line's next billing date is three or more days past the work date. If you leave the field blank, the cue doesn't show anything.

The **Default Period Calculation​** determines which period calculation option is set on a subscription package line. To learn more about the **Align to Start of Month** and **Align to End of Month** options, go to [Managing contracts, subscriptions, and subscription lines](../working-with-contracts/contracts-services-mgmt.md). By changing the default, the value updates in all existing subscription lines commitments, sales subscription lines, and subscription package lines. If the existing records aren't updated, the period calculation isn't changed. Only the default value for creating new subscription package lines changes.

**Default Billing Base Period** and **Default Billing Rhythm** are used and applied when contract lines are created manually by the user. Since these values need to be specified per contract line, this setup ensures that the fields are populated properly.

Use **Create Contract Deferrals** to specify the default for new customer and vendor subscription contracts. It is also used when creating new contract types.

### Dimensions

The **Autom. Insert Cust. Contr. Dimension Value** field controls whether the customer subscription contract number is automatically created as a new dimension value for each new customer subscription contract. The number is then automatically assigned to the contract. The default value for this setting is **No**.

Dimensions are usually used for analysis or reporting purposes. To learn more about how dimensions work, go to [Work with dimensions](../../finance-dimensions.md).

### Number series

The number series for customer subscription contracts, vendor subscription contracts, and subscriptions determine which number series are used to set default numbers when creating new entities.

### Invoice details

The selection in the **Origin Name for Collective Sales Invoice** field controls which customer information you transfer to collective invoices for several contracts. You can select:

* The contractor (Sell-to Customer)
* The delivery recipient (Ship-to Address)
* Both

For example, this could be useful for a partner business if the end customer is listed as the delivery recipient in the contract. The partner as the recipient of the invoice can thus easily understand which invoice components refer to which end customer.

The **Origin Name for Collective Sales Invoice** field is a default that is transferred to the contractor name on the collective invoice and the recipient name in collective invoice fields when you create a new customer subscription contract. To learn more, go to [Details for contract invoices](../working-with-contracts/customer-contracts.md#details-for-contract-invoices). The fields can be changed there. The fields on the customer subscription contract determine how the invoice is created.

You can also specify how texts from contract lines and subscriptions are handles when you create invoices. The selection in the **Description** field is used as the description of the invoice line. Additionally, you can set up additional texts to be used. The **Additional Lines 1 to 5** are created as text lines below the respective invoice line, depending on the configuration. The following contents can be passed to the invoice:

* Description of the subscription
* Description of the subscription lines
* Customer reference
* Serial number
* Billing period

> [!NOTE]
> You must set up at least one of the additional lines to output the billing period to include this information in the invoice. If you don't, you can't create posting documents and an error message displays.

## Item templates

Item templates contain the **Subscription Option** and **Subscription Packages** so they're predefined for new records.

## General posting setup

You set up the default G/L accounts to use in the same way as the [!INCLUDE [prod_short](../../includes/prod_short.md)] standard on the **General Posting Setup** page. The **Customer Subscription Contract Account**, **Customer Subscription Contract Deferral Account**, **Vendor Subscription Contract Account** and **Vendor Subscription Contract Deferral Account** are available for revenues from customer subscription contracts, costs from vendor subscription contracts and their respective deferrals. The fields are included on the **General Posting Setup** page. To learn more about how contract deferrals work, go to [Contract Deferrals](../working-with-contracts/contract-deferrals.md).

## Report layouts

**Subscription Billing** includes additional layouts (both Word and RDLC) for the following reports to support included features:

* Sales - Quote
* Sales - Confirmation
* Sales - Invoice

## Related information

[Subscription contract types](contract-types.md)
