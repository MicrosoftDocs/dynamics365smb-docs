---
title: General setup
description: There are a few general things to set up for subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
---

# General setup

## Service contract setup

The **Service Contract Setup** page is where settings and defaults for creating and managing customer and vendor Contracts (such as number series) are made.

> [!TIP]
> **Item Templates** contain specific fields so they can be easily predefined for new master data records.

### Inventory picks

If a location requires a dedicated warehouse activity when picking items (**Require Pick**=*Yes* in the Location Card, FastTab *Warehouse*), the item is subsequently delivered via commission. In order to handle the base date for the calculation of the service start differently, the reference date can be specified via **Service Start Date for Warehouse Picking**. It is used when the item is shipped from a commission or warehouse pick. For more information on warehouse and logistics functionalities, go to [Set up locations](../../inventory-how-setup-locations.md).

### Dimensions

The **Autom. Insert Cust. Contr. Dimension Value** field controls whether the customer contract number is automatically created as a new dimension value for each new customer contract. This is then automatically assigned to the respective contract. Dimensions are usually used for evaluation purposes. For details on how dimensions work, go to [Work with dimensions](../../finance-dimensions.md). The default value for this setting is *Yes*.

### Number series

The number series for customer contracts, vendor contracts, and service objects determine which principle is used to assign new numbers. The number series to be used when creating new entries are stored here.

### Invoice details

The selection in the **Origin Name for collective Sales Invoice** field controls which customer information is transferred to *collective invoices*. You can select the contractor (*Sell-to Customer*), the delivery recipient (*Ship-to Address*) or both. In this way, it is possible to control which customer information of the respective contracts is transferred to the collective invoices for several contracts. This is interesting for example in the partner business, if the end customer of the partner is deposited as the delivery recipient in the contract. The partner as the recipient of the invoice can thus easily understand which invoice components refer to which end customer. The field described here is a default that is translated to the **Contractor Name in collective Invoice** and **Recipient Name in collective Invoice** fields (*Invoice Details* fast tab in [Customer Contract](/srb/working-with-contracts/customer-contracts.md#details-for-contract-invoices)) when a new customer contract is created. The fields can be changed there. Decisive for the creation of the invoice are the fields of the respective customer contract.

Whether additional texts, which are created during invoice creation for the contract lines and which description should be used in the invoice line, can be defined in the **Service Contract Setup** page in the **Invoice Details** tab.
The **Description** field represents the description of the invoice line. The **Additional Lines 1 to 5** are created as text lines below the respective invoice line, depending on the configuration.

The following contents can be passed to the invoice:

* Description of the service object
* Description of the service commitments
* Customer reference
* Serial number
* Billing period

> [!CAUTION]
> At least one of the additional lines must be set up to output the *billing period* to prevent this information from being missing in the invoice. If none of the additional lines is set up to output the billing period, the creation of the posting documents will abort with an appropriate error message.

## Sales & Receivables Setup

Explanations about the field **Autom. Insert Project Dimension Value** can be found in [this](/docs/general/essentials/customer-dimension.md) part of the DYCE documentation.

### Bundles

For details on Bundle settings and defaults, please refer to [this](/docs/ebs/setup.md) part of the DYCE documentation.

### Document sending profiles

Via **[Batch Sending Documents](/docs/general/essentials/batch-sending-documents.md)** it is controlled whether the settings defined at the customer are used for batch sending of posted documents or whether the standard dialog is displayed. For the default setting *Use customer's setup* no dialog is displayed.

## General posting setup

The default G/L accounts to be used are set up in the same way as the Business Central standard via [General Posting Setup](../../finance-posting-groups.md) page. The fields **Customer Contract Account**, **Customer Contract Deferral Account**, **Vendor Contract Account** and **Vendor Contract Deferral Account** are available for revenues from customer contracts, costs from vendor contracts and their respective deferrals. The fields are also included in the related **General Posting Setup Card** page. To learn more about how contract deferrals work and are handled, go to [Contract Deferrals](../working-with-contracts/contract-deferrals.md).

## Reports

Along with **Subscription & Recurring Billing**, the **Essentials** app is installed. The app includes, among others, enhancements to the dataset of the following standard reports:

* **Purchase**
    * Purchase Order
    * Blanket Purchase Order
     
* **Sales**
    * Quote
    * Order Confirmation
    * Blanket Sales Order
    * Shipment
    * Invoice (incl. details of Service Commitments invoiced) 
    * Credit Memo
    * Reminder

An additional layout for Word and for RDL is supplied for each report.