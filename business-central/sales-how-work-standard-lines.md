---
title: Setup Standard Lines for Recurring Sales and Purchases| Microsoft Docs
description: You can set up sales lines and purchase lines that you frequently make and then insert them on sales and purchase documents to quickly fill the lines with standard information.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: trade, sell, replenishment
ms.date: 07/02/2017
ms.author: sgroespe

---
# Create Recurring Sales and Purchase Lines
If you often need to create sales and purchase lines with similar information, you can set up standard lines that you can then insert on recurring sales and purchase documents, for example, for recurring replenishment orders.  

The following procedure shows how to work with standard sales lines. It works in a similar way for standard purchase lines.  

## To set up standard sales lines  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Standard Sales Codes**, and then choose the related link.  
2. In the **Standard Sales Lines** window, choose the **New** action.  
3. On the **General** FastTab, fill the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
4. On the **Lines** FastTab, enter information in the fields to prepare sales lines that reflect the standard lines that you expect to use as recurring lines on sales documents.  

## To insert standard sales lines on a sales invoice
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Invoices**, and then choose the related link.
2. Open the sales invoice that you want to insert one or more standard sales lines on.
3. Choose the **Get Recurring Sales Lines** action.
4. In the **Recurring Sales Lines** window, choose the lookup button in the **Code** field, and then select a set of standard sales lines.
5. Choose the **OK** button to insert the standard sales lines on the invoice, where you can reuse as is or edit the information.

## To create multiple sales invoices based on standard sales lines
You can use the **Create Recurring Sales Inv.** batch job to create sales invoices according to standard sales lines that are assigned to the customers and with posting dates within the valid-from and valid-to dates that you specify on the standard sales code.

In the **Recurring Sales Lines** window, you can also specify a direct-debit payment method and a direct-debit mandate. The sales invoices that are created with the **Create Recurring Sales Inv.** batch job will then include information required to collect payment for the sales invoices with SEPA direct debit. For more information, see [Collecting Payments with SEPA Direct Debit](finance-collect-payments-with-sepa-direct-debit.md).

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Create Recurring Sales Invoices**, and then choose the related link.
2. In the **Create Recurring Sales Inv.** window, fill in the fields as necessary.
3. In the **Code** field, enter the code for standard sales lines assigned to a customer that you want to create sales invoices for.
4. Choose the **OK** button.

Sales invoices are created for the customers with the specified standard customer sales code, and any specified direct-debit information, for posting on the specified date.

## See Also  
[Sales](sales-manage-sales.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
