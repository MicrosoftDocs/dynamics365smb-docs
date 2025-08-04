---
title: Set up and invoicing sales prepayments
description: Prepayments are payments that are invoiced and posted to a sales or purchase prepayment order before final invoicing. 
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.date: 01/29/2024
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Walkthrough: Set up and invoicing sales prepayments

This walkthrough takes you through the process of setting up and using prepayments in [!INCLUDE [prod_short](includes/prod_short.md)]. [!INCLUDE [prepayment_def](includes/prepayment_def.md)]

[!INCLUDE [prepayment_req](includes/prepayment_req.md)]

For example, you can send more prepayment invoices if more items are added to the order.  

## About this walkthrough  

This walkthrough will take you through the following scenarios:  

- Setting up prepayments  
- Creating an order that requires a prepayment  
- Creating a prepayment invoice  
- Correcting the prepayment requirements on an order  
- Applying prepayments to an order  
- Invoicing the final amount on an order with prepayment  

### Roles

This walkthrough includes tasks for the following roles:  

- Accounting Manager (Phyllis)  
- Order Processor (Susan)  
- Accounts Receivable Administrator (Arnie)  

## Story

 Phyllis is an accounting manager and makes decisions about which customers are required to pay a deposit before items are manufactured or shipped. Phyllis sets up [!INCLUDE[prod_short](includes/prod_short.md)] to calculate prepayments automatically.  

 Susan is a sales order processor. When a customer calls to place an order, Susan enters the order into the system while the customer is on the telephone. This way, Susan can verify prices and payment terms with the customer immediately, and make changes to the order while negotiating with the customer.  

 Arnie works in the Accounts Receivable department and posts invoices and payments.  

 In this scenario, Phyllis sets up prepayment requirements for the customer Selangorian based on their credit history. Phyllis gives Susan instructions for how to handle their orders.  

 When the customer calls, Susan negotiates with the customer until they reach an agreement, and then chooses to calculate the prepayment in several different ways.  

 After Susan sends the prepayment invoice, the customer orders an extra item. Susan updates the order and creates a second prepayment invoice.  

 Arnie registers the customer's payment and applies it to the invoices, and then sends the final invoice.  

## Set up prepayments

Phyllis sets up the system to handle prepayments for customers.  

- Phyllis decides to have the same number series for prepayments as the one used for sales invoicing.  
- Phyllis sets application to check if prepayments are required before final invoicing on an order.  
- Phyllis sets up default values for a required prepayment percentage for particular items and customers.  

The following procedures describe how to complete Phyllis' tasks:  

### To set up number series for prepayments

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales & Receivables Setup**, and then choose the related link.  
2. On the **Sales & Receivables Setup** page, expand the **Number Series** FastTab.  
3. Verify that the number series for posted prepayment invoices in the **Posted Prepmt. Inv. Nos.** field is the same as for posted sales invoices (**Posted Invoice Nos.**), and the number series for posted prepayment credit memos (**Posted Prepmt. Cr. Memo Nos.**) is the same as for posted credit memos (**Posted Credit Memo Nos.**).  

### To block shipments for unpaid prepayment

1. On the **Sales & Receivables Setup** page, on the **General** FastTab, select the **Check Prepayment when Posting** check box.

Now you can't ship or invoice an order that has an unpaid prepayment amount.  

By default, Phyllis requires customer 20000 to be invoiced for a 30% down payment on all orders. Therefore, Phyllis will enter a default prepayment percentage on the customer card.  

Phyllis requires all customers to be invoiced a 20% deposit for item 1896-S. Customer 20000 has a poor payment history, so Phyllis requires a 40% prepayment from customer 20000 for item 1896-S. The following procedure illustrates how to set up default prepayment percentages.  

