---
title: How to Set Up Reports for VAT and Intrastat
description: Learn how to specify the reports used to create documents for submission to authorities, such as the VAT statement and the Intrastat form.
author: brentholtorf  
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: VAT statement, Intrastat form, set up reports, German version
ms.date: 03/12/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up reports for VAT and Intrastat

[!INCLUDE[intrastat-2022w2](../../includes/intrastat-2022w2.md)]

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can specify which reports to use to create the documents that you must submit to the authorities, such as the VAT statement and the Intrastat form.  

## Set up reports for VAT

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Selections VAT**, and then choose the related link.  
1. On the **Report Selection – VAT** page, in the **Usage** field, select the type of document that you want to specify reports for. This includes the VAT statement and the VAT statement schedule.  
1. Specify the report or batch job that must run when a user starts the activity for the document type that you specified in the **Usage** field. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Sequence**|Specifies where a report is in the printing order.|  
    |**Report ID**|Specifies the ID of the report that prints for this document type.|  
    |**Report Name**|Specifies the name of the report that prints for this document type. The **Report Name** field updates based on the selection in the **Report ID** field.|  

1. Choose the **OK** button.  

### Set up reports for Intrastat

> [!NOTE]
> Intrastat reports can use either the XML or ASCII formats. Depending on the format you use, enter the material number in one of the following fields on the **Company  Information** page.  
>
> |Format|Fields|
> |---------|---------|
> |XML|Company No.|
> |ASCII|Sales Material No., Purchase Material No.|

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Selection**, and then choose the related link.  
1. On the **Report Selection – Intrastat** page, in the **Usage** field, select the type of document that you want to specify reports for. This includes the Intrastat checklist and Intrastat form.  
1. Specify the report or batch job that must run when a user starts the activity for the document type that you specified in the **Usage** field. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Sequence**|Specifies where a report is in the printing order.|  
    |**Report ID**|Specifies the ID of the report that prints for this document type.|  
    |**Report Name**|Specifies the name of the report that prints for this document type. The **Report Name** field updates based on the selection in the **Report ID** field.|  

1. Choose the **OK** button.  

## Related information

- [Export and Print Intrastat Reports](how-to-export-and-print-intrastat-reports.md)  
- [VAT Reporting](vat-reporting.md)
- [Germany Local Functionality](germany-local-functionality.md)  
- [Set Up Intrastat Reporting](../../finance-how-setup-report-intrastat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
