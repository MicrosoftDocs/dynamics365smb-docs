---
title: Charge group assignment functionality
description: Discover the enhanced charge group assignment functionality in Business Central India localization. Simplify charge distribution for purchase orders efficiently.
author: v-vnigam
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, charge group
ms.date: 11/05/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Charge group assignment functionality

The charge assignment functionality streamlines assigning charges to items in Business Central. Previously, users manually selected and assigned charges to each item, which was cumbersome for orders with many items. Based on customer feedback, an enhancement now allows automatic charge assignment, making the process more efficient and user-friendly.

## Setup steps

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or    Report icon") icon, enter **Charge Groups**, and then choose the related link.
2. Select **New** to configure a charge group on the **Charge Groups** page.
3. Define the fields on the **Charge Group Card** page. The following fields are important:
   - **Computation Method**: Determines how charges are calculated.
       - *Fixed Value*: A set amount per order.
       - *Percentage*: A percentage of each line’s amount.
       - *Amount for Quantity*: A fixed amount per item quantity at the line level, calculated by multiplying line quantity by the charge amount.
   - **Assignment Method**: Determines how charges are assigned to items at the line level.
       - *Equally*: Charges are distributed equally to all the items or lines in the order.
       - *By Amount*: Charges are distributed in proportion of line values for all lines in the order.
       - *By Weight*: Charges are distributed in proportion of weight of items of all lines in the order.
       - *By Volume*: Charges are distributed in proportion of Volume of items of all lines in the order.
   - **Third Party Invoice**: If this checkbox is selected, the charge is provided by a third party vendor. You must specify the third party vendor and G/L code, and a separate invoice will be created for this line.
   - **Invoice Combination**: This field provides you with two options:
       - *Combine*: If you don’t want separate invoices to be posted for each G/L account associated with the third party vendor, then select this option. When this option is chosen, only two invoices are created: one standard posted purchase invoice for the main vendor, and another invoice for the third party vendor, which includes multiple lines for the different G/L accounts present on the line header.
       - *Separate*: Posts individual invoices for each GL account linked to the third party vendor; otherwise, it creates the invoice based on other settings but doesn’t post it.
       - *Post Third Party Invoice*: If enabled, the system automatically posts the third party invoice.

   > [!NOTE]
   > The **GST Group Code**, **HSN/SAC Code**, and **GST Credit** (Availment/Non-Availment) must be defined on the **Item Charge** card. GST is calculated per charge item.
   ![Explode Charge Group](image/explode_charge_group.png)
4. Apply charges in transactions by performing the following steps:
5. Create a purchase or sales invoice/order and apply charges in the line. In the **Tax Information** panel, define the charge group code and select that code.
6. On the **Lines** section, select **Line** > **Functions** > **Explode Charge Group**.
   ![Explode Charge Group](image/explode_charge_group.png)
   This action automatically creates lines for charges and assigns them as configured.
   ![Explode Charge Group](image/explode_charge_group.png)

## Third- arty invoice setup

If a third party invoice is required, perform the following steps:

1. Select the **Third Party Invoice** checkbox on the **Charge Group Card** page.
   > [!NOTE]
   > When this checkbox is selected and the user posts the invoice or order, two invoices are generated—a standard posted purchase invoice for the main vendor and another one for the third party.
2. Define the third party **Vendor No.** and **G/L Account Number**.
3. Apply the **Charge Group Code** in the **Tax Information** panel that is set up for the third party.
4. Create the purchase order/invoice as outlined in Step 4 of the **Setup Steps** section.
5. On the **Lines** section, navigate to **Line** > **Functions** > **Explode Charge Group**.
6. Post the purchase order or invoice. This action posts two invoices: one for the main vendor and one for the third party vendor.

> [!NOTE]
> GST isn't calculated for third-party invoices.
> To include GL accounts automatically in the lines when exploding the charge group, select the **G/L Account** option in the **Type** field instead of **Charge (Item)** on the **Charge Group Card** page.
