---
title: Setting up customer and vendor agreements in Russia
description: Russian localization provides features for managing customer and vendor agreements.
author: DianaMalina
ms.topic: how-to
ms.search.keywords: customer agreement, vendor agreement, Russia
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Set up customer and vendor agreements

The customer and vendor agreements feature provides the following:

- A list of agreements for customers and vendors
- An agreement card where all the required information about agreements is stored
- Synchronization between agreements and dimensions, to enable use of existing reports and dimension analyses

The following procedure shows how to set up an agreement for a customer, but the procedure for a vendor is similar and starts from the **Purchases & Payables** window.

## Set up an agreement

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales & Receivables Setup**, and then choose the related link.

1. To set up agreement, on the **Dimensions** FastTab and **Numbering** FastTabs, enter information in the fields listed in the following table.

   | Field | Description |
   |:-|:-|
   | **Customer Agreement Dim. Code** | Select a dimension code for customer agreements. For vendors, use **Vendor Agreement Dim. Code** in **Purchases & Payables Setup**. |
   | **Synch. Agreement Dimension** | Select this field to create a dimension value code after agreements is created, and the dimension value codes are equal to the agreement codes. |
   | **Customer Agreement Nos.** | Select the customer agreement number series. |

## Create a customer or vendor agreement

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.

1. Select a customer from the list, and then choose the **Edit** action.

1. Expand the **Agreements** FastTab, and modify the **Agreement Posting** field.

1. Choose the **Agreements** action. In the **Customer Agreements** window, choose the **New** action.

1. In the **Customer or Vendor Agreement** card, enter the information in the following fields listed in the table.

   | Field | Description |
   |:-|:-|
   | **No.** | Enter an agreement number of up to 20 characters. Automatic numbering uses **Agreement Nos.** on the customer or vendor card. |
   | **Description** | Enter the description of the agreement. Enter a maximum of 250 characters, both numbers and letters. |
   | **External Agreement No.** | Enter the agreement number used by the customer or vendor. |
   | **Agreement Date** | Enter the date of the agreement. |
   | **Starting Date** | Enter starting date of the period for which you want to use the agreement. |
   | **Expire Date** | Enter the expiration date of the agreement. |
   | **Blocked** | Select the blocking option that applies to the agreement. The available options depend on whether it's a customer or vendor agreement. |

The agreement belongs to the customer or vendor from whose card you opened **Agreements**. Use the **Dimensions** action to review its default dimensions. When **Synch. Agreement Dimension** is enabled, creating an agreement also creates a dimension value whose code matches the agreement number.

On the agreement card, you can use the following actions:

- **Ledger Entries**: Shows customer or vendor ledger entries posted with this agreement number.
- **Dimensions**: Shows default dimensions for the agreement.

Agreement dimension synchronization depends on **Synch. Agreement Dimension** and the agreement dimension code in the corresponding sales or purchases setup.

## Related information

- [Russian Receivables Reports](russian-receivables-reports.md)  
- [Russian Payables Reports](russian-payables-reports.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
