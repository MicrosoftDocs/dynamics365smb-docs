---
title: Charge Assignment Functionality
description: Discover the enhanced charge group assignment functionality in Business Central India localization. Simplify charge distribution for purchase orders efficiently.
author: v-vnigam
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, charge group
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Charge assignment functionality

The charge assignment functionality streamlines assigning charges to items in Business Central. Configure reusable charge groups, then use **Explode Charge Group** to create charge lines and assign item charges on purchase or sales documents.

## Setup steps

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Charge Groups**, and then choose the related link.
1. Select **New** to configure a charge group.
1. Enter a **Code** and **Name** on the **Charge Group Card** page.
1. Add lines with a **Type** of **Charge (Item)** or **G/L Account**, and select the **No.** The following fields are important:
   - **Computation Method**: Determines how charges are calculated. It has three options:
       - **Fixed Value**: Uses the **Value** as the charge amount.
       - **Percentage**: Multiplies the total item line amount by the **Value** percentage.
       - **Amount Per Quantity**: Multiplies the total item quantity by the **Value**.
   - **Assignment**: Determines how item charges are assigned. Choose **Equally**, **By Amount**, **By Weight**, or **By Volume**.

The following settings control third-party purchase invoices:

- **Third Party Invoice**: Select this field on a **G/L Account** charge group line, and specify **Vendor No.** and **G/L Account No.** It isn't available for **Charge (Item)** lines.
- **Invoice Combination**: Set this field on the charge group header before enabling third-party lines.
  - **Combine Invoice**: Creates one purchase invoice per third-party vendor, with multiple lines when that vendor has multiple charges.
  - **Seperate Invoice**: Creates a separate purchase invoice for each third-party charge group line. This spelling is the option caption.
- **Post Third Party Inv.**: Controls whether the third-party invoices are automatically posted when the main purchase document is invoiced. Otherwise, the invoices are created but remain unposted.

> [!NOTE]
> Configure the applicable **GST Group Code**, **HSN/SAC Code**, and **GST Credit** on the item charge for purchase item charges. Tax calculation depends on the transaction and tax configuration.

## Apply a charge group

1. Create a purchase or sales order or invoice, and enter the item lines.
1. Select the **Charge Group Code** on the document header.
1. In **Lines**, choose **Line** > **Functions** > **Explode Charge Group**. This action creates charge lines and assigns item charges as configured.

If item quantities or values change, explode the charge group again before invoicing. Posting checks whether the charge lines still match the calculated charges.

## Third-party invoice setup

If a third party invoice is required, perform the following steps:

1. On the **Charge Group Card**, select **Invoice Combination** and decide whether to enable **Post Third Party Inv.**
1. On each applicable **G/L Account** line, select **Third Party Invoice**.
1. Specify the third-party **Vendor No.** and **G/L Account No.**
1. Apply and explode the charge group on a purchase order or invoice as described in [Apply a charge group](#apply-a-charge-group).
1. Invoice the purchase document. Third-party purchase invoices are created according to the combination setting and posted only if **Post Third Party Inv.** is enabled.

> [!NOTE]
>
> - Third-party invoice generation uses G/L account lines. Review the generated invoice and its tax setup before posting; it doesn't copy the item-charge GST fields.
> - To create G/L account charge lines rather than item charges, select **G/L Account** in **Type**.

## Related information

[Purchase from registered vendors](GST-Purchase-from-Registered-Vendor.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
