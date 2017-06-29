---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# How to: Set Up XBRL Lines
After you import or update the taxonomy, the lines of the schemas must be supplied with all the information that is required. This information will include basic company information, the actual financial statements, notes to the financial statements, supplemental schedules, and other information that is required to satisfy the particular financial reporting requirements.  
  
 You set up the XBRL Lines by mapping the data in the taxonomy to the data in your general ledger.  
  
### To set up XBRL lines  
  
1.  In the **Search** box, enter **XBRL Taxonomies**, and then choose the related link.  
  
2.  In the **XBRL Taxonomies** window, select a taxonomy from the list.  
  
3.  On the **Home** tab, in the **Process** group, choose **Lines**.  
  
4.  Select a line and fill in the fields. ADD INCLUDE<!--[!INCLUDE[bp_fieldhelp]()]-->  
  
5.  To read detailed information about what to fill in, on the **Navigate**, in the **XBRL Line** group, choose **Information**.  
  
6.  To set up the mapping of the general ledger accounts in the chart of accounts to the XBRL lines, on the **Navigate**, in the **XBRL Line** group, choose **G\/L Map Lines**.  
  
7.  To add notes to the financial statement, on the **Navigate**, in the **XBRL Line** group, choose **Notes**.  
  
> [!NOTE]  
>  You can only export data that correspond to the source type you have selected in the **Source Type** field that includes description and notes.  
  
> [!NOTE]  
>  Lines that are not relevant can be marked as line type **NOT APPLICABLE** so the lines are not exported.  
  
## See Also  
 [How to: Import XBRLTaxonomies](../how-to-import-xbrltaxonomies.md)   
 [How to: Update XBRL Taxonomies](../how-to-update-xbrl-taxonomies.md)   
 XBRL Export Instance - Spec. 2   
 [eXtensible Business Reporting Language](../extensible-business-reporting-language.md)