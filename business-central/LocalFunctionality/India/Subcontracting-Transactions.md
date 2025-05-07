---
title: Sub-Contracting Order Creation
description: Sub-Contracting Order Creation

    
author: v-debapd

    
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Subcontracting Order Creation


You cannot create a subcontracting order directly and a released production order is required to be created first.

For purchases from registered vendors for services attracting reverse charge, purchasers are required to pay the GST tax, to the Government.
If exempted goods and services are purchased from registered vendor, then no GST is to be paid to supplier or to the Government.


## Create a released production order

For a Subcontracting order, it is required to create the **Released Production Order** with **Subcontracting location**.

## Run subcontracting worksheet

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Subcontracting worksheet**, and then choose the related link. 
2. Click on Process **Actions** -> **Functions** -> **Calculate Subcontract**. System will copy the selected released production orders to the subcontracting worksheet.

4. Click **Action** -> **Function** and then click **Carry out action message**.
5. Click Ok in the carry out action message window to automatically create the **Subcontracting Order**.

> [!NOTE]
> - Program will delete the lines from the subcontracting worksheet after creating the Subcontracting Order.
> - Program will also update the subcontracting order no. along with the subcontractor code on the Released Prod. Order line.

## Material issue or sending raw material to subcontractor

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Subcontracting Order**, and then choose the related link. 
2. In the **Subcontracting Order** list window, select the **Subcontracting Order**.
3. Click **Action** and then click **Edit** to open the subcontracting order.
4. Click on **Line** -> **Order Subcon details**  and then click on **Send**.
5. In **Ord. Subcon Details Delv.** List, select the **Ord. Subcon Details Delv**.
6. Click **Manage** and then click **Edit** to open **Order Subcon Details Delivery**.
7. On the General Tab, enter the **Quantity** of finished item for which you want to send the raw item to your subcontracting vendor in **Deliver Comp. For** field.
8. Enter the date on which you want to physically send the raw item to your subcontracting vendor in **Delivery Challan Date** field.
9. Program will automatically update the **Quantity to Send** field on the Sub Order Component line. You can also edit the quantity as per the physical transfer of material.
10. Click **Send** to transfer the raw item from company location to subcontracting location.

 Program will update the **Total Qty at Vendor Location** and **Qty. at Vendor Location** field on the Sub Order Components line. Program will also update the **Delivery Challan Posted** field on the General FastTab.


## Receiving material from subcontractor

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Subcontracting Order**, and then choose the related link. 
2. In the **Subcontracting Order** list window, select the **Subcontracting order**.
3. Click **Action** and then click **Edit** to open the subcontracting order.
4. Click on **Line** and then select **Order Subcon details**.
5. On the **Order Subcon Details**, click **Receive**.
6. On the **Ord. Subcon Details Rcpt.** List window, select the Ord. Subcon Details Rcpt.
7. Click **Manage** and then click **Edit** to open Order Subcon Details Receipt.
8. On the General FastTab, enter the **Shipment No.** as per the documents received from the subcontracting vendor in **Vendor Shipment No.** field.
9. Enter the **Quantity** of finished item which you received physically from your subcontracting vendor in **Qty. to Accept** field.
10. Enter the **Posting Date** on which you have received the finished item.
11. Program will automatically update the **Quantity to Consume** field on the **Sub Order Comp. List** Vend line.
12. Click on the **Line** and then click on **Apply Delivery Challan**.
13. On the **Apply Deleivery Challan**, select **Apply Delivery Challan No.** and enter value in the **Qty to Consume**.
14. Click ok to close the Apply Delivery Challan.
15. Click **Receive** to receive the finish item.
16. Click **Yes** to post the receipt.

Program will update the **Qty. Consumed** and **Quantity at Vendor Location** field on the Sub Order Comp. lines. Program will also update the **Quantity Received** field in the general tab.





## Related information 
[Create GST Liability](Subcontracting-Create-GST-Liability.md)






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
