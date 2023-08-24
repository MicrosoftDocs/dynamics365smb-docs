---
title: Requirements for Reporting Declaration of Trade in Goods [FR]
description: This article shows a list of required fields that are needed for reporting Declaration of Trade in Goods (DEB) based on the DTI+ format in the French version of Business Central.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 05/09/2022
ms.author: bholtorf

---
# Requirements for Reporting Declaration of Trade in Goods in the French Version

In this article, we describe how you can set up your [!INCLUDE [prod_short](../../includes/prod_short.md)] for reporting the Declaration of Trade in Goods (DEB) report in France.  

The following fields are required for reporting DEB:  

- **CISD** from the **Company Information** table.  
- **Registration No.** from the **Company Information** table.  
- **VAT Registration No.** from the **Company Information** table.  
- **Name** from the **Company Information** table.  
- **Date** for the statistics period from the **Intrastat Jnl. Line** table.  
- **Transaction Specification** from the **Intrastat Jnl. Line** table.  
- **Quantity** from the **Intrastat Jnl. Line** table must be greater than 0.  
- **Statistical Value** from the **Intrastat Jnl. Line** table must be greater than 0.  

> [!NOTE]  
> The **Export DEB DTI** report exports shipments and receipts in one batch. If you want to report only shipments or receipts, then you must set a filter to remove the lines that are not needed in the **Intrastat Journal** table.  

## Intrastat requirements for DEB

For France, Intrastat management implies to separate the declaration data for the statistical reporting and for the fiscal reporting (recapitulative statement of VAT). It is required that Intrastat exports separetely files based on configured obligation level.

1. To export Intrastat lines correctly, choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journals** and then select the action **Suggest Lines**. New Intrastat journal lines will be created for the selected period.  

2. On the journal lines, fill in the necessary fields, and then choose the **Export DEB DTI+** action.  

    The **Export DEB DTI** runs. You must specify the obligation level that you want to report. The **Transaction Specification Filter** field on the request page has a predefined value that depends on the specified obligation level. The value of this field is a filter that is applied to the **Transaction Specification** field of the Intrastat journal lines.  

When the report is run, only Intrastat journal lines with a value of the **Transaction Specification** field that matches the **Transaction Specification Filter** field are processed. The field **Transaction Specification Filter** is editable, so you can change its value according to your needs. The following table outlines the currently supported values:

| Level | Filter |
|--|--|
| **Obligation Level 1** | `11 | 19 | 21 | 29` |
| **Obligation Level 2** | “” (a blank filter, so that all Intrastat journal lines are processed) |
| **Obligation Level 3** | “” |
| **Obligation Level 4** | `<>29&<>11&<>19` (lines with Transaction Specification 29, 11, 19 are not processed) |
| **Obligation Level 5** | `<>11&<>19` |

## Validate Intrastat lines

Run the **Advanced Intrastat Checklist** report to check Intrastat journal lines before they are exported to XML. The check is run inside the **Export DEB DTI** report.  

### To enable the check

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Setup** and then choose the relevant link.  
2. Select the **Use Advanced Checklist** field.  
3. Choose the **Advanced Intrastat Checklist Setup** action.
4. Add the necessary lines with the **Object Type** field set to *Report*, and the **Object Id** field set to *10821*. Then set the **Field No.** field to a field that must be checked for a non-empty value. Fill in the **Filter Expression** field if needed.

## See Also

[France Local Functionality](france-local-functionality.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
