---
author: brentholtorf
ms.topic: include
ms.date: 10/05/2022
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
After you've added all the items on lines you can calculate the invoice discount for the entire sales document by choosing the **Calculate Invoice Discount** action.

The discount is calculated based on all lines on the sales document where the **Allow Invoice Disc.** checkbox is chosen. By default, invoice discounts are allowed. However, lines with item charges, for example, are not included in the calculation of the invoice discount. To apply a discount to such lines, enter a value in the **Line Discount Amount** field on the lines.  

> [!NOTE]
> By default, the **Allow Invoice Disc.** and **Line Discount Amount** fields are hidden on lines. If the fields aren't available, you can add them by personalizing the page. For more information, see [Personalize Your Workspace](../ui-personalization-user.md#start-personalizing-by-using-the-personalization-mode).

> [!TIP]
> If the **Calc. Inv. Discount** field is selected in the **Sales & Receivables Setup** page, the invoice discount is calculated automatically. When the calculation happens differs, depending on the type of sales document you're using.
>
> If you're using a sales order, the discount is calculated when you add a line. For all other sales documents, such as sales invoices, the discount is calculated when you do any of the following actions:
>
> * View statistics
> * View a test report
> * Print
> * Post

You define invoice discount terms for a customer on the **Cust. Invoice Discounts** page. The currency code on the sales document is used to find the invoice discount terms in the corresponding currency.

If you haven't defined invoice discounts for foreign currencies, the discount terms on the **Cust. Invoice Discounts** page are used to calculate the discount. The calculation uses your local currency and the exchange rate that was valid on the document's posting date.
