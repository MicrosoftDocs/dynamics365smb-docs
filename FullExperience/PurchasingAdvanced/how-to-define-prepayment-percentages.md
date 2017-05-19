---
title: "How to: Define Prepayment Percentages"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "installments, prepayments"
  - "prepayments, percentages"
ms.assetid: 81fafb27-f5e9-4621-82d9-cd22a918cc97
caps.latest.revision: 10
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
---
# How to: Define Prepayment Percentages
If you require your customers to submit payment before you ship an order to them, or if your vendor requires you to submit payment before they ship an order to you, you can use the Prepayment functionality.  
  
 You can set up default prepayment percentages for customers, vendors, and items.  
  
 After you create a sales or purchase order, you can create a prepayment invoice. You can use the default percentages for each sales or purchase line, or you can adjust the amount as necessary. For example, you can specify a total amount for the entire order.  
  
 Because the prepaid amount belongs to the buyer until they have received the goods or services, you need to set up general ledger accounts to hold the prepayment amounts until the final invoice is posted. Sales prepayments must be recorded in a liabilities account until the items are shipped. Purchase prepayments must be recorded in an assets account until the items are received. In addition, you must set up a separate general ledger account for each VAT identifier. For more information, see [Set Up Prepayments](../Finance/set-up-prepayments.md).  
  
### To add prepayment accounts to the general posting setup  
  
-   In the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**[\($ N\_314 General Posting Setup $\)](DynamicsNAV:////runpage?Page=314)** window, you must fill in the following fields:  
  
     **[\($ T\_252\_36 Sales Prepayments Account $\)](assetId:///5e588810-ec36-44f1-ab12-0f556fc4b58a)**  
  
     **[\($ T\_252\_37 Purch. Prepayments Account $\)](assetId:///7cca15dd-e092-40ea-b8a5-590826dc030f)**  
  
### To set up number series for prepayment documents  
  
-   If you use prepayments for sales, in the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**[\($ N\_459 Sales & Receivables Setup $\)](DynamicsNAV:////runpage?Page=459)** window, fill in the following fields:  
  
     **[\($ T\_311\_21 Posted Prepmt. Inv. Nos. $\)](../Topic/\($%20T_311_21%20Posted%20Prepmt.%20Inv.%20Nos.%20$\).md)**  
  
     **[\($ T\_311\_22 Posted Prepmt. Cr. Memo Nos. $\)](../Topic/\($%20T_311_22%20Posted%20Prepmt.%20Cr.%20Memo%20Nos.%20$\).md)**  
  
-   If you use prepayments for purchases, in the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**[\($ N\_460 Purchases & Payables Setup $\)](DynamicsNAV:////runpage?Page=460)** window, fill in the following fields:  
  
     **[\($ T\_312\_27 Posted Prepmt. Inv. Nos. $\)](../Topic/\($%20T_312_27%20Posted%20Prepmt.%20Inv.%20Nos.%20$\).md)**  
  
     **[\($ T\_312\_28 Posted Prepmt. Cr. Memo Nos. $\)](../Topic/\($%20T_312_28%20Posted%20Prepmt.%20Cr.%20Memo%20Nos.%20$\).md)**  
  
    > [!NOTE]  
    >  You can use the same number series for prepayment invoices and regular invoices, or you can use different number series. If you use different series, they must not overlap \- there must not be any numbers that exist in both series.  
  
### To set up prepayment percentages for items, customers, and\/or vendors  
  
-   For an item, you can set up a default prepayment percentage for all customers, a specific customer, or a customer price group.  
  
-   To setup prepayment defaults for an item, on the item card, on the **Navigate** tab, in the **Sales** group, choose **Prepayment Percentages**.  
  
-   For a customer or vendor, you can set up one default prepayment percentage for all items and all types of sales lines. You enter this on the customer card, on the **Invoicing** FastTab, in the **\($ T\_18\_124 Prepayment % $\)** field.  
  
### To determine which prepayment percentage has first priority  
  
-   An order may have a prepayment percentage on the sales header, and a different percentage for the items on the lines.  
  
     To determine which prepayment percentage applies to each sale line, the program looks for the prepayment percentage in the following order and will apply the first default that it finds:  
  
    1.  A prepayment percentage for the item on the line and the customer that the order is for.  
  
    2.  A prepayment percentage for the item on the line and the customer price group that the customer belongs to.  
  
    3.  A prepayment percentage for the item on the line for all customers.  
  
    4.  The prepayment percentage on the sales or purchase header.  
  
 In other words, the prepayment percentage on the customer card will only apply if there is no prepayment percentage set up for the item.  
  
 However, if you change the contents of the **\($ T\_36\_130 Prepayment Percentage $\)** field on the sales or purchase header after you create the lines, the prepayment percentage on all of the lines will be updated. This makes it easy to create an order with a fixed prepayment percentage, regardless of the percentage set up on items.  
  
## See Also  
 [How to: Create Prepayment Invoices](../Finance/how-to-create-prepayment-invoices.md)   
 [How to: Correct Prepayments](../Finance/how-to-correct-prepayments.md)