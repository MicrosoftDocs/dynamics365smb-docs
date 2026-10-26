---
title: Set Up Subcontracting for India
description: Set up subcontracting locations, vendors, items, return periods, and GST liability posting accounts in the India localization of Business Central.
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, subcontracting, subcontracting orders, job work, source code, routing, work center
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up subcontracting for India

Business Central has included **Subcontracting** Feature to Indian Localization.

Subcontracting process is common in manufacturing organizations. Organizations adopt the job work process due to their capacity constraints, lack of resources or due to machine breakdowns. In Subcontracting, a delivery challan is used to send the raw items to the subcontractor from the company. With some value addition by the subcontractor, the finished items are sent back to the company.

While receiving the finished items in the company against a subcontracting order, it's mandatory to apply received material against the delivery challan to knock off the raw items at subcontractor end.

As far as the costing of finished item is concerned, it consists of raw material cost, subcontracting cost along with the other charges such as freight etc.

For taxable components subject to a job work return period, the functionality supports creating GST liability for overdue delivery challans and adjusting it when materials are received. Configure the return period and tax treatment for your applicable requirements. Liability creation is a separate action, not an automatic result of the period expiring.

## Multiple subcontracting orders

Subcontracting feature also enables you to send the raw items to subcontracting vendor for multiple subcontracting orders against a single Delivery Challan. Delivery Challan shows the details of all subcontracting orders for which the raw material components have been sent to subcontracting vendor.

## Stock register for job work

Stock register for job work gives the details of delivery challan sent to the subcontractor. This register shows all the transaction against a delivery challan and at any movement it also shows the status of delivery challan along with GST liability if any.

## Subcontracting setup

Following setups are required for Subcontracting:

- [Subcontracting Location setup](subcontracting-001-basic-setup.md#subcontracting-location-setup)
- [Subcontracting Vendor setup](subcontracting-001-basic-setup.md#set-up-subcontracting-vendor)
- [Subcontracting Item setup](subcontracting-001-basic-setup.md#set-up-subcontracting-item)
- [Job Work Return Period](subcontracting-001-basic-setup.md#set-up-job-work-return-period)
- [Source Code Setup](subcontracting-001-basic-setup.md#set-up-source-code)
- [General Ledger Setup](subcontracting-001-basic-setup.md#set-up-general-ledger-setup)
- [Work Center](subcontracting-001-basic-setup.md#set-up-work-center)
- [Routing](subcontracting-001-basic-setup.md#set-up-routing)
- [GST liability no series setup](subcontracting-001-basic-setup.md#gst-liability-no-series-setup)

## Subcontracting location setup

You need to create a setup for subcontracting location. Raw item needs to be transferred from company location to subcontracting location.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Locations**, and then choose the related link.
1. On the **Tax Information** FastTab, enable the boolean in the **Subcontracting Location** field to make this location as a **Subcontracting Location**.

## Set up subcontracting vendor

You need to set up a vendor as a subcontractor. Same vendor can be the prime vendor and a subcontracting vendor. Each subcontracting vendor needs to be attached with the subcontracting location.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Vendors**, and then choose the related link.
1. On the **Tax Information** FastTab, enable the boolean in the **Subcontractor** field to make this vendor as a **Subcontractor**.
1. Select the subcontracting location by clicking on **Vendor Location** look up field. 
1. Enter **Commissioner's Permission No.** if required for your process. This value is copied to the delivery challan.

## Set up subcontracting item

The finished item needs to be identified as a subcontracting item.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Items**, and then choose the related link.
1. On the **Cost & Posting** FastTab, enable the boolean in the **Subcontracting** field to make this Item as a subcontracting item.
1. Select the subcontracting location by clicking on **Sub. Comp. Location** look up field. This is the location from where you send the raw material to the subcontractor.

## Set up job work return period

Set the return period used to calculate the last return date on delivery challan lines. Review overdue eligible lines on **Create GST Liability**.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Inventory Setup**, and then choose the related link.
1. On the **Numbering** FastTab, enter the return period for which you want to create GST liability in the **Job Work Return Period** field.
1. Select the **Sub. Component Location** from lookup list. This sub component location is used to transfer the raw items to the subcontracting location through delivery challan.

## Set up source code

As per statutory requirement, you need to define the source code in the source code setup window. This source code is mandatory if subcontractor doesn't Return the item within job work Return period, then to create the GST liability. Source code is also required if any subcontracting item is received after the job work Return period.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Source Code Setup**, and then choose the related link.
1. On the **General** FastTab, select Source code in the **GST Receipt – Job Work** field. 
1. Select Source code in the **GST Liability – Job Work** field.

## Set up general ledger setup

Set up the interim account used when posting subcontracting GST liability.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **General Ledger Setup**, and then choose the related link.
1. On the **Tax Information** FastTab, specify **Sub-Con Interim Account**. Liability posting requires this account.

## Set up work center

You need to set up the work center for the subcontracting vendor. On the work center, you can also set up the unit cost of job work.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Work Centers**, and then choose the related link.
1. On the Posting tab, select **subcontracting vendor** in the **Subcontractor No.** field.

## Set up routing

You need to create a Routing for finished item. Routing defines the sequence of the operations required to manufacture the finished item.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Routings**, and then choose the related link.
1. On the Lines tab, select **subcontracting work center no.** in the **Work Center No.** field. 
1. On the  Lines tab, enter the job work charges in the **Unit Cost Per** field.

## GST liability no series setup

No. series for GST liability invoice is set up on location master. You can define location wise number series for GST liability invoices.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Locations**, and then choose the related link.
1. On the **Tax Information** FastTab, select the number series in **GST Liability Invoice**.

## Related information

[Subcontracting Transactions](Subcontracting-Transactions.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
