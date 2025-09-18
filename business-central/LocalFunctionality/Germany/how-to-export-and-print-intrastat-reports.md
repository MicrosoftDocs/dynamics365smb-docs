---
title: Export and Print Intrastat Reports (DE)
description: Business Central supports Intrastat reporting according to German requirements. You can meet the requirement to report your trade with other EU countries/regions.
author: brentholtorf 
ms.topic: how-to
ms.devlang: al
ms.search.keywords: intrastat reporting, print intrastat reports, export intrastat reports, German version
ms.search.form: 26100
ms.date: 04/24/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Export and print Intrastat reports

> [!NOTE]
> This article explains the old Intrastat Journals functionality, which is now deprecated.

[!INCLUDE[intrastat-2022w2](../../includes/intrastat-2022w2.md)]

Intrastat reporting is required throughout the European Union (EU) and must follow local requirements, such as specific formats and files. All companies in the EU must report their trade with other EU countries/regions. The movement of goods must be reported to the statistics authorities (Statistisches Bundesamt) every month, and a report must be delivered to the tax authorities.  

For Intrastat reporting, you must provide paper reports and files, which must be in ASCII format for Germany. [!INCLUDE[prod_short](../../includes/prod_short.md)] includes reports and batch jobs that generate all of the information that must be sent to the German tax authorities. This information automatically includes both receipt and delivery of goods. The Intrastat file contains information from the lines in the **Intrastat** journal.  

## Deprecated Intrastat functionality

This article provides details about the deprecated Intrastat Journals functionality. Learn more in [Set up Intrastat reporting](../../finance-how-setup-report-intrastat.md), which provides information about the updated version of Intrastat.

### Print the German Intrastat checklist  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journals**, and then choose the related link.  
1. In the **Batch Name** field, select the required journal batch name.
1. Choose the **Checklist Report** action.  
1. On the **Intrastat - Checklist DE** page, on the **Options** FastTab, select the **Show Intrastat Journal Lines** checkbox.  

    > [!IMPORTANT]  
    > If you clear the **Show Intrastat Journal Lines** checkbox, the report displays only the information that must be reported to the tax authorities, and not the lines in the journal.  

1. Optionally, on the **Intrastat Jnl. Batch** FastTab, select the appropriate filters.  
1. Optionally, on the **Intrastat Jnl. Line** FastTab, select the appropriate filters.  
1. Choose the **Print** button to print the Intrastat checklist or choose the **Preview** button to view it on the screen.  

### Print the German Intrastat form  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journals**, and then choose the related link.  
1. In the **Batch Name** field, select the required journal batch name.  
1. Choose the **Form** action.  
1. Optionally, on the **Intrastat Jnl. Batch** FastTab, select the appropriate filters.  
1. Optionally, on the **Intrastat Jnl. Line** FastTab, select the appropriate filters.  
1. Choose the **Print** button to print the Intrastat checklist or choose the **Preview** button to view it on the screen.  

### Export Intrastat information to a disk  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journals**, and then choose the related link.  
1. In the **Batch Name** field, select the required journal batch name.  
1. Choose the **Make Diskette** action.  
1. On the **Options** FastTab, in the **Path** field, enter the full path and the name of the file to which you want to write the information.  

   Optionally, on the **Intrastat Jnl. Batch** FastTab, select the appropriate filters.  

1. To export the file, choose the **OK** button.  

The Intrastat information is exported, and you can either save the data to a file, or you can open the file in the appropriate program.  

When the file is exported, the **Reported** checkbox on the **Intrastat Jnl. Batches** page is selected, and the **Internal Ref. No.** field on every entry in the journal is filled in. You can manually change the contents of the field. For example, you can make changes when you need to run the report again.

## Related information

- [VAT Reporting](vat-reporting.md)  
- [Report VAT to Tax Authorities](../../finance-how-report-vat.md)
- [Export and Print Intrastat Reports](how-to-export-and-print-intrastat-reports.md)  
- [Germany Local Functionality](germany-local-functionality.md)  
- [Set Up Intrastat Reporting](../../finance-how-setup-report-intrastat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
