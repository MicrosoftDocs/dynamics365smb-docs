---
title: Setting up customer and vendor agreements in Russia
description: Russian enhancements include agreements with customers and vendors.
author: DianaMalina


ms.topic: how-to
ms.search.keywords:
ms.date: 04/01/2021
ms.reviewer: bholtorf
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Set Up Customer and Vendor Agreements

The customer and vendor agreements feature provides the following:

- A list of agreements for customers and vendors
- An agreement card where all the required information about agreements is stored
- Synchronization between agreements and dimensions, to enable use of existing reports and dimension analyses

The following procedure shows how to set up an agreement for a customer, but the procedure for a vendor is similar and starts from the **Purchases & Payables** window.

## To set up an agreement

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales & Receivables Setup**, and then choose the related link.

2. To set up agreement, on the **Dimensions** FastTab and **Numbering** FastTabs, enter information in the fields listed in the following table.

   | Field                          | Description         |
   | :----------------------------- | :------------------ |
   | **Dimension Agreement**        | Select a dimension code for agreements.             |
   | **Synch. Agreement Dimension** | Select this field to create a dimension value code after agreements is created, and the dimension value codes are equal to the agreement codes. |
   | **Customer Agreement Nos.**    | Select the customer agreement number series.        | 

## To create a customer or vendor agreement 

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.

2. Select a customer from the list, and then choose the **Edit** action.

3. Expand the **Agreements** FastTab, and modify the **Agreement Posting** field.

4. Choose the **Agreements** action. In the **Customer Agreements** window, choose the **New** action.

5. In the **Customer or Vendor Agreement** card, enter the information in the following fields listed in the table.

   | Field                    | Description                                                  |
   | :----------------------- | :----------------------------------------------------------- |
   | **Code**                 | Enter the code for an agreement. Enter a maximum of 20 characters, both numbers and letters. It is created by default from the number series set up in the General Ledger Setup form. |
   | **Description**          | Enter the description of the agreement. Enter a maximum of 250 characters, both numbers and letters. |
   | **Source No.**           | Select this field to see the number of the vendor or customer for whom the agreement is created. |
   | **Source Name**          | Enter the name of the vendor or customer for whom the agreement is created. The source name is automatically retrieved from the Vendor or Customer table. |
   | **Dimension Value Code** | Enter the dimension value code. Enter agreement and dimension functionality. The dimension value code is equal to the agreement code when the **Synch. Agreement Dimensions** field is selected in the **Sales & Receivables Setup** window. |
   | **Starting Date**        | Enter starting date of the period for which you want to use the agreement. |
   | **Expire Date**          | Enter the expiration date of the agreement.                  |
   | **Blocked**              | Select this field to prevent posting of entries on the agreement. When you try to create a document with a blocked agreement, an error message is displayed. An agreement is usually blocked after the expiration date. |

On the **Navigate** tab, you can find the following functions: 

- List - Shows a list of customer or vendor agreements.
- Ledger Entries - Shows customer or vendor ledger entries posted with this agreement code. 

The agreements are fully synchronized with dimensions. You can post transactions and choose the dimension value code of the appropriate agreement from the list of agreements.

## Related information

[Russian Receivables Reports](Russian-Receivables-Reports.md)  
[Russian Payables Reports](Russian-Payables-Reports.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
