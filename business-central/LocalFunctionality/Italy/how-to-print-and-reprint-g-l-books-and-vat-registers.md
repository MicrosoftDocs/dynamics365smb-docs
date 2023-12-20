---
title: Print and reprint G-L books VAT registers [IT]
description: Tax authorities require that you submit two fiscal reports that list all posted ledger entries, the G/L Book - Print report and the VAT Register - Print report.
author: brentholtorf
ms.topic: conceptual
ms.search.keywords:
ms.search.form: 12141, 12143, 12149, 12150
ms.date: 11/29/2023
ms.author: bholtorf
ms.custom: bap-template
---
# Print and reprint GL books and VAT registers in the Italian version

The tax authorities require that you submit two fiscal reports that list all of the posted ledger entries, the **G/L Book - Print** report and the **VAT Register - Print** report. Each printed page must have its own progressive number, and therefore, you must update [!INCLUDE[prod_short](../../includes/prod_short.md)] with the last printed page number before you run these reports again.  

The following procedure describes how to print or reprint the **G/L Book - Print** report, but the same steps apply to printing or reprinting the **VAT Register - Print** report.  

## To print the general ledger book report  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **G/L Book - Print**, and then choose the related link.  
2. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Report Type**|Select the type of report to create.<br /><br /> If you select **Reprint**, the **From Progressive No.** field becomes enabled.|  
    |**Starting Date**|Enter the first date in the period from which posted entries are shown.|  
    |**Ending Date**|Enter the last date in the period from which posted entries are shown.|  
    |**From Progressive No.**|Specifies the progressive number for the report.|  
    |**Print Company Information**|Select to print company information on the report.<br /><br /> The remaining fields are populated based on the **Company Information** page.|  

    When you print the report, you are reminded to update the **General Ledger Setup** page with the page number on the last page.  

    > [!IMPORTANT]  
    >  [!INCLUDE[prod_short](../../includes/prod_short.md)] does not save the page number automatically when you run the reports. After you run the G/L Book - Print report or the VAT Register - Print report, you must update [!INCLUDE[prod_short](../../includes/prod_short.md)] with the last printed page number..  

3. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.  

    To set the last printed page number for the VAT register report, search for **VAT Register**, and choose the link for the page under **VAT Posting Group**.  

4. In the **Fiscal Reporting** FastTab, in the **Last Printed G/L Book Page** field, specify the page number that is on the last page of the **G/L Book - Print** report that you printed.  

Both official reports can be reprinted. When you reprint a report, the first page of the report must have the same page number as it did when the report was printed the first time. If you want to reprint one of the reports, and the page number is incorrect, you can change the reprinting information for the report  

The following procedure describes how to view or change the page numbering for previously printed versions of the **G/L Book - Print** report, but the same steps apply to the **VAT Register - Print** report.  

## To view or change page numbers for reprinting the general ledger book report  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.  
2. Choose the **Change G/L Book Reprint Info.** action. On the **G/L Book Reprint Info** page, the **First Page Number** field specifies the first page number of the previously printed reports.  

When you update the **General Ledger Setup** page or the **VAT Registers** page with the page number of the last page of the printed report, make sure that you specify the correct page number. If the reprinted report starts with the wrong page number, the tax authorities won't accept the report. The **G/L Book Reprint Info** page and the **VAT Register Reprint Info** can help you identify the correct page number.  

## See also  

[Italy Local Functionality](italy-local-functionality.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]