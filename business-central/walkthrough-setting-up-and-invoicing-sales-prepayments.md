---
    title: Walkthrough - Setting Up and Invoicing Sales Prepayments | Microsoft Docs
    description: Prepayments are payments that are invoiced and posted to a sales or purchase prepayment order before final invoicing. You may require a deposit before you manufacture items to order, or you may require payment before you ship items to a customer. You use the prepayments functionality in Business Central to invoice and collect deposits that are required from customers or remit deposits to vendors. Thus, you can make sure that all payments are posted against an invoice.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Walkthrough: Setting Up and Invoicing Sales Prepayments

**Note**: This walkthrough must be performed on a demonstration company with the **Full Evaluation - Complete Sample Data** option, which is available in the Sandbox environment. For more information, see [Creating a Sandbox Environment](across-how-create-sandbox-environment.md).

Prepayments are payments that are invoiced and posted to a sales or purchase prepayment order before final invoicing. You may require a deposit before you manufacture items to order, or you may require payment before you ship items to a customer. You use the prepayments functionality in [!INCLUDE[d365fin](includes/d365fin_md.md)] to invoice and collect deposits that are required from customers or remit deposits to vendors. Thus, you can make sure that all payments are posted against an invoice.  

 Prepayment requirements can be defined for a customer or vendor for all items or selected items. After you complete the required setup, you can generate prepayment invoices from sales and purchase orders for the calculated prepayment amount. You can change the default amounts on the invoice as needed. For example, you can send additional prepayment invoices if additional items are added to the order.  

## About This Walkthrough  
 This walkthrough will take you through the following scenarios:  

-   Setting up prepayments  
-   Creating an order that requires a prepayment  
-   Creating a prepayment invoice  
-   Correcting the prepayment requirements on an order  
-   Applying prepayments to an order  
-   Invoicing the final amount on an order with prepayment  

### Roles  
 This walkthrough includes tasks for the following roles:  

-   Accounting Manager (Phyllis)  
-   Order Processor (Susan)  
-   Accounts Receivable Administrator (Arnie)  

## Story  
 Phyllis is an accounting manager. She makes decisions about which customers are required to pay a deposit before items are manufactured or shipped. Phyllis sets up [!INCLUDE[d365fin](includes/d365fin_md.md)] to calculate prepayments automatically.  

 Susan is a sales order processor. When a customer calls to place an order, she enters the order into the system while the customer is on the telephone. This way, she can verify prices and payment terms with the customer immediately, and she can make adjustments to the order while she negotiates with the customer.  

 Arnie works in the Accounts Receivable department, where he posts invoices and payments.  

 In this scenario, Phyllis sets up prepayment requirements for the customer Selangorian, based on their credit history, and gives Susan instructions for how to handle their orders.  

 When the customer calls, Susan negotiates with the customer until they reach an agreement. She can then choose to calculate the prepayment in several different ways.  

 After Susan sends the prepayment invoice, the customer orders an extra item. Susan updates the order and creates a second prepayment invoice.  

 Arnie registers the customer's payment and applies it to the invoices, and then sends the final invoice.  

## Setting Up Prepayments  
 Phyllis sets up the system to handle prepayments for customers.  

-   Phyllis decides to have the same number series for prepayments as the one used for sales invoicing.  
-   Phyllis sets application to check if prepayments are required before final invoicing on an order.  
-   Phyllis sets up default values for a required prepayment percentage for particular items and customers.  

The following procedures describe how to complete Phyllis' tasks:  

#### To set up number series for prepayments  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales & Receivables Setup**, and then choose the related link.  
2.  On the **Sales & Receivables Setup** page, expand the **Numbering** FastTab.  
3.  Verify that the number series for posted prepayment invoices in the **Posted Prepmt. Inv. Nos.** field is the same as for posted sales invoices (**Posted Invoice Nos.**) and the number series for posted prepayment credit memos (**Posted Prepmt. Cr. Memo Nos.**) is the same as for posted credit memos (**Posted Credit Memo Nos.**).  

