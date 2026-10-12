---
title: How to Set Up Reports for VAT and Intrastat
description: Learn how to specify the reports used to create documents for submission to authorities, such as the VAT statement and the Intrastat form.
author: brentholtorf  
ms.topic: how-to
ms.devlang: al
ms.search.keywords: VAT statement, Intrastat form, set up reports, German version
ms.date: 10/09/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Set up reports for VAT and Intrastat

> [!NOTE]
> From the January 2027 reporting period, INSTAT/XML must be submitted via eSTATISTIK.CORE (IDEV retired) and that the same INSTAT/XML structure is used.

[!INCLUDE[intrastat-2022w2](../../includes/intrastat-2022w2.md)]

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can specify which reports to use to create the documents that you must submit to the authorities, such as the VAT statement and the Intrastat form.  

## Set up reports for VAT

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Selections VAT**, and then choose the related link.  
1. On the **Report Selection - VAT** page, in the **Usage** field, select the type of document that you want to specify reports for. This includes the VAT statement and the VAT statement schedule.  
1. Specify the report or batch job that must run when a user starts the activity for the document type that you specified in the **Usage** field. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Sequence**|Specifies where a report is in the printing order.|  
    |**Report ID**|Specifies the ID of the report that prints for this document type.|  
    |**Report Name**|Specifies the name of the report that prints for this document type. The **Report Name** field updates based on the selection in the **Report ID** field.|  

1. Choose the **OK** button.  

## Set up reports for Intrastat

> [!NOTE]
> Intrastat reports are submitted in XML format. Depending on the submission channel, enter the material number in one of the following fields on the **Company Information** page.  
>
> |Submission channel|Field|Comment|
> |---------|---------|--------------|
> |IDEV|**Company No./Material No. (XML)**|Required. The IDEV format requires the material number in the message ID.|
> |eSTATISTIK.CORE|**Company No./Material No. (XML)**|Not required; you can leave this field empty.|
>
> If you submit Intrastat data in the legacy ASCII format, use the **Sales Authorized No. (ASCII)** and **Purch. Authorized No. (ASCII)** fields instead.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Report Setup**, and then choose the related link.  
1. In the **Default Submission Channel** field, choose **eSTATISTIK.CORE** or **IDEV**. This is the submission channel that's suggested on new Intrastat reports.  
1. On each Intrastat report, you can also choose the **Submission Channel** field directly, and select the **Test Submission** field if you want the exported XML file to be used for a test submission.  

Learn more in [Export and print Intrastat reports](how-to-export-and-print-intrastat-reports.md).

## Related information

- [Export and print Intrastat reports](how-to-export-and-print-intrastat-reports.md)
- [VAT reporting](vat-reporting.md)
- [Germany local functionality](germany-local-functionality.md)
- [Set up Intrastat reporting](../../finance-how-setup-report-intrastat.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
