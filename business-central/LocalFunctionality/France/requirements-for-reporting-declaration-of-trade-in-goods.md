---
    title: Requirements for Reporting Declaration of Trade in Goods
    description: This topic shows a list of required fields that are needed for reporting Declaration of Trade in Goods (DEB) based on the DTI+ format.

    author: SorenGP

    
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2021
    ms.author: edupont

---
# Requirements for Reporting Declaration of Trade in Goods
## Setup for DEB reporting
This topic shows a list of required fields that are needed for reporting Declaration of Trade in Goods (DEB) based on the DTI+ format. For more information, see Export DEB DTI.  

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
>  The **Export DEB DTI** report exports shipments and receipts in one batch. If you want to report only shipments or receipts, then you must set a filter to remove the lines that are not needed in the **Intrastat Journal** table.  

## Intrastat requirements for DEB
For France, Intrastat management implies to separate the declaration data for the statistical reporting and for the fiscal reporting (recapitulative statement of VAT). It is required that Intrastat exports separetely files based on configured obligation level.

1. To export Intrastat lines properly choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journals** and then select the action **Suggest Lines**. New intrastat journal lines will be created for the selected period.

2. On the journal lines fill in necessary fields and select **Export DEB DTI+** action. A report **Export DEB DTI** is run. You need to choose Obligation Level you want to report. Field **Transaction Specification Filter** on the request page has predefined value which depends on the selected Obligation Level. The value of this field is a filter that is applied to the **Transaction Specification** field of intrastat journal lines.

3. Therefore, when the report is run, only intrastat journal lines with the **Transaction Specification** that matches the **Transaction Specification Filter** are processed. The field **Transaction Specification Filter** is editable, so you can change its value according to your needs. Current Transaction Specification Filter values are:

    |Level|Filter|  
    |---------------------------------|---------------------------------------|  
    |**Obligation Level 1**|11|19|21|29|  
    |**Obligation Level 2**| “” (blank filter, i.e. all intrastat journal lines are processed)|  
    |**Obligation Level 3**| “” |  
    |**Obligation Level 4**|<>29&<>11&<>19 (lines with Transaction Specification 29, 11, 19 are not processed)|  
    |**Obligation Level 5**|<>11&<>19|  

## Validate Intrastat lines
It is possible to use **Advanced Intrastat Checklist** for checking intrastat journal lines before they are exported to xml. The check is run inside the report Export DEB DTI. 
To enable the check:
1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Setup** and then choose the relevant link.
2. Enable **Use Advanced Checklist** flag.
3. Select **Advanced Intrastat Checklist Setup** action on Intrastat Setup page.
4. Add necessary lines with Object Type = Report, Object Id = 10821. Then set the “Field No.” for a field that must be checked for a non-empty value. Fill in the Filter Expression field if needed.

## See Also  
[France Local Functionality](france-local-functionality.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
