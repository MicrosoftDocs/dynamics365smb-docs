---
title: Print VAT Audit Reports in the United Kingdom
description: Print the VAT Audit and VAT Entry Exception reports in the British version of Business Central to review posted VAT entries and identify differences.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: VAT audits
ms.search.form: 317, 320
ms.date: 10/19/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Print VAT audit reports in the British version

In the United Kingdom, all vendors must export the data required for auditing in a comma-separated values (CSV) file format. The following reports in the British version of [!INCLUDE [prod_short](../../includes/prod_short.md)] comply with this requirement:

- **VAT Audit**  report – This report is used for VAT auditing.  
- **VAT Entry Exception** report - This report details the differences between the calculated VAT and the changes that occur because of rounding, VAT tolerance percentage, and discounts. It also displays the difference in VAT amounts for the tax authorities.  

## Print the VAT audit report

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **VAT Statements**, and then choose the related link.
1. Choose the relevant VAT statement template, and then choose **OK**.
1. On the **VAT Statement** page, choose **VAT Audit Report**.
1. On the **VAT Audit** page, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |-----|-----------|  
    |**Export Customers**|Select to export customer numbers, names, and addresses from the **Customer** table.|
    |**Export Open Payments**|Select to export open customer credit entries.|
    |**Export Late Invoicing**|Select to export customer entries that took longer to invoice than the number of days specified in the **Late Invoice Delay (Days)** field.|  
    |**Late Invoice Delay (Days)**|Enter the maximum number of days between a customer's payment posting date and the related invoice posting date. If **Export Late Invoicing** is selected, entries exceeding this limit are exported. The value must be greater than zero.|
    |**Export Vendors**|Select to export vendor numbers, names, and addresses from the **Vendor** table.|
    |**Export VAT Entries**|Select to export entries from the **VAT Entry** table. Use the **VAT Reporting Date** and **Posting Date** filters to limit the entries.|

    > [!NOTE]  
    > You must select at least one checkbox in this page.  

1. To export the file, choose the **OK** button.  

    The VAT audit information is exported. You can save the data to a file, or open the file in the appropriate program.  

## Print the VAT entry exception report

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **VAT Statements**, and then choose the related link.
1. Choose the relevant VAT statement template, and then choose **OK**.
1. On the **VAT Statement** page, choose **VAT Entry Exception Report**.  
1. On the **VAT Entry Exception Report** page, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**VAT Base Discount**|Select to check for VAT base discounts that exceed **VAT Base Discount %**.|
    |**Manual VAT Difference** under **Check**|Select to check for manual VAT differences that exceed the maximum **Manual VAT Difference** amount.|
    |**VAT Calculation Types**|Select to compare the VAT calculation type on entries with VAT posting setup.|
    |**VAT Rate**|Select to check for VAT rate differences that exceed **VAT Rate % Difference**.|
    |**VAT Base Discount %**|Specify the maximum VAT base discount percentage. The initial value comes from **VAT Tolerance %** on **General Ledger Setup**.|
    |**Manual VAT Difference** under **Maximum**|Specify the maximum manual VAT difference. The initial value comes from **Max. VAT Difference Allowed** on **General Ledger Setup**.|
    |**VAT Rate % Difference**|Specify the maximum VAT rate difference. If no value is set, the report initially uses 0.1.|

    > [!NOTE]  
    > You must select at least one checkbox in this page.  

1. Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  

## Related information

- [Work with Reports, Batch Jobs, and XMLports](../../ui-work-report.md)  
- [Report VAT to Tax Authorities](../../finance-how-report-vat.md)  
- [United Kingdom Local Functionality](united-kingdom-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
