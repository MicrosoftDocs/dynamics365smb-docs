---
title: Set up and Print Intrastat Reports for Italy
description: Learn how to set up and print monthly or quarterly Intrastat reports, and submit them to authorities in the Italian version of Business Central.
author: brentholtorf
ms.topic: article
ms.search.keywords: set up intrastat reports, print intrastat reports, submit intrastat reports, corrective Intrastat report, Italian version
ms.date: 05/21/2025
ms.search.form: 12116
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
ms.custom: bap-template
---

# Set up and print Intrastat reports for Italy

> [!NOTE]
> This article is based on new redesigned Intrastat experience with enhanced features available from the 2022 release wave 2. If you're using old functionality based on Intrastat journals, learn more about old Intrastat experience in [Print Intrastat for Italy](intrastat-for-italy-old.md). The old feature isn't available in [!INCLUDE [prod_short](../../includes/prod_short.md)] online.

You can print monthly and quarterly Intrastat reports and submit them to the authorities on a diskette by running the **Intrastat Make Disk Tax Auth** batch job. Information regarding the receipt and the delivery of goods is included automatically.  

## Set up Intrastat reporting

Learn more in [Set up Intrastat reporting](../../finance-how-setup-report-intrastat.md).

## Work with Intrastat reporting

Learn more in [Work with Intrastat reporting](../../finance-how-report-intrastat.md).

## Local Italian functionalities

### Additional parameters

When you create new a **Intrastat Report**, you need to make another setup at the **Export Parameters** FastTab. You can choose the period for reporting choosing one of the following options at the **Periodicity** field: Month, Quarter, Year. You can also choose the **Type** - Purchases or Sales, to choose the type of item ledger entries to be included.  

You also need to enter the **File Disk No.** to specify the floppy disk number if you're creating a reporting disk. If you want to specify whether to include intra-community entries from drop shipment documents to **Intrastat Report**, you need to mark the **Include Intra-Community Entries** field.

> [!NOTE]  
> Before you print, you can select the path and file name. If you don't specify this information, the file is named **scambi.cee** and prints to the root of the C drive.  

### Corrective Intrastat report

A corrective Intrastat report in Italy is a declaration submitted to correct errors or make adjustments to previously filed Intrastat reports.

To prepare corrective intrastat report, you previously must post the credit memo, and it must be applied to the posted invoice. Corrective credit memo can't be in the same period as original invoice.  

If you already posted and applied documents, you can prepare a new Intrastat report and mark the **Corrective Entry** field to specify if the Intrastat report has an adjusting entry, and also populate the **Corrected Intrastat Report No.** field to specify the corrected report.  

## Related information

- [Italy Local Functionality](italy-local-functionality.md)  
- [Set Up Intrastat Reporting](../../finance-how-setup-report-intrastat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