### To assign default prepayment percentages to customers and items

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.  
2. Open the card for customer 20000 (Trey Research).
3. On the **Payments** FastTab, in the **Prepayment %** field, enter **30**.  
4. Choose the **Related** action, select the **Sales** menu item, and then choose the **Prepayment Percentages** menu item.  
5. Fill in two lines on the **Sales Prepayment Percentages** page as follows.  

    |**Sales Type**|**Sales Code**|**Item No.**|**Prepayment %**|  
    |--------------------|--------------------|------------------|----------------------|  
    |**Customer**|**20000**|**1896-S**|**40**|
    |**Customer**|**20000**|**1900-S**|**30**|  
    
    > [!TIP]
    > Depending on your country/region, you must also specify a tax group code on the **Costs & Posting** FastTab for item 1896-S. When you use the demonstration company, this field is already set.

6. Close all pages.  

### To specify an account for sales prepayments in general posting setup

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Posting Setup**, and then choose the related link.  
2. Select the line where the **Gen. Bus. Posting Group** field is set to **DOMESTIC**, and the **Gen. Prod. Posting Group** field is set to **RETAIL**.  
3. In the **Sales Prepayments Account** field, specify the relevant account. Your selection is automatically saved.  

> [!TIP]
> If you cannot see the field in the **General Posting Setup** page, then use the horizontal scroll bar at the bottom of the page to scroll to the right.  

## Create an order that requires a prepayment

 In the following scenario, Susan, the order processor, creates an order when talking to a customer. The items the customer is ordering require a prepayment. Plus, the customer has made some late payments in the past. Susan's been instructed to require a fixed amount of **800** as a prepayment on the order.  

The customer asks to pay 35%, to which Susan agrees and changes the order.  

Susan creates the prepayment invoice and sends it to the customer.  

