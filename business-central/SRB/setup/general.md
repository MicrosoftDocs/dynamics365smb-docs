---
title: General setup
description: There are a few general things to set up for subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: install-set-up-deploy
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
---

# General setup

## Service contract setup

Use the **Service Contract Setup** page to enter settings and defaults for creating and managing customer and vendor contracts. For example, use the page to specify the default number series.

<!--### Inventory picks

If a location requires a dedicated warehouse activity when picking items (**Require Pick**=*Yes* in the Location Card, FastTab *Warehouse*), the item is subsequently delivered via commission. In order to handle the base date for the calculation of the service start differently, the reference date can be specified via **Service Start Date for Warehouse Picking**. It is used when the item is shipped from a commission or warehouse pick. For more information on warehouse and logistics functionalities, go to [Set up locations](../../inventory-how-setup-locations.md). -->

### General

The **Default Period Calculation​** determines which period calculation option is set on a service commitment package line. To learn more about the **Align to Start of Month** and **Align to End of Month** options, go to [Managing contracts, service objects, and services commitments](../working-with-contracts/contracts-services-mgmt.md). By changing the default, the value updates in all existing service commitments, sales service commitments, and service commitment package lines. If the existing records aren't updated, the period calculation isn't changed. Only the default value for creating new service commitment package lines changes.

You can set a date formula in the **Overdue Date Formula** field that filters for overdue service commitments in the **Service Commitments - Overdue** cue in the **Subscription & Recurring Billing** Role Center. For example, you can enter **3D** if you want the cue to count a service commitment as overdue if the service commitment's next billing date is three or more days past the work date. If you leave the field blank, the cue doesn't show anything.

If a location requires a dedicated warehouse activity when picking items (The **Require Pick** toggle is turned on on the **Location Card** page on the **Warehouse** FastTab), the item is subsequently delivered via commission. To handle the base date for the calculation of the service start differently, the reference date can be specified via the **Service Start Date for Warehouse Picking**. It is used when the item is shipped from a commission or warehouse pick. To learn more about warehouse and logistics features, go to [Set up locations](../../inventory-how-setup-locations.md).

### Dimensions

The **Autom. Insert Cust. Contr. Dimension Value** field controls whether the customer contract number is automatically created as a new dimension value for each new customer contract. The number is then automatically assigned to the contract. The default value for this setting is **Yes**.

Dimensions are usually used for analysis or reporting purposes. To learn more about how dimensions work, go to [Work with dimensions](../../finance-dimensions.md).

### Number series

The number series for customer contracts, vendor contracts, and service objects determine which number series are used to set default numbers when creating new entities.

### Invoice details

The selection in the **Origin Name for Collective Sales Invoice** field controls which customer information you transfer to collective invoices for several contracts. You can select:

* The contractor (Sell-to Customer)
* The delivery recipient (Ship-to Address)
* Both

For example, this is interesting in the partner business if the end customer of the partner is deposited as the delivery recipient in the contract. The partner as the recipient of the invoice can thus easily understand which invoice components refer to which end customer.

The **Origin Name for Collective Sales Invoice** field is a default that is translated to the contractor name on the collective invoice and the recipient name in collective invoice fields when you create a new customer contract. To learn more, go to [Details for contract invoices](../working-with-contracts/customer-contracts.md#details-for-contract-invoices). The fields can be changed there. The fields on the customer contract determine how the invoice is created.

You can also specify whether additional texts that are added for contract lines when you create invoices. Their descriptions are used in the invoice line. You set up additional texts on the **Service Contract Setup** page, on the **Invoice Details** FastTab. The **Additional Lines 1 to 5** are created as text lines below the respective invoice line, depending on the configuration. The following contents can be passed to the invoice:

* Description of the service object
* Description of the service commitments
* Customer reference
* Serial number
* Billing period

> [!NOTE]
> You must set up at least one of the additional lines to output the billing period to include this information in the invoice. If you don't, you can't create posting documents and an error message displays.

## Item templates

Item templates contain the **Service Commitment Option** and **Service Commitment Packages** so they're predefined for new records.

## General posting setup

You set up the default G/L accounts to use in the same way as the [!INCLUDE [prod_short](../../includes/prod_short.md)] standard on the **General Posting Setup** page. The **Customer Contract Account**, **Customer Contract Deferral Account**, **Vendor Contract Account** and **Vendor Contract Deferral Account** are available for revenues from customer contracts, costs from vendor contracts and their respective deferrals. The fields are also included on the related **General Posting Setup** page. To learn more about how contract deferrals work, go to [Contract Deferrals](../working-with-contracts/contract-deferrals.md).

The default G/L accounts to be used are set up in the same way as the Business Central standard via [General Posting Setup](../../finance-posting-groups.md) page. The fields **Customer Contract Account**, **Customer Contract Deferral Account**, **Vendor Contract Account** and **Vendor Contract Deferral Account** are available for revenues from customer contracts, costs from vendor contracts and their respective deferrals. The fields are also included in the related **General Posting Setup Card** page. To learn more about how contract deferrals work and are handled, go to [Contract Deferrals](../working-with-contracts/contract-deferrals.md).

## Reports

Along with **Subscription & Recurring Billing**, the **Essentials** app is installed. The app includes, among others, enhancements to the dataset of the following standard reports:

* Purchase
   * Purchase Order
   * Blanket Purchase Order
  
* Sales
   * Quote
   * Order Confirmation
   * Blanket Sales Order
   * Shipment
   * Invoice (including details of service commitments invoiced)
   * Credit Memo
   * Reminder

An additional layout for Word and for RDL is supplied for each report.

## Related information

[Contract types](contract-types.md)
