---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# How to: Define Prepayment Percentages
If you require your customers to submit payment before you ship an order to them, or if your vendor requires you to submit payment before they ship an order to you, you can use the Prepayment functionality.  
  
 You can set up default prepayment percentages for customers, vendors, and items.  
  
 After you create a sales or purchase order, you can create a prepayment invoice. You can use the default percentages for each sales or purchase line, or you can adjust the amount as necessary. For example, you can specify a total amount for the entire order.  
  
 Because the prepaid amount belongs to the buyer until they have received the goods or services, you need to set up general ledger accounts to hold the prepayment amounts until the final invoice is posted. Sales prepayments must be recorded in a liabilities account until the items are shipped. Purchase prepayments must be recorded in an assets account until the items are received. In addition, you must set up a separate general ledger account for each VAT identifier. For more information, see [Set Up Prepayments](../set-up-prepayments.md).  
  
### To add prepayment accounts to the general posting setup  
  
-   In the **General Posting Setup** window, you must fill in the following fields:  
  
     **Sales Prepayments Account**  
  
     **Purch. Prepayments Account**  
  
### To set up number series for prepayment documents  
  
-   If you use prepayments for sales, in the **Sales & Receivables Setup** window, fill in the following fields:  
  
     **Posted Prepmt. Inv. Nos.**  
  
     **Posted Prepmt. Cr. Memo Nos.**  
  
-   If you use prepayments for purchases, in the **Purchases & Payables Setup** window, fill in the following fields:  
  
     **Posted Prepmt. Inv. Nos.**  
  
     **Posted Prepmt. Cr. Memo Nos.**  
  
    > [!NOTE]  
    >  You can use the same number series for prepayment invoices and regular invoices, or you can use different number series. If you use different series, they must not overlap - there must not be any numbers that exist in both series.  
  
### To set up prepayment percentages for items, customers, and\/or vendors  
  
-   For an item, you can set up a default prepayment percentage for all customers, a specific customer, or a customer price group.  
  
-   To setup prepayment defaults for an item, on the item card, on the **Navigate** tab, in the **Sales** group, choose **Prepayment Percentages**.  
  
-   For a customer or vendor, you can set up one default prepayment percentage for all items and all types of sales lines. You enter this on the customer card, on the **Invoicing** FastTab, in the **Prepayment %** field.  
  
### To determine which prepayment percentage has first priority  
  
-   An order may have a prepayment percentage on the sales header, and a different percentage for the items on the lines.  
  
     To determine which prepayment percentage applies to each sale line, the program looks for the prepayment percentage in the following order and will apply the first default that it finds:  
  
    1.  A prepayment percentage for the item on the line and the customer that the order is for.  
  
    2.  A prepayment percentage for the item on the line and the customer price group that the customer belongs to.  
  
    3.  A prepayment percentage for the item on the line for all customers.  
  
    4.  The prepayment percentage on the sales or purchase header.  
  
 In other words, the prepayment percentage on the customer card will only apply if there is no prepayment percentage set up for the item.  
  
 However, if you change the contents of the **Prepayment Percentage** field on the sales or purchase header after you create the lines, the prepayment percentage on all of the lines will be updated. This makes it easy to create an order with a fixed prepayment percentage, regardless of the percentage set up on items.  
  
## See Also  
 [How to: Create Prepayment Invoices](../how-to-create-prepayment-invoices.md)   
 [How to: Correct Prepayments](../how-to-correct-prepayments.md)