#### To block shipments for unpaid prepayment  
1.  On the **Sales & Receivables Setup** page, on the **General** FastTab, select the **Check Prepayment when Posting** check box.

    Now you cannot ship or invoice an order that has an unpaid prepayment amount.  

By default, Phyllis requires customer 20000 to be invoiced for a 30% down payment on all orders. Therefore, she will enter a default prepayment percentage on the customer card.  

Phyllis requires all customers to be invoiced a 20% deposit for item 1100. Customer 20000 has a poor payment history. Therefore, she requires a 40% prepayment from customer 20000 for item 1100. The following procedure illustrates how to set up default prepayment percentages.  

#### To assign default prepayment percentages to customers and items  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.  
2.  Open the card for customer 20000 (Selangorian).
3.  In the **Prepayment %** field, type **30**.  
4.  Choose the **OK** button to close the customer card.  
5.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.  
6.  Open the card for customer 1100.
7.  Choose the **Prepayment Percentages** action.  
8.  Fill in two lines on the **Sales Prepayment Percentages** page as follows.  

    |**Sales Type**|**Sales Code**|**Item No.**|**Prepayment %**|  
    |--------------------|--------------------|------------------|----------------------|  
    |**Customer**|**20000**|**1100**|**40**|  
    |**All Customers**||**1100**|**20**|  

    > [!IMPORTANT]  
    >  Depending on your country/region, you must also specify a tax group code on the **Invoicing** FastTab for items 1000 and 1100.  

9. Close all pages.  

#### To specify an account for sales prepayments in general posting setup  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Posting Setup**, and then choose the related link.  
2.  Select the line where the **Gen. Bus. Posting Group** field is set to **EXPORT**, and the **Gen. Prod. Posting Group** field is set to **RETAIL**, and then choose the **Edit** action.  
3.  On the **General Posting Setup Card** page, in the **Sales Prepayments Account** field, specify the relevant account.  
4.  Choose the **OK** button.  

## Creating an Order that Requires a Prepayment  
 In the following scenario, Susan, the order processor, creates an order when talking to a customer. The items that the customer orders require a prepayment, and the customer has made some late payments in the past. Therefore, Susan has been instructed to require a fixed amount of 2,000 as a prepayment on the order.  

The customer requests to be able to pay 35%, to which Susan can agree. Therefore, she changes the order.  

Susan creates the prepayment invoice and sends it to the customer.  

#### To create a sales order with a prepayment  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
2.  Choose the **New** action.  
3.  In the **Sell-to Customer No.** field, select **20000**.  
5.  Accept the overdue balance warning that is displayed.  
6.  Fill in two sales lines with the following information.  

    |**Type**|**No.**|**Quantity**|  
    |--------------|-------------|------------------|  
    |**Item**|**1000**|**1**|  
    |**Item**|**1100**|**1**|

    By default, the prepayment fields on the sales line are hidden, so you must display them.  

7. Verify that the **Prepayment %** field on the line with item **1000** contains **30**. The default value was taken from the sales header, which was populated from the customer card.  

    The **Prepayment %** field on the line with item **1100** contains **40**. This is the percentage you entered on the **Sales Prepayment Percentages** page for item **1100** and customer **20000**.  

    For more information, see [Set Up Prepayments](finance-set-up-prepayments.md).  
8. Choose the **Statistics** action.  
9. On the **Prepayment** FastTab, the **Prepmt. Line Amount Excl. VAT** field contains **1,560**. If you create a prepayment invoice for the order now, then this is the amount that is displayed on the invoice.  

    In this scenario, Susan has been instructed to suggest a total prepayment of 2000 for the order.  

    > [!IMPORTANT]  
    >  Depending on your country/region, the following step might not apply.  
