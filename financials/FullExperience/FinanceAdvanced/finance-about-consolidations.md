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
# About Consolidations
Consolidation means combining the general ledger entries of two or more separate companies \(subsidiaries\) into a consolidated company. In the program, each individual company involved in a consolidation is called a business unit. The combined company is called the consolidated company and is usually a company set up for only this purpose, holding no normal business transactions.  
  
 You can consolidate:  
  
-   Across different charts of accounts  
  
-   Companies with different fiscal years  
  
-   Either the full amount or a specified percentage of a particular company's financial information  
  
-   Companies with different currencies  
  
-   Using different methods of translating individual G\/L account.  
  
 You can consolidate companies that are:  
  
-   In the same database as the consolidated company.  
  
-   In other [!INCLUDE[d365fin](../../includes/d365fin_md.md)] databases, including databases in older versions.  
  
-   In other accounting and business management programs \(assuming that you can export the data from the other program to a file with the appropriate format\).  
  
 You set up the consolidated company in a database in the same way that you set up other companies. The chart of accounts is independent of the chart of accounts in the other business units, and the chart of accounts in the individual business units may differ from one another. The consolidation features in the program lets you set up a list of companies to consolidate, verify the accounting data before consolidating, import from files and databases, and generate consolidation reports.  
  
## See Also  
 [How to: Process Consolidations](../how-to-process-consolidations.md)