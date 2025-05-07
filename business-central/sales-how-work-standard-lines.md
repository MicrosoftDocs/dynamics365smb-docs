---
title: Standard recurring sales lines
description: Set up frequently used sales lines to insert them on sales documents and quickly fill the lines with standard information.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: trade, sell, replenishment
ms.search.form: 172
ms.date: 02/14/2024
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Create recurring sales

If you often need to create sales lines with similar information, you can set up standard lines that you can then insert on recurring sales documents, for example, for recurring replenishment orders.  

## Set up recurring sales lines

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Recurring Sales Lines**, and then choose the related link.  
2. On the **Recurring Sales Lines** page, choose the **New** action.  
3. On the **General** FastTab, fill the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
4. On the **Lines** FastTab, enter information in the fields to prepare sales lines that reflect the standard lines that you expect to use as recurring lines on sales documents.  

> [!NOTE]
> You cannot define prices on recurring sales lines because prices, discounts, etc. are calculated on the actual sales documents after you insert the recurring sales lines.

[!INCLUDE [line-no-info](includes/line-no-info.md)]

## Assign recurring sales lines to a customer

Assign one or more recurring sales lines to a customer so that they are available to insert on sales documents for that customer.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Open the card for a relevant customer.
3. Select **Related** and **Sales**
4. Choose the **Recurring Sales Lines** action.
5. On the **Recurring Sales Lines** page, select codes for the recurring sales lines that you want to be able to insert on sales documents for the customer.
6. Fill in the other fields to define when, how, and where the recurring sales lines are to be used.  

    If you plan to use the recurring sales lines set together with the **Create Recurring Sales Invoices** batch job, use the **Valid From Date** and **Valid To Date** fields to restrict when the recurring sales lines are used for creation of invoices. For more information, see [Create multiple sales invoices based on standard sales lines](sales-how-work-standard-lines.md#create-multiple-sales-invoices-based-on-recurring-sales-lines).

    You can also specify a direct-debit payment method and a direct-debit mandate. The sales invoices that are created with the **Create Recurring Sales Invoices** batch job will then include the information required to collect payment with SEPA direct debit. For more information, see [Collect Payments with SEPA Direct Debit](finance-collect-payments-with-sepa-direct-debit.md).

7. In the four fields where you select how the lines are inserted on four document types, select one of the following options:

|Option|Description|
|------|-----------|
|**Manual**|You must manually look up and insert a recurring sales line that exists for the customer.|
|**Automatic**|If multiple recurring sales lines exist for the customer, you'll get a notification from where you can pick which one to insert. If only one recurring sales line exists, it will be inserted automatically.<br /><br />This only works if the new document was created from a document list, for example by choosing the **New** action on the **Sales Orders** page. It doesn't work if the document was created from a customer card, for example.|
|**Always Ask**|A notification appears and all existing recurring sales lines are shown so that you can select one.

## Insert recurring sales lines on a sales invoice

If recurring sales lines exist for the customer, you can insert them, or have them inserted, on all types of sales documents, such as a sales invoice. If you have activated the **Always Ask** options while assigning recurring sales lines to customers, you'll be informed if recurring sales lines exist.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Invoices**, and then choose the related link.
2. Open the sales invoice that you want to insert one or more standard sales lines on.
3. Choose the **Get Recurring Sales Lines** action.
4. On the **Recurring Sales Lines** page, choose the lookup button in the **Code** field, and then select a set of standard sales lines.
5. Choose the **OK** button to insert the standard sales lines on the invoice where you can reuse them as is or edit the information.

## Create multiple sales invoices based on recurring sales lines

You can use the **Create Recurring Sales Invoices** batch job to create sales invoices according to standard sales lines that are assigned to the customers and with posting dates within the valid-from and valid-to dates that you specify on the standard sales lines.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Create Recurring Sales Invoices**, and then choose the related link.
2. On the **Create Recurring Sales Invoices** page, fill in the fields as necessary.
3. In the **Code** filter field, enter the code for standard sales lines that are assigned to a customer that you want to create sales invoices for.
4. Choose the **OK** button.

Sales invoices are created for the customers with the specified standard customer sales code, and any specified direct-debit information, for posting on the specified date.

## Related information

[Sales](sales-manage-sales.md)  
[Set Up Sales](sales-setup-sales.md)  
[Create Recurring Purchase Lines](purchasing-how-work-recurring-purchase-lines.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
