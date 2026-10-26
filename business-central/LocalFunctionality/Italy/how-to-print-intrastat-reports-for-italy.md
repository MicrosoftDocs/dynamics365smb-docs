---
title: Set Up and Print Intrastat Reports for Italy
description: Learn how to set up and print monthly or quarterly Intrastat reports, and submit them to authorities in the Italian version of Business Central.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: set up intrastat reports, print intrastat reports, submit intrastat reports, corrective Intrastat report, Italian version
ms.date: 10/20/2026
ms.search.form: 12116
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ms.custom: bap-template
ai-usage: ai-assisted
---

# Set up and print Intrastat reports for Italy

> [!NOTE]
> This article is based on new redesigned Intrastat experience with enhanced features available from the 2022 release wave 2. If you're using old functionality based on Intrastat journals, learn more about old Intrastat experience in [Print Intrastat for Italy](intrastat-for-italy-old.md). The old feature isn't available in [!INCLUDE [prod_short](../../includes/prod_short.md)] online.

Use **Intrastat Report** to prepare goods declarations and export an electronic file. The Italian export supports monthly and quarterly purchase or sales reports. You can download the file and submit it through the process required by the authorities.

## Set up Intrastat reporting

Learn more in [Set up Intrastat reporting](../../finance-how-setup-report-intrastat.md).

## Work with Intrastat reporting

Learn more in [Work with Intrastat reporting](../../finance-how-report-intrastat.md).

## Local Italian functionalities

### Additional parameters

On the **Intrastat Report** page, fill in the **Export Parameters** FastTab. Set **Periodicity** to **Month** or **Quarter** for the Italian electronic export. Although **Year** is also shown in the field, the Italian export configuration provides monthly and quarterly formats. Set **Type** to **Purchases** or **Sales**.

Enter **File Disk No.**, which is included as an identifier in the exported header. Select **Include Intra-Community Entries** if the report must include intra-community entries from drop shipment documents.

> [!NOTE]  
> The Italian export uses the default file name `scambi.cee`. The file is downloaded through your browser; the export doesn't write it to the root of the C drive.

### Corrective Intrastat report

A corrective Intrastat report in Italy is a declaration submitted to correct errors or make adjustments to previously filed Intrastat reports.

To prepare corrective intrastat report, you previously must post the credit memo, and it must be applied to the posted invoice. Corrective credit memo can't be in the same period as original invoice.  

After you post and apply the documents, create a new Intrastat report and select **Corrective Entry**. In **Corrected Intrastat Report No.**, select the original report. The original must be reported, must not itself be corrective, and must have the same **Type** and **Periodicity**.

## Related information

- [Italy Local Functionality](italy-local-functionality.md)  
- [Set Up Intrastat Reporting](../../finance-how-setup-report-intrastat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