10. Change the amount in the **Prepmt. Line Amount Excl. VAT** field to **2000** and then close the page.  
11. Verify the **Prepayment %** field on the sales lines, and you will see that it has been recalculated to **40.81625**.  

    The recalculation includes all lines that have a prepayment percentage that is greater than 0.  

    Now the customer asks if the prepayment percent can be set to 35%. Susan's supervisor approves the change.  

12. On the **Sales Order** page, in the **Prepayment %** field, enter **35**.  
13. In the warning that appears, choose the **Yes** button. A rate of 35% will be applied as the payment percentage for the whole order.  
14. Verify that the lines have been updated accordingly.  

## Creating a Prepayment Invoice  
After entering the correct prepayment values on the order, Susan creates the prepayment invoice and sends it to the customer.  

#### To create a prepayment invoice  

1.  On the **Sales Order** page, choose the **Post Prepayment Invoice** action.  

> [!NOTE]  
>  Susan would select **Post and Print Prepmt. Invoice** and mail the invoice to the customer.  

## Creating an Additional Prepayment Invoice  
The following day, the customer calls Susan and makes changes to the order. The customer wants two of item 1100. Susan reopens and updates the order, and then she creates a second prepayment invoice on the order and sends it to the customer.  

#### To create an additional prepayment invoice  

1.  On the **Sales Order** page, choose the **Reopen** action.  
2.  On the line for item **1100**, in the **Quantity** field, enter **2**.  

    Scroll to see the prepayment fields. The **Prepayment Line Amount Excl. VAT** field now contains **630**, and the **Prepmt. Amt. Inv. Excl. VAT** field contains **315**. This shows that there is an additional prepayment amount that has not been invoiced yet.  
3.  To post an invoice for the additional prepayment amount, choose the **Post Prepayment Invoice** action.  

## Applying the Prepayments  
The customer pays the prepayments amount and Arnie, who works in the accounts department, registers the payment and applies it to the prepayment invoices.  

#### To apply a payment to the prepayment invoices  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cash Receipt Journals**, and then choose the related link.  
2.  Fill in a journal line with the following information.  

    |Field name|Enter|  
    |----------------|-----------|  
    |**Document Type**|**Payment**|  
    |**Account Type**|**Customer**|  
    |**Account No.**|**20000**|  
3. Choose the **Apply Entries** action.  
4.  On the **Apply Customer Entries** page, select the first prepayment invoice, and then choose the **Set Applies-to ID** action.  
5.  Repeat the previous step for the second prepayment.  
6.  Choose the **OK** button.  

    The amount field has now been filled in with the sum of the two prepayment invoices.  

7.  Post the journal.  

## Invoicing the Remaining Amount  
Now Arnie has been informed that the items on the order have been shipped and that the order is ready for invoicing. Arnie creates the invoice for the order.  

#### To invoice the remaining amount  
1. Open the sales order.  
2. Choose the **Ship and Invoice** action, and then choose the **OK** button.  

> [!NOTE]  
>  Normally, the shipping department would have already posted the shipment.  

Arnie can view the history to verify that the sales invoice was created as intended.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Sales Invoices**, and then choose the related link.  

## Next Steps  
This walkthrough has taken you through steps to set up [!INCLUDE[d365fin](includes/d365fin_md.md)] to handle prepayments. You have set up default prepayment percentages on customers and items, and you have also used different methods to calculate the prepayments on an order. You have tried to assign one total prepayment amount to the order, and you have had the prepayment amount calculated as a percentage of the whole order.  

You have also posted a prepayment invoice, created a second prepayment invoice when the order has changed, and posted the final invoice for the remaining amount.  

The prepayments functionality in [!INCLUDE[d365fin](includes/d365fin_md.md)] makes it easy to set up and enforce prepayment rules for customers and items, and it enables you to post every payment against an invoice.  

## See Also  
[Invoicing Prepayments](finance-invoice-prepayments.md)  
[Finance](finance.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Business Process Walkthroughs](walkthrough-business-process-walkthroughs.md)
