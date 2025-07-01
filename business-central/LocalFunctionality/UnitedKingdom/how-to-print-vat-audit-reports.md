---
title: Print VAT Audit Reports
description: Learn how Business Central supports the British requirements for VAT audits.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: VAT audits
ms.search.form: 317, 320
ms.date: 02/19/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramni
---

# Print VAT Audit reports in the British version

In the United Kingdom, all vendors must export the data required for auditing in a Content Separated Value (CSV) file format. The following reports in the British version of [!INCLUDE [prod_short](../../includes/prod_short.md)] comply with this requirement:  

- **VAT Audit**  report – This report is used for VAT auditing.  
- **VAT Entry Exception** report - This report details the differences between the calculated VAT and the changes that occur because of rounding, VAT tolerance percentage, and discounts. It also displays the difference in VAT amounts for the tax authorities.  

## Print the VAT Audit report  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Statements**, and then choose the related link.  
1. Choose the relevant VAT statement template, and then choose **OK**.
1. On the **VAT Statement** page, choose **VAT Audit Report**.
1. On the **VAT Audit** page, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |-----|-----------|  
    |**Export Customers**|Select to export the file to the **Customer** table.|  
    |**Export Open Payments**|Select to export the open credit entries.|  
    |**Export Late Invoicing**|Select to export customer entries that took longer to invoice than the number of days specified in the **Late Invoice Delay (Days)** field.|  
    |**Late Invoice Delay (Days)**|Enter the number of days between the invoice issue date and the payment received date. If the **Export Late Invoicing** field is selected, entries exceeding this limit are exported.|  
    |**Export Vendors**|Select to export the file to the **Vendor** table.|  
    |**Export VAT Entries**|Select to export the entries in the **VAT Entry** table.|  

    > [!NOTE]  
    > You must select at least one checkbox in this page.  

1. To export the file, choose the **OK** button.  

    The VAT audit information is exported. You can save the data to a file, or open the file in the appropriate program.  

## Print the VAT Entry Exception report  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Statements**, and then choose the related link.  
1. Choose the relevant VAT statement template, and then choose **OK**.
1. On the **VAT Statement** page, choose **VAT Entry Exception Report**.  
1. On the **VAT Entry Exception Report** page, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**VAT Base Discount**|Select if you want to enter a value in the **VAT Base Discount %** field.|  
    |**Manual VAT Difference**|Select if you want to enter a value in the **Manual VAT Difference** field.|  
    |**VAT Calculation Types**|Select to determine the VAT calculation type.|  
    |**VAT Rate**|Select to determine the VAT rate for a particular journal line.|  
    |**VAT Base Discount %**|Enter a value in this field if you selected the **VAT Base Discount** field.|  
    |**Manual VAT Difference**|Enter a value in this field if you selected the **Manual VAT Difference** field.|  
    |**VAT Rate % Difference**|Specify the maximum VAT rate difference.|  

    > [!NOTE]  
    > You must select at least one checkbox in this page.  

1. Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  

## See also

- [Work with Reports, Batch Jobs, and XMLports](../../ui-work-report.md)  
- [Report VAT to Tax Authorities](../../finance-how-report-vat.md)  
- [United Kingdom Local Functionality](united-kingdom-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
