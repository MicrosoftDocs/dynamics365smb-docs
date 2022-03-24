---
author: edupont04


ms.topic: include
ms.date: 04/01/2021
ms.author: edupont
---
When all the items have been entered as lines, you can calculate the invoice discount for the entire sales document by choosing the **Calculate Invoice Discount** action.

The discount is calculated based on all the lines in the sales document for items where the **Allow Invoice Disc.** field on the sales order line contains **Yes**. This is the default setting for items. Lines with item charges, for example, are not included in the calculation of the invoice discount. If you want to apply a discount to such lines, you must set the **Line Discount %** field on the relevant lines.  

> [!TIP]
> If the **Calc. Inv. Discount** field is selected in the **Sales and Receivables Setup** page, then the invoice discount is calculated automatically when you do either of the following on a sales document:
>
> * View statistics
> * View a test report
> * Print
> * Post

The invoice discount terms for a customer are defined in the **Cust. Invoice Discounts** page for the customer. The currency code on the sales document is used to find the invoice discount terms in the corresponding currency.

If invoice discounts have not been defined for foreign currencies, then the invoice discount terms defined in the **Cust. Invoice Discounts** page with amounts in your local currency and the exchange rate on the posting date on the sales document are used to calculate the invoice discount in the foreign currency.
