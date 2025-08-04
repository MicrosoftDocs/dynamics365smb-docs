---
title: Print Intrastat Reports for Italy - Deprecated feature
description: Learn how to print and submit monthly and quarterly Intrastat reports to the Italian authorities on a diskette by running the Intrastat Make Disk Tax Auth batch job.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: monthly intrastat report, quarterly intrastat report, print intrastat reports, submit intrastat reports, intrastat checklist, intrastat form, Italian version
ms.date: 05/22/2025
ms.search.form: 12116
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Print Intrastat reports for Italy - Deprecated feature

[!INCLUDE[intrastat-2022w2](../../includes/intrastat-2022w2.md)]

You can print monthly and quarterly Intrastat reports and submit them to the authorities on a diskette by running the **Intrastat Make Disk Tax Auth** batch job. Information regarding the receipt and the delivery of goods is included automatically.  

The following Intrastat reports are available:  

- **Intrastat - Checklist** report  
- **Intrastat - Form** report  

## Print quarterly or monthly reports  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journals**, and then choose the related link.  
1. Select the required journal batch.  
1. To open the **Intrastat - Monthly** report or the **Intrastat - Quarterly** report, choose the **Monthly Report** action or the **Quarterly Report** action.  
1. On the **Intrastat Jnl. Line** FastTab, select the appropriate filters.  
1. Choose the **Print** button to print the report, or choose the **Preview** button to view it on the screen.  
1. On the **Intrastat Journal** page, to save the report details to a diskette, choose the **Make Diskette** action.  

    > [!NOTE]  
    > Before you print, you can select the path and file name. If you don't specify this information, the file is named **scambi.cee** and prints to the root of the C drive.  

## Print Intrastat - Checklist reports  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat - Checklist**, and then choose the related link.  
1. On the **Options** FastTab, select the **Show Intrastat Journal Lines** checkbox to include detailed information about the journal lines in the report.  
1. On the **Intrastat Jnl. Batch** and **Intrastat Jnl. Line** FastTabs, select the appropriate filters.  
1. Choose the **Print** button to print the report, or choose the **Preview** button to view it on the screen.  

## Print Intrastat - Form reports  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat - Form**, and then choose the related link.  
1. On the **Intrastat Jnl. Batch** and **Intrastat Jnl. Line** FastTabs, select the appropriate filters.  
1. Choose the **Print** button to print the report, or choose the **Preview** button to view it on the screen.  

## Related information

- [Set Up Journal Templates and Batches](how-to-set-up-journal-templates-and-batches.md)  
- [Italy Local Functionality](italy-local-functionality.md)  
- [Set Up Intrastat Reporting](../../finance-how-setup-report-intrastat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
