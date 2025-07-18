---
title: Sub-Contracting Order Creation
description: Learn how to create and manage subcontracting orders in Business Central for India.
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, subcontracting, order creation, subcontracting order
ms.date: 06/26/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Subcontracting order creation

You can't create a subcontracting order directly and a released production order is required to be created first.

For purchases from registered vendors for services attracting reverse charge, purchasers are required to pay the GST tax, to the Government. If exempted goods and services are purchased from registered vendor, then no GST is to be paid to supplier or to the Government.

## Create a released production order

For a Subcontracting order, it's required to create the **Released Production Order** with **Subcontracting location**.

## Run subcontracting worksheet

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Subcontracting worksheet**, and then choose the related link.
1. Select **Process Actions** -> **Functions** -> **Calculate Subcontract**. System copies the selected released production orders to the subcontracting worksheet.
1. Select **Action** -> **Function** and then select **Carry out action message**.
1. Select **Ok** in the carry out action message window to automatically create the **Subcontracting Order**.

> [!NOTE]
> - Program deletes the lines from the subcontracting worksheet after creating the Subcontracting Order.
> - Program also updates the subcontracting order no. along with the subcontractor code on the Released Prod. Order line.

## Material issue or sending raw material to subcontractor

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Subcontracting Order**, and then choose the related link.
1. In the **Subcontracting Order** list window, select the **Subcontracting Order**.
1. Select **Action** and then select **Edit** to open the subcontracting order.
1. Select **Line** -> **Order Subcon details**  and then select on **Send**.
1. In **Ord. Subcon Details Delv.** List, select the **Ord. Subcon Details Delv**.
1. Select **Manage** and then select **Edit** to open **Order Subcon Details Delivery**.
1. On the General Tab, enter the **Quantity** of finished item for which you want to send the raw item to your subcontracting vendor in **Deliver Comp. For** field.
1. Enter the date on which you want to physically send the raw item to your subcontracting vendor in **Delivery Challan Date** field.
1. Program automatically updates the **Quantity to Send** field on the Sub Order Component line. You can also edit the quantity as per the physical transfer of material.
1. Select **Send** to transfer the raw item from company location to subcontracting location.

 Program updates the **Total Qty at Vendor Location** and **Qty. at Vendor Location** field on the Sub Order Components line. Program also updates the **Delivery Challan Posted** field on the General FastTab.

## Receiving material from subcontractor

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Subcontracting Order**, and then choose the related link.
1. In the **Subcontracting Order** list window, select the **Subcontracting order**.
1. Select **Action** and then select **Edit** to open the subcontracting order.
1. Select **Line** and then select **Order Subcon details**.
1. On the **Order Subcon Details**, select **Receive**.
1. On the **Ord. Subcon Details Rcpt.** List window, select the Ord. Subcon Details Rcpt.
1. Select **Manage** and then select **Edit** to open Order Subcon Details Receipt.
1. On the General FastTab, enter the **Shipment No.** as per the documents received from the subcontracting vendor in **Vendor Shipment No.** field.
1. Enter the **Quantity** of finished item, which you received physically from your subcontracting vendor in **Qty. to Accept** field.
1. Enter the **Posting Date** on which you have received the finished item.
1. Program automatically updates the **Quantity to Consume** field on the **Sub Order Comp. List** Vend line.
1. Select on the **Line** and then select on **Apply Delivery Challan**.
1. On the **Apply Delivery Challan**, select **Apply Delivery Challan No.** and enter value in the **Qty to Consume**.
1. Select ok to close the Apply Delivery Challan.
1. Select **Receive** to receive the finish item.
1. Select **Yes** to post the receipt.

Program updates the **Qty. Consumed** and **Quantity at Vendor Location** field on the Sub Order Comp. lines. Program also updates the **Quantity Received** field in the general tab.

## Related information

[Create GST Liability](Subcontracting-Create-GST-Liability.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
