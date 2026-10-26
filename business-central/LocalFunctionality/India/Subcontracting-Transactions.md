---
title: Subcontracting Order Creation
description: Create subcontracting orders, send components with delivery challans, and apply challans when receiving finished items in Business Central for India.
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, subcontracting, order creation, subcontracting order
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Subcontracting order creation

You can't create a subcontracting order directly and a released production order is required to be created first.

For purchases of services configured for reverse charge, review the GST setup on the subcontracting transaction. Exemption and reverse-charge treatment depend on the applicable tax configuration and requirements.

## Create a released production order

For a Subcontracting order, it's required to create the **Released Production Order** with **Subcontracting location**.

## Run subcontracting worksheet

The following steps describe the legacy subcontracting worksheet workflow. The base **Subcontracting Worksheet** page is marked obsolete from version 28 and identifies the Subcontracting app as its replacement. Confirm the worksheet available in your installed version before following these steps.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Subcontracting Worksheet**, and then choose the related link.
1. Choose **Functions** > **Calculate Subcontracts**, and set the filters for the released production orders.
1. Choose **Carry Out Action Message**.
1. Choose **OK** to create the subcontracting orders.

> [!NOTE]
> - Program deletes the lines from the subcontracting worksheet after creating the Subcontracting Order.
> - Program also updates the subcontracting order no. along with the subcontractor code on the Released Prod. Order line.

## Material issue or sending raw material to subcontractor

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Subcontracting Orders**, and then choose the related link.
1. In the **Subcontracting Order** list window, select the **Subcontracting Order**.
1. Select **Action** and then select **Edit** to open the subcontracting order.
1. Choose **Line** > **Order Subcon. Details** > **Send**.
1. In **Ord. Subcon Details Delv.** List, select the **Ord. Subcon Details Delv**.
1. Select **Manage** and then select **Edit** to open **Order Subcon Details Delivery**.
1. On the General Tab, enter the **Quantity** of finished item for which you want to send the raw item to your subcontracting vendor in **Deliver Comp. For** field.
1. Enter the date on which you want to physically send the raw item to your subcontracting vendor in **Delivery Challan Date** field.
1. Program automatically updates the **Quantity to Send** field on the Sub Order Component line. You can also edit the quantity as per the physical transfer of material.
1. Select **Send** to transfer the raw item from company location to subcontracting location.

 Program updates the **Total Qty at Vendor Location** and **Qty. at Vendor Location** field on the Sub Order Components line. Program also updates the **Delivery Challan Posted** field on the General FastTab.

## Receive material from a subcontractor

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Subcontracting Orders**, and then choose the related link.
1. Open the relevant order.
1. Choose **Line** > **Order Subcon. Details** > **Receipt**.
1. Select the receipt line, and choose **Edit** to open **Order Subcon Details Receipt**.
1. On the **General** FastTab, enter **Vendor Shipment No.**, **Qty. to Accept**, and **Posting Date**.
1. Review **Qty. to Consume** on the component lines.
1. For each component, choose **Apply Delivery Challan**.
1. On **Applied Delivery Challan**, select **Applied Delivery Challan No.** and enter **Qty. to Consume**.
1. Close **Applied Delivery Challan**.
1. Choose **Receive**, and confirm the posting.

The applied delivery challan quantities must match the component quantities being consumed or returned. Posting checks for missing challan applications.

Program updates the **Qty. Consumed** and **Quantity at Vendor Location** field on the Sub Order Comp. lines. Program also updates the **Quantity Received** field in the general tab.

## Related information

[Create GST Liability](Subcontracting-Create-GST-Liability.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
