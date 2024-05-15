---
title: Payment practices report
description: Learn how to easily create the Payment Practices report for vendors and customers. 
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: payment, practices, vendor, customer, report
ms.search.form: 686, 687, 689 
ms.date: 04/23/2024
ms.author: altotovi
ms.reviewer: bholtorf
--- 

# Payment practices report  

Some countries/regions require that companies report payment times for their vendors as defined by local authorities. This reporting can be based on different sources and can sort vendors based on their size or defined payment terms, providing reporting for vendors for the following as required by local authorities:  

- The average agreed payment period.  
- The average actual payment term.   
- The proportion of invoices paid after the end of the agreed payment period. 

Users can select the period for which they want to run a calculation and to find details based on a grouping that you choose. For each of these groupings, you can find sourced entries. 

> [!NOTE]
> This reporting is so far required in some countries, but this is a global feature and can be used everywhere. Currently, each year Swedish companies with 250 and more employees must report to the Swedish Companies Registration Office what payment times they have for purchases from companies that are smaller than themselves. Similar acts exist in the United Kingdom, Australia, and New Zealand.  

## Generate the report 

To run the **Payment Practices** report, use the following steps:

1. Select the ![Lightbulb that op the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Practices**, and then select the related link. 
2. Select **New**.
3. On the **General** FastTab, enter values in the following fields:

   | Field | Description |
   |---------|-----------------------------------|
   | No. | Specify the number of the entry or record for the report. |
   | Aggregation Type | Specify how data is aggregated. If you choose the option **Period** report will be based on different periods, but if you choose the **Company Size** option report is created based on company sizes configured in the **Company Size Code** field on the **Vendor** card. |
   | Header Type | Specifies the source for entries in the payment practice, and you can choose Vendors, Customers or both. |
   | Starting Date | Specifies the starting date of the payment practice. |
   | Ending Date | Specifies the ending date of the payment practice. |

> [!NOTE]
> If you decide to use the **Company Size** option, you first must create entries in the **Company Sizes** page and to add them to all vendors you want to track by this method.

4. Once when you populate all fields in the header, you need to run the **Generate** action to generate data in the lines and statistics for selected type of reporting.
5. Based on the **Agregation Type** you will get different lines. You can change some of values manually, but in this case each of modified line and the whole report will be marked as **Modified Manually**.
6. From all of calculated fields, you can go deeper to see how this result has been calculated, opening the **Payment Practice Data List** page.
7. If you want to print the document, you can do it by running the **Print** action.

## See also

[Finance reports](finance-reports.md)  
[Analyzing Financial Statements in Microsoft Excel](finance-analyze-excel.md)  
[Accounts Receivable Reports and Analytics](receivables-reports.md)  
[Accounts Payable Reports and Analytics](payables-reports.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Finance](finance.md)  
[Local Functionality Overview](about-localization.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
