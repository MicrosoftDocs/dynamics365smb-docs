---
title: Print and Reprint G/L Books and VAT Registers for Italy
description: Learn how to print and reprint the G/L Book - Print and VAT Fiscal Register - Print reports, and maintain their page numbers in Business Central for Italy.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: print GL books, reprint GL books, VAT registers, Italian version
ms.search.form: 12141, 12143, 12149, 12150
ms.date: 10/21/2026
ms.author: bholtorf
ms.custom: bap-template
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Print and reprint GL books and VAT registers in the Italian version

The tax authorities require that you submit two fiscal reports that list all of the posted ledger entries, the **G/L Book - Print** report and the **VAT Fiscal Register - Print** report. Each printed page must have its own progressive number, and therefore, you must update [!INCLUDE[prod_short](../../includes/prod_short.md)] with the last printed page number before you run these reports again.

## Print the general ledger book report

Use **G/L Book - Print** for the general ledger book. The VAT register report has a separate request page, described later in this article.

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **G/L Book - Print**, and then choose the related link.  
1. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Report Type**|Select the type of report to create.<br><br/> If you select **Reprint**, the **From Progressive No.** field becomes enabled.|  
    |**Starting Date**|Enter the first date in the period from which posted entries are shown.|  
    |**Ending Date**|Enter the last date in the period from which posted entries are shown.|  
    |**From Progressive No.**|Specifies the progressive number for the report.|  
    |**Print Company Informations**|Select to print company information on the report.<br><br/> The remaining fields are populated based on the **Company Information** page.|

1. Choose **Print** to run the report. For **Final Print**, you're reminded to update **General Ledger Setup** with the last printed page number.

    > [!IMPORTANT]  
    > [!INCLUDE[prod_short](../../includes/prod_short.md)] doesn't save the last printed page number automatically. Update that number after a final print, not after a test print or preview.

1. After a final print, [!INCLUDE [open-search-lowercase](../../includes/open-search-lowercase.md)], enter **General Ledger Setup**, and then choose the related link.

1. In the **Fiscal Reporting** FastTab > **Last Printed G/L Book Page** field, specify the page number that is on the last page of the **G/L Book - Print** report that you printed.  

## Print a VAT register

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **VAT Fiscal Register - Print**, and then choose the related link.
1. Select **VAT Register**, **Period Starting Date**, and **Period Ending Date**.
1. Set **Printing Type** to **Test**, **Final**, or **Reprint**. Review **Print Company Informations** and the company details.
1. Choose **Print** to run the report.
1. After a final print, open **VAT Register**, select the register, and update **Last Printed VAT Register Page** with the number on the last printed page.

Both official reports can be reprinted. When you reprint a report, the first page must have the same page number as the original printout. If the page number is incorrect, change the reprinting information before you reprint the report.

## View or change page numbers for reprinting the general ledger book report

Use the general ledger setup for G/L book reprints and the VAT register for VAT register reprints.

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **General Ledger Setup**, and then choose the related link.  
1. Choose **Change Reprinting Information for G/L Books**. On **G/L Book Reprinting Information**, review or correct **First Page Number** for the relevant date range.
1. For a VAT register, open **VAT Register**, select the register, and choose **Change Reprinting Information**. Review or correct **First Page Number** on **VAT Register Reprinting Information**.

When you update the last printed page number on **General Ledger Setup** or **VAT Register**, check it against the printed report. Use **G/L Book Reprinting Information** or **VAT Register Reprinting Information** to check the starting number for a reprint.

## Related information  

[Italy Local Functionality](italy-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
