---
    title: How to Print VAT Audit Reports | Microsoft Docs
    description: All vendors must export the data required for auditing in a Content Separated Value (CSV) file format.
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
# Print VAT Audit Reports
All vendors must export the data required for auditing in a Content Separated Value (CSV) file format. The following reports comply with this requirement:  

-   **VAT Audit**  report – This report is used for VAT auditing.  
-   **VAT Entry Exception** report - This report details the differences between the calculated VAT and the changes that occur because of rounding, VAT tolerance percentage, and discounts. It also displays the difference in VAT amounts for the tax authorities.  

## To print the VAT audit report  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Audit**, and then choose the related link.  
2.  On the **VAT Audit** page, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Export Customers**|Select to export the file to the **Customer** table.|  
    |**Export Open Payments**|Select to export the open credit entries.|  
    |**Export Late Invoicing**|Select to export customer entries that took longer to invoice than the number of days specified in the **Late Invoice Delay (Days)** field.|  
    |**Late Invoice Delay (Days)**|Enter the number of days between the invoice issue date and the payment received date. If the **Export Late Invoicing** field is selected, entries exceeding this limit will be exported.|  
    |**Export Vendors**|Select to export the file to the **Vendor** table.|  
    |**Export VAT Entries**|Select to export the entries in the **VAT Entry** table.|  

    > [!NOTE]  
    >  You must select at least one check box in this page.  

3.  To export the file, choose the **OK** button.  

    The VAT audit information is exported. You can save the data to a file, or open the file in the appropriate program.  

## To print the VAT entry exception report  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Entry Exception Report**, and then choose the related link.  
2.  On the **VAT Entry Exception Report** page, on the **Options** FastTab, fll in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**VAT Base Discount**|Select if you want to enter a value in the **VAT Base Discount %** field.|  
    |**Manual VAT Difference**|Select if you want to enter a value in the **Manual VAT Difference** field.|  
    |**VAT Calculation Types**|Select to determine the VAT calculation type.|  
    |**VAT Rate**|Select to determine the VAT rate for a particular journal line.|  
    |**VAT Base Discount %**|Enter a value in this field if you have selected the **VAT Base Discount** field.|  
    |**Manual VAT Difference**|Enter a value in this field if you have selected the **Manual VAT Difference** field.|  
    |**VAT Rate % Difference**|Specify the maximum VAT rate difference.|  

    > [!NOTE]  
    >  You must select at least one check box in this page.  

3.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  

## See Also  
[United Kingdom Local Functionality](united-kingdom-local-functionality.md)