### To create a sales order with a prepayment

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
2. Choose the **New** action.  
3. In the **Customer Name** field, choose **Trey Research**.  
4. Close the overdue balance warning that is displayed.  
5. Fill in two sales lines with the following information.  

    |**Type**|**No.**|**Quantity**|  
    |--------------|-------------|------------------|  
    |**Item**|**1896-S**|**1**|  
    |**Item**|**1900-S**|**1**|

    By default, the prepayment fields on the sales line are hidden. To display the fields, you must personalize the page. For more information, see [To start personalizing a page through the Personalizing banner](ui-personalization-user.md#start-personalizing-by-using-the-personalization-mode).

6. Verify that the **Prepayment %** field on the line with item **1900-S** contains **30**. The default value was taken from the sales header, which was populated from the customer card.  

    The **Prepayment %** field on the line with item **1896-S** contains **40**. 40 is the percentage you entered on the **Sales Prepayment Percentages** page for item **1896-S** and customer **20000**.  

    For more information, see [Set Up Prepayments](finance-set-up-prepayments.md).  
7. In the **Order** action, choose  **Statistics**.  
8. On the **Prepayment** FastTab, the **Prepayment Amount Excl. VAT** field contains **458.16**. If you create a prepayment invoice for the order now, 458.16 is the amount on the invoice.  

    In this scenario, Susan has been instructed to suggest a total prepayment of **800** for the order.  

    > [!IMPORTANT]  
    >  Depending on your country/region, the following step might not apply.  
9. Change the amount in the **Prepmt. Amount Excl. Tax** field to **800** and then close the page.  
10. Verify the **Prepayment %** field on the sales lines, and you'll see that it has been recalculated to **67.02438** and **67.02282**.  

     The recalculation includes all lines that have a prepayment percentage that is greater than 0.  

     Now the customer asks if the prepayment percent can be set to 35%. Susan's supervisor approves the change.
11. On the **Sales Order** page, on the **Prepayment** FastTab in the **Prepayment %** field, enter **35**.  
12. In the warning that appears, choose the **Yes** button. A rate of 35% will be applied as the payment percentage for the whole order.  
13. Verify that the lines have been updated correctly.  

## Create a prepayment invoice

After entering the correct prepayment values on the order, Susan creates the prepayment invoice and sends it to the customer.  

### To create a prepayment invoice

1. On the **Sales Order** page, choose **Actions**, then **Posting**, then **Prepayment** and then select **Post and Print Prepmt. Invoice**
2. Choose the **Yes** button to post the invoice.  

> [!NOTE]  
> Susan would now send the invoice to the customer.  

## Create an additional prepayment invoice

The following day, the customer calls Susan and makes changes to the order. The customer wants two of item 1896-S. Susan reopens the order, updates it, and then creates a second prepayment invoice for the order and sends it to the customer.  

### To create an additional prepayment invoice

1. On the **Sales Order** page, choose the **Release** action, and then **Reopen**.  
2. On the line for item **1896-S**, in the **Quantity** field, enter **2**.  

    In the **Order** action, choose **Statistics**. The **Prepayment Amount Excl. VAT** field now contains **768.04**, and the **Prepmt. Amt. Invoiced Excl. VAT** field contains **417.76**. These values show that there's an extra prepayment amount that hasn't been invoiced yet.  
3. To post an invoice for the extra prepayment amount, choose **Actions**, then **Posting**, then **Prepayment** and then select **Post and Print Prepmt. Invoice**
4. Choose the **Yes** button to post the invoice.  

## Apply the prepayments

The customer pays the prepayment amount. Arnie, from the accounting department, registers the payment, and applies it to the prepayment invoices.  

### To apply a payment to the prepayment invoices

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cash Receipt Journals**, and then choose the related link.  
2. Fill in a journal line with the following information.  

    |Field name|Enter|  
    |----------------|-----------|  
    |**Document Type**|**Payment**|  
    |**Account Type**|**Customer**|  
    |**Account No.**|**20000**|  
3. Choose the **Process** action, and then **Apply Entries**.  
4. On the **Apply Customer Entries** page, select the first prepayment invoice, and then choose the **Process** action, and then choose the **Set Applies-to ID** action.  
5. Repeat the previous step for the second prepayment.  
6. Choose the **OK** button.  

    The **Amount** fields have now been filled in with the sum of the two prepayment invoices.  

7. To post the journal, choose the **Post/Print** action, then select **Post**.
8. Choose the **Yes** button.

## Invoice the remaining amount

Now Arnie has been informed that the items on the order have been shipped and that the order is ready for invoicing. Arnie creates the invoice for the order.  

### To invoice the remaining amount

1. Open the sales order.
2. Choose the **Posting** action, then **Post**.
3. Select **Ship and Invoice**, and then choose the **OK** button.
4. If you want to preview the invoice, choose the **Yes** button.

    > [!NOTE]  
    > Normally, the shipping department would have already posted the shipment.  

    Arnie can view the history to verify that the sales invoice was created as intended.

5. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Sales Invoices**, and then choose the related link.  

## Update the status of prepaid orders and invoices automatically

You can speed up order and invoice processing by setting up job queue entries that automatically update the status of those documents. When a prepayment invoice is paid, the job queue entries can automatically change the document status from **Pending Prepayment** to **Released**. When you set up the job queue entries, the codeunits you'll need to use are **383 Upd. Pending Prepmt. Sales** and **383 Upd. Pending Prepmt. Purchase**. We recommend that you schedule the entries to run frequently, for example, every minute. For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).

## Next steps

This walkthrough covered the following steps to set up [!INCLUDE[prod_short](includes/prod_short.md)] to handle prepayments. 

- Set up default prepayment percentages on customers and items.
- Use different methods to calculate the prepayments on an order.  
- Calculate the prepayment amount as a percentage of the total on the order.
- Assign one total prepayment amount to the order.  

You've also posted a prepayment invoice, created a second prepayment invoice when the order has changed, and posted the final invoice for the remaining amount.  

The prepayments capabilities make it easy to set up and enforce prepayment rules for customers and items. They also let you to post every payment against an invoice.  

## Related information

[Invoicing Prepayments](finance-invoice-prepayments.md)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Business Process Walkthroughs](walkthrough-business-process-walkthroughs.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
