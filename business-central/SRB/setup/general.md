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

# General Setup
## Service Contract Setup
The **Service Contract Setup** page is where settings and defaults for creating and managing Customer and Vendor Contracts (such as number series) are made.

:::tip Item Template
The **Item Templates** contain DYCE-specific fields so they can be easily predefined for new master data records.
:::


### Inventory Picks
If a location requires a dedicated warehouse activity when picking items (**Require Pick**=*Yes* in the Location Card, fast tab *Warehouse*), the item is subsequently delivered via commission. In order to handle the base date for the calculation of the service start differently, the reference date can be specified via **Service Start Date for Warehouse Picking**. It is used when the item is shipped from a commission or warehouse pick. For more information on warehouse and logistics functionalities, please refer to <a href="https://learn.microsoft.com/en-us/dynamics365/business-central/inventory-how-setup-locations" title="Set Up Locations">this part</a> of the Microsoft documentation.


### Dimensions
The **Autom. Insert Cust. Contr. Dimension Value** field controls whether the Customer Contract No. is automatically created as a new dimension value for each new customer contract. This is then automatically assigned to the respective contract. Dimensions are usually used for evaluation purposes. For details on how dimensions work, please refer to <a href="https://learn.microsoft.com/en-us/dynamics365/business-central/finance-dimensions" title="Working with Dimensions">this part</a> of the Microsoft documentation. The default value for this setting is *Yes*.


### No. Series
The Number Series for Customer Contracts, Vendor Contracts, and Service Objects determine which principle is used to assign new numbers. The number series to be used when creating new entries are stored here.


### Invoice Details
The selection in the **Origin Name for collective Sales Invoice** field controls which customer information is transferred to *collective invoices*. You can select the contractor (*Sell-to Customer*), the delivery recipient (*Ship-to Address*) or both. In this way, it is possible to control which customer information of the respective contracts is transferred to the collective invoices for several contracts. This is interesting for example in the partner business, if the end customer of the partner is deposited as the delivery recipient in the contract. The partner as the recipient of the invoice can thus easily understand which invoice components refer to which end customer. The field described here is a default that is translated to the **Contractor Name in collective Invoice** and **Recipient Name in collective Invoice** fields (*Invoice Details* fast tab in [Customer Contract](/srb/working-with-contracts/customer-contracts.md#details-for-contract-invoices)) when a new Customer Contract is created. The fields can be changed there. Decisive for the creation of the invoice are the fields of the respective Customer Contract.

Whether additional texts, which are created during invoice creation for the contract lines and which description should be used in the invoice line, can be defined in the **Service Contract Setup** page in the **Invoice Details** tab.
The **Description** field represents the description of the invoice line. The **Additional Lines 1 to 5** are created as text lines below the respective invoice line, depending on the configuration.
The following contents can be passed to the invoice:
* Description of the Service Object.
* Description of the Service Commitments
* Customer reference
* Serial number
* Billing period


:::caution Billing period
At least one of the additional lines must be set up to output the *billing period* to prevent this information from being missing in the invoice. If none of the additional lines is set up to output the billing period, the creation of the posting documents will abort with an appropriate error message.
:::


## Sales & Receivables Setup
Explanations about the field **Autom. Insert Project Dimension Value** can be found in [this](/docs/general/essentials/customer-dimension.md) part of the DYCE documentation.


### Bundles
For details on Bundle settings and defaults, please refer to [this](/docs/ebs/setup.md) part of the DYCE documentation.


### Document Sending Profiles
Via **[Batch Sending Documents](/docs/general/essentials/batch-sending-documents.md)** it is controlled whether the settings defined at the customer are used for batch sending of posted documents or whether the standard dialog is displayed. For the default setting *Use customer's setup* no dialog is displayed.


## General Posting Setup
The default G/L accounts to be used are set up in the same way as the Business Central standard via the <a href="https://learn.microsoft.com/en-us/dynamics365/business-central/finance-posting-groups" title="Set Up Posting Groups">General Posting Setup</a> page. The fields **Customer Contract Account**, **Customer Contract Deferral Account**, **Vendor Contract Account** and **Vendor Contract Deferral Account** are available for revenues from Customer Contracts, costs from Vendor Contracts and their respective deferrals. The fields are also included in the related **General Posting Setup Card** page. For more details on how Contract Deferrals work and are handled, please see [here](/docs/srb/working-with-contracts/contract-deferrals.md).


## Reports
Along with **DYCE Subscription & Recurring Billing**, the **DYCE Essentials** app is installed. The app includes, among others, enhancements to the dataset of the following standard reports:
* **Purchase** <br/>
    * Purchase Order<br/>
    * Blanket Purchase Order <br/>
     
* **Sales** <br/>
    * Quote <br/>
    * Order Confirmation <br/>
    * Blanket Sales Order <br/>
    * Shipment <br/>
    * Invoice (incl. details of Service Commitments invoiced) <br/>
    * Credit Memo <br/>
    * Reminder <br/>

Furthermore, an additional DYCE layout for WORD and for RDL is supplied for each report.