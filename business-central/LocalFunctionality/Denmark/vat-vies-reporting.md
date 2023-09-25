---
title: VAT-VIES Reporting [DK]
description: You can create the required VAT declarations for trade of goods or services file in the Danish version by using the EC Sales List report.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form:
ms.date: 05/09/2022
ms.author: bholtorf

---
# VAT-VIES Reporting in the Danish Version

Danish companies must submit VAT declarations for trade of goods or services with other EU countries/regions. You can create the required file by using the **EC Sales List** report.  

## Set up VAT registration numbers

To report VAT-VIES correctly, you must enter a plain VAT registration number in the **VAT Registration No.** on **Customer** and **Vendor** cards. That means you cannot add country codes or other shortcuts since the VAT-VIES reporting requires plain VAT number for clients. It's different for Intrastat, so you can set up exactly how you want VAT registration numbers to be generated for Intrastat in the **Intrastat Setup** page. For more information, see [VAT Registration Number Setup for Intrastat](vat-registration-no-intrastat.md).  

## Reporting EU Sales

In order to track VAT for the trade of goods or services between EU countries/regions, you must submit information about this trade to the Danish Listesystem. The **EC Sales List** report creates a file that you can then upload to the tax authorities at the [www.skat.dk](https://go.microsoft.com/fwlink/?LinkId=212340) site. Before you create the file, you can verify your customers’ VAT registration number online. The tax authorities also recommend that you do not submit large files to the online portal. If your declaration consists of more than 1,000 lines, it is recommended that you submit several smaller files instead. For more information, see the tax authorities’ [website](https://www.skat.dk).  

[!INCLUDE [finance-ecsaleslist](../../includes/finance-ecsaleslist.md)]

## See Also

[About the EC Sales List Report](../../finance-how-report-vat.md#ecsaleslist)  
[Report VAT to Tax Authorities](../../finance-how-report-vat.md)  
[Denmark Local Functionality](denmark-local-functionality.md)  
[Print VAT Reconciliation Reports](how-to-print-vat-reconciliation-reports.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
