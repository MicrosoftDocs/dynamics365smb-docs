---
title: "How to: Print VAT Audit Reports"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "VAT Entry Exception report"
  - "VAT Audit report"
  - "audit files, reports"
ms.assetid: 9739f057-879b-4004-9730-21634cae65d5
caps.latest.revision: 33
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "en-gb"
---
# How to: Print VAT Audit Reports
All vendors must export the data required for auditing in a Content Separated Value \(CSV\) file format. The following reports comply with this requirement:  
  
-   **VAT Audit**  report – This report is used for VAT auditing.  
  
-   **VAT Entry Exception** report \- This report details the differences between the calculated VAT and the changes that occur because of rounding, VAT tolerance percentage, and discounts. It also displays the difference in VAT amounts for the tax authorities.  
  
### To print the VAT audit report  
  
1.  In the **Search** box, enter **VAT Audit**, and then choose the related link.  
  
2.  In the **VAT Audit** window, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Export Customers**|Select to export the file to the **Customer** table.|  
    |**Export Open Payments**|Select to export the open credit entries.|  
    |**Export Late Invoicing**|Select to export customer entries that took longer to invoice than the number of days specified in the **Late Invoice Delay \(Days\)** field.|  
    |**Late Invoice Delay \(Days\)**|Enter the number of days between the invoice issue date and the payment received date. If the **Export Late Invoicing** field is selected, entries exceeding this limit will be exported.|  
    |**Export Vendors**|Select to export the file to the **Vendor** table.|  
    |**Export VAT Entries**|Select to export the entries in the **VAT Entry** table.|  
  
    > [!NOTE]  
    >  You must select at least one check box in this window.  
  
3.  To export the file, choose the **OK** button.  
  
     The VAT audit information is exported. You can save the data to a file, or open the file in the appropriate program.  
  
### To print the VAT entry exception report  
  
1.  In the **Search** box, enter **VAT Entry Exception Report**, and then choose the related link.  
  
2.  In the **VAT Entry Exception Report** window, on the **Options** FastTab, fll in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**VAT Base Discount**|Select if you want to enter a value in the **VAT Base Discount %** field.|  
    |**Manual VAT Difference**|Select if you want to enter a value in the **Manual VAT Difference** field.|  
    |**VAT Calculation Types**|Select to determine the VAT calculation type.|  
    |**VAT Rate**|Select to determine the VAT rate for a particular journal line.|  
    |**VAT Base Discount %**|Enter a value in this field if you have selected the **VAT Base Discount** field.|  
    |**Manual VAT Difference**|Enter a value in this field if you have selected the **Manual VAT Difference** field.|  
    |**VAT Rate % Difference**|Specify the maximum VAT rate difference.|  
  
    > [!NOTE]  
    >  You must select at least one check box in this window.  
  
3.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  
  
## See Also  
 [VAT Audit](../../LocalFunctionalityForMicrosoftDynamicsNav2016/UnitedKingdom/-$-b_10512-vat-audit-$-.md)   
 [VAT Entry Exception](../../LocalFunctionalityForMicrosoftDynamicsNav2016/UnitedKingdom/-$-r_10511-vat-entry-exception-$-.md)   
 [VAT Exception](../Topic/\($%20R_31%20VAT%20Exception%20$\).md)   
 [United Kingdom Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/UnitedKingdom/united-kingdom-local-functionality.md)