---
title: Export and Print Intrastat Reports (DE)
description: Learn how to verify, export, and submit Intrastat reports for Germany, including the IDEV and eSTATISTIK.CORE submission channels.
author: brentholtorf 
ms.topic: how-to
ms.devlang: al
ms.search.keywords: intrastat reporting, print intrastat reports, export intrastat reports, German version
ms.date: 10/09/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Export and print Intrastat reports

[!INCLUDE[intrastat-2022w2](../../includes/intrastat-2022w2.md)]

> [!NOTE]
> The old **Intrastat Journals** functionality, and the standalone **Intrastat - Checklist DE**, **Form**, and **Make Diskette** actions described in earlier versions of this article, are no longer available. Use the **Intrastat Report** page and its **Checklist Report** and **Create File** actions instead, as described in this article.

Intrastat reporting is required throughout the European Union (EU) and must follow local requirements, such as specific formats and files. All companies in the EU must report their trade with other EU countries/regions. The movement of goods must be reported to the statistics authorities (Statistisches Bundesamt) every month.

For the German version, Intrastat reports are submitted in XML format, using one of two submission channels: **IDEV** or **eSTATISTIK.CORE**. Depending on the channel, you might also need to set up a company or material number on the **Company Information** page. Learn more in [Set up reports for VAT and Intrastat](how-to-set-up-reports-for-vat-and-intrastat.md).

## Verify an Intrastat report before you export it

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Report List**, and then choose the related link.  
1. Open the Intrastat report that you want to verify.  
1. Choose the **Checklist Report** action.  
1. Review the errors and warnings shown in the **Error Messages** FactBox, and fix any lines that are missing required information.  

## Export an Intrastat report for Germany

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Report List**, and then choose the related link.  
1. Open the Intrastat report that you want to export.  
1. On the **Export Parameters** FastTab, in the **Submission Channel** field, choose **IDEV** or **eSTATISTIK.CORE**.

    This field defaults to the **Default Submission Channel** set up on the **Intrastat Report Setup** page.

    > [!IMPORTANT]
    > If you choose the **IDEV** channel, you must enter a material number in the **Company No./Material No. (XML)** field on the **Company Information** page. The **eSTATISTIK.CORE** channel doesn't require this field.

1. If you want the exported XML file to be used for a test submission only, select the **Test Submission** field.  
1. Choose the **Create File** action to generate and export the XML file.  

## Related information

- [VAT reporting](vat-reporting.md)  
- [Report VAT to Tax Authorities](../../finance-how-report-vat.md)
- [Set up reports for VAT and Intrastat](how-to-set-up-reports-for-vat-and-intrastat.md)  
- [Germany local functionality](germany-local-functionality.md)  
- [Set Up Intrastat Reporting](../../finance-how-setup-report-intrastat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
