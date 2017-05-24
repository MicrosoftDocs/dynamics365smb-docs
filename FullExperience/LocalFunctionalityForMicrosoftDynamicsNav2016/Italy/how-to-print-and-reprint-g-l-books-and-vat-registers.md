---
title: "How to: Print and Reprint G-L Books and VAT Registers"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "registers, VAT"
  - "registers, printing"
  - "VAT register, print"
  - "registers, general ledger"
  - "general ledger book report, printing"
ms.assetid: c94e157f-cae4-44e5-93d6-bc4a95260169
caps.latest.revision: 9
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "it-it"
---
# How to: Print and Reprint G-L Books and VAT Registers
The tax authorities require that you submit two fiscal reports that list all of the posted ledger entries, the **\($ R\_12121 G\/L Book \- Print $\)** report and the **\($ R\_12120 VAT Register \- Print $\)** report. Each printed page must have its own progressive number, and therefore, you must update [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] with the last printed page number before you run these reports again.  
  
 The following procedure describes how to print or reprint the **\($ R\_12121 G\/L Book \- Print $\)** report, but the same steps apply to printing or reprinting the **\($ R\_12120 VAT Register \- Print $\)** report.  
  
### To print the general ledger book report  
  
1.  In the **Search** box, enter **\($ R\_12121 G\/L Book \- Print $\)**, and then choose the related link.  
  
2.  Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_12121\_N\_2\_1130006 Report Type $\)**|Select the type of report to create.<br /><br /> If you select **Reprint**, the **\($ R\_12121\_N\_2\_1130000 From Progressive No. $\)** field becomes enabled.|  
    |**\($ R\_12121\_N\_2\_1130004 Starting Date $\)**|Enter the first date in the period from which posted entries will be shown.|  
    |**\($ R\_12121\_N\_2\_1130002 Ending Date $\)**|Enter the last date in the period from which posted entries will be shown.|  
    |**\($ R\_12121\_N\_2\_1130000 From Progressive No. $\)**|Specifies the progressive number for the report.|  
    |**\($ R\_12121\_N\_2\_1130108 Print Company Information $\)**|Select to print company information on the report.<br /><br /> The remaining fields are populated based on the **\($ N\_1 Company Information $\)** window.|  
  
     When you print the report, you will be reminded to update the **\($ N\_118 General Ledger Setup $\)** window with the page number on the last page.  
  
    > [!IMPORTANT]  
    >  [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] does not save the page number automatically when you run the reports. After you run the **\($ R\_12121 G\/L Book \- Print $\)** report or the **\($ R\_12120 VAT Register \- Print $\)** report, you must update [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] with the last printed page number.  
  
3.  In the **Search** box, enter **\($ N\_118 General Ledger Setup $\)**, and then choose the related link.  
  
     To set the last printed page number for the VAT register report, search for **\($ N\_12151 VAT Register $\)**, and choose the link for the window under **VAT Posting Group**.  
  
4.  In the **Fiscal Reporting** FastTab, in the **\($ T\_98\_12120 Last Printed G\/L Book Page $\)** field, specify the page number that is on the last page of the **\($ R\_12121 G\/L Book \- Print $\)** report that you just printed.  
  
 Both official reports can be reprinted. When you reprint a report, the first page of the report must have the same page number as it did when the report was printed the first time. If you want to reprint one of the reports, and the page number is incorrect, you can change the reprinting information for the report  
  
 The following procedure describes how to view or change the page numbering for previously printed versions of the **\($ R\_12121 G\/L Book \- Print $\)** report, but the same steps apply to the **\($ R\_12120 VAT Register \- Print $\)** report.  
  
### To view or change page numbering for reprinting the general ledger book report  
  
1.  In the **Search** box, enter **\($ N\_118 General Ledger Setup $\)**, and then choose the related link.  
  
2.  On the **Actions** FastTab, in the **Functions** group, choose **Change G\/L Book Reprint Info.**. In the **\($ N\_12149 G\/L Book Reprint Info $\)** window, the **\($ T\_12149\_5 First Page Number $\)** field specifies the first page number of the previously printed reports.  
  
 When you update the **\($ N\_118 General Ledger Setup $\)** window or the **\($ N\_12151 VAT Registers $\)** window with the page number of the last page of the printed report, make sure that you specify the correct page number. If the reprinted report starts with the wrong page number, the report will not be accepted by the tax authorities. The **\($ N\_12149 G\/L Book Reprint Info $\)** window and the **\($ N\_12150 VAT Register Reprint Info $\)** can help you identify the correct page number.  
  
## See Also  
 [\($ R\_12121 G\-L Book \- Print $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/-$-r_12121-g-l-book-print-$-.md)   
 [\($ R\_12120 VAT Register \- Print $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/-$-r_12120-vat-register-print-$-.md)   
 [\($ N\_12149 G\-L Book Reprint Info $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/-$-n_12149-g-l-book-reprint-info-$-.md)   
 [\($ N\_12150 VAT Register Reprint Info $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/-$-n_12150-vat-register-reprint-info-$-.md)