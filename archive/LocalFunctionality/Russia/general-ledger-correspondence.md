---
    title: General Ledger Correspondence
    description: The general ledger correspondence feature enables you to create a correspondence transaction periodically, post correspondence operations when you post general ledger transactions, and analyze a number of reports for correspondence.

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
# General Ledger Correspondence
The general ledger correspondence feature enables you to:  

- Create a correspondence transaction periodically.  
- Post correspondence operations when you post general ledger transactions.  
- Analyze a number of reports for correspondence.  

## Creating a General Ledger Correspondence Entry  
The following procedure shows how to periodically create general ledger correspondence entries.  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Create G/L Correspondence**, and then choose the related link.  
2.  Enter the **Transaction No.** field with the transaction number if general ledger correspondence is to be created only for the selected transaction. Otherwise, leave it blank.  

To set up automatic general ledger correspondence  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **General Ledger Setup**, and then choose the related link.
2. Select the **Automatic G/L Correspondence** check box.  

## Reports  
The following reports have been added for the analysis of data from correspondence transactions:  

- General Ledger Correspondence General Ledger (page 12403; report 12431)  
- General Ledger Correspondence Analysis (page 12401)  
- General Ledger Correspondence Journal Order (report 12432)  
- General Ledger Correspondence Entries Analysis (report 12435)  

### General Ledger Correspondence General Ledger Window  
The **General Ledger Correspondence General Ledger** window shows turnovers in the chosen period in correspondence.  

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Correspondence**, and then choose the related link.  
2. Choose the **General Ledger** action.  

The header of the **G/L Corresp. General Ledger** window contains the following filters:  

- Date  
- Business unit  
- Global Dimension 1 Filter  
- Global Dimension 2 Filter  

If you select a turnover in the left subform, the report shows the turnover in correspondence with other accounts in the right subform.  

1. Choose the **General Ledger** action.
2. On the **Options** FastTab, set parameters by filling in the fields with the information listed in the following table.  

|Field|Description|  
|--------------|-----------------|  
|**Starting Date**|Enter the starting date of the period, for the entries that you want to include in the report.|  
|**Ending Date**|Enter the ending date of the period, for the entries that you want to include in the report.|  

### General Ledger Correspondence Entries Analysis Report  
The **General Ledger Correspondence Entries Analysis** report shows the correspondence entries for each account. The report can be used to get an overview of general ledger account entries with correspondence and totals.  

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Correspondence**, and then choose the related link.  
2. Choose the **Entries Analysis** action.   

On the **Options** tab of the request form, you can set parameters by filling in the fields with the information listed in the following table.  

|Field|Description|  
|-----------|-----------------|  
|**Starting Date**|Enter the starting date of the period, for the entries that you want to include in the report.|  
|**Ending Date**|Enter the ending date of the period, for the entries that you want to include in the report.|  
|**Other parameters**<br /><br /> **Without Zero Net Changes**<br /><br /> **Without Zero Lines**<br /><br /> **Debit Credit Separately**<br /><br /> **New Page for GL Acc**|Specify the view of the report, such as whether the information for each account should be written without zero lines or net changes.|

## See Also
[Russia Local Functionality](russia-local-functionality.md)
