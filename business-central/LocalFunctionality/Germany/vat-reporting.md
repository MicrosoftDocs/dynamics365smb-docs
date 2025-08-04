---
title: VAT Reporting in the German version
description: You can report VAT electronically to the tax authorities in the German version.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: report VAT electronically, VAT reporting, VAT declaration, VAT statement, German version
ms.search.form: 11016, 11017, 11019, 11025, 11026, 11027, 11028
ms.date: 03/12/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# VAT reporting in the German version

You can report VAT to the German tax authorities on the Elektronische Steuererklärungen (ELSTER) online portal. You can generate and export your VAT declaration as an XML file that you send to the German ELSTER portal. Learn more in [Sales VAT Advance Notifications](how-to-set-up-and-export-sales-vat-advance-notifications.md).  

You can print the following local VAT reports.  

|Report|Description|  
|------------|---------------------------------------|  
|**VAT Statement Germany**|A simple VAT report. The main VAT reporting is handled by the ELSTER functionality. The amounts are differentiated by taxable base and taxable amount.<br><br/> Serves as the basis for VAT registration for a selected period, and is printed according to the VAT statement in the VAT Statement Line table. Use the **Period Date Type** to specify the type of date used for the period from which VAT entries are processed in the batch job. Based on your choice, the statement can be based on **Posting Date**, **Document Date**, or **VAT Date**.<br><br/> Use this report together with VAT corrections.|  
|**Sales VAT Adv. Not. Acc. Proof**|Confirms that entries in the VAT statement form are also posted in general ledger accounts.<br><br/> To verify VAT in sales VAT advance notifications, select the same settings for the VAT statement form and the sales VAT advance notification.|  
|**VAT Statement Schedule**|This report can be retrieved from the **VAT Statement** page.<br><br/> Prints the settings in the VAT statement. Using this report, you can print the characteristics of the **Sales VAT Adv. Not. Acc. Proof**.|  

## Related information

- [Sales VAT Advance Notifications](how-to-set-up-and-export-sales-vat-advance-notifications.md)  
- [Report VAT to the Tax Authorities](../../finance-how-report-vat.md)  
- [Work with VAT on Sales and Purchases](../../finance-work-with-vat.md)  
- [Set Up Reports for VAT and Intrastat](how-to-set-up-reports-for-vat-and-intrastat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
