---
author: brentholtorf
ms.topic: include
ms.date: 10/08/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

Use the cost-plus percentage field to set a sales price based on the cost of an item. Business Central calculates the unit price from the item's unit cost and the cost-plus percentage that you enter. This functionality eliminates the need for spreadsheets to determine percentage-based sales prices.

## Determine sales price by cost-plus percentage

1. Choose the **Receivables** action.
1. Choose the **Customers** action.
1. Open the card for a relevant customer.

   –or–

   Choose the **New** action.

   > [!NOTE]
   > For a new customer, in the **No.** field, enter the customer number.

1. On the action bar, select **Sales Price Lists**.
1. On the **Sales Price Lists** page, open an existing price list, or select **New** to create one.
1. On the price list, fill in header fields such as **Currency Code**, **Starting Date**, and **Ending Date** as needed.
1. On a line, set the **Asset Type** field to **Item**, and then select the item in the **Asset No.** field.
1. In the **Cost-plus %** field, enter the percentage to add to the item's unit cost.

   Business Central multiplies the item's unit cost by 1 plus the cost-plus percentage, and then fills in the **Unit Price** field with the result. If you also enter a **Discount Amount**, it's subtracted from the calculated unit price.
1. Repeat these steps for other items on the price list.
