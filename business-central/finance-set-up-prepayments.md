---
title: Set Up Prepayments | Microsoft Docs
description: Prepayments are payments that are invoiced and posted to a sales or purchase prepayment order before final invoicing. You might require a deposit before you manufacture items to order, or you might require payment before you ship items to a customer. The prepayments functionality enables you to invoice and collect deposits required from customers or to remit deposits to vendors. Thus, you can ensure that all payments are posted against an invoice.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: prepayment
ms.date: 04/01/2020
ms.author: edupont

---
# Set Up Prepayments
If you require your customers to submit payment before you ship an order to them, or if your vendor requires you to submit payment before they ship an order to you, you can use the Prepayment functionality. The functionality enables you to invoice and collect deposits required from customers or to remit deposits to vendors, and to ensure that all partial payments are posted against an invoice. For more information, see [Create Prepayment Invoices](finance-how-to-create-prepayment-invoices.md).

Before you can post prepayment invoices, you have to set up the posting accounts in the general ledger, and you have to set up number series for prepayment documents. You must specify an account for prepayments related to sales and an account for prepayments related to purchasing. You can specify the same posting accounts to be used for all prepayments related to all general business posting groups or general product posting groups, or you can specify specific accounts for specific posting groups for sales and purchasing, respectively. This depends on your company's requirements for tracking prepayments.  

You can define the percentage of the line amount that will be invoiced for prepayment, for a customer or vendor, for all items or selected items. After you complete the setup, you can generate prepayment invoices from sales and purchase orders. You can use the default percentages for each sales or purchase line, or you can change the amounts on the invoice as needed. For example, you can specify a total amount for the entire order.  

Because the prepaid amount belongs to the buyer until they have received the goods or services, you need to set up general ledger accounts to hold the prepayment amounts until the final invoice is posted. Sales prepayments must be recorded in a liabilities account until the items are shipped. Purchase prepayments must be recorded in an assets account until the items are received. In addition, you must set up a separate general ledger account for each VAT identifier.  

[!INCLUDE[local-func-setup-link](includes/local-func-setup-link.md)]

## To add prepayment accounts to the general posting setup  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Posting Setup**, and then choose the related link.
2. On the **General Posting Setup** page, fill in the following fields:  

    - **Sales Prepayments Account**  
    - **Purch. Prepayments Account**  

> [!TIP]
> If you cannot see the fields in the **General Posting Setup** page, then use the horizontal scroll bar at the bottom of the page to scroll to the right.  

If you have not already set up general ledger accounts for prepayments, you can open the **G/L Account List** page from the relevant account field.  

## To set up number series for prepayment documents  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales & Receivables Setup**, and then choose the related link.
2. On the **Sales & Receivables Setup** page, fill in the following fields:  

   - **Posted Prepmt. Inv. Nos.**
   - **Posted Prepmt. Cr. Memo Nos.**

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchases & Payables Setup**, and then choose the related link.
2. On the **Purchases & Payables Setup** page, fill in the following fields:

    - **Posted Prepmt. Inv. Nos.**
    - **Posted Prepmt. Cr. Memo Nos.**

> [!NOTE]  
> You can use the same number series for prepayment invoices and regular invoices, or you can use different number series. If you use different series, they must not overlap because there must not be any numbers that exist in both series.  

## To set up prepayment percentages for items, customers, and vendors  
For an item, you can set up a default prepayment percentage for all customers, a specific customer, or a customer price group.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
2. Select an item, and then choose the **Prepayment Percentages** action.  
3. On the **Sales Prepayment Percentages** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

For a customer or vendor, you can set up one default prepayment percentage for all items and all types of sales lines. You enter this on the customer or vendor card.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Open the card for a customer.
3. Fill in the **Prepayment %** field.
4. Repeat the steps for other customers or for vendors.  

### To determine which prepayment percentage has first priority  

An order may have a prepayment percentage on the sales header, and a different percentage for the items on the lines. To determine which prepayment percentage applies to each sale line, the system looks for the prepayment percentage in the following order and will apply the first default that it finds:  

1. A prepayment percentage for the item on the line and the customer that the order is for.  
2. A prepayment percentage for the item on the line and the customer price group that the customer belongs to.  
3. A prepayment percentage for the item on the line for all customers.  
4. The prepayment percentage on the sales or purchase header.  

In other words, the prepayment percentage on the customer card will only apply if there is no prepayment percentage set up for the item. However, if you change the contents of the **Prepayment Percentage** field on the sales or purchase header after you create the lines, the prepayment percentage on all of the lines will be updated. This makes it easy to create an order with a fixed prepayment percentage, regardless of the percentage set up on items.

## See Also  

[Invoicing Prepayments](finance-invoice-prepayments.md)  
[Walkthrough: Setting Up and Invoicing Sales Prepayments](walkthrough-setting-up-and-invoicing-sales-prepayments.md)  
[Calculate Goods and Services Tax on Prepayments in Australia](LocalFunctionality/Australia/how-to-calculate-goods-and-services-tax-on-prepayments.md)  
[Calculate Goods and Services Tax on Prepayments in New Zealand](LocalFunctionality/NewZealand/how-to-calculate-goods-and-services-tax-on-prepayments.md)  
[Understanding the General Ledger and the COA](finance-general-ledger.md)  
[Finance](finance.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
