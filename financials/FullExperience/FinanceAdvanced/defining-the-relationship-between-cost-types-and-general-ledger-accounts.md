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
# Defining the Relationship Between Cost Types and General Ledger Accounts
The relationship between the cost type and the general ledger account is created in the cost type and in the general ledger account.  
  
-   The **G\/L Account Range** field in the **Cost Type** table establishes which general ledger accounts belong to a cost type.  
  
-   The **Cost Type No.** field in the chart of accounts establishes which cost type a general ledger account belongs to.  
  
 These two fields are filled automatically when you use the **Get Cost Types from Chart of Accounts** function.  
  
## Relationship Between General Ledger Accounts and Cost Types  
 There is an n:1 relationship between general ledger accounts and cost types. Several general ledger accounts can belong to one cost type, but each general ledger account belongs to only one cost type. The following table describes the details in the relationship.  
  
|Relationship|**G\/L Account Range**|**Cost Type No.**|  
|------------------|------------------------------------------------|-------------------------------------------|  
|One general ledger account for each cost type|One general ledger account|One cost type|  
|Several general ledger accounts for one cost type|General ledger account range, for example, 7110..7193 for each general ledger account|For each general ledger account in the range, there is only one cost type|  
|Cost types without corresponding general ledger accounts|\<Empty\>||  
|General ledger accounts whose entries will not be transferred||\<Empty\>|  
  
### Cost Types Without a Relationship to the General Ledger  
 A cost type may not have a relationship to general ledger accounts if one of the following conditions is true:  
  
-   Accounts for operational accounting, such as Calc. Interest and Depreciation, only take costs from the operational accounting.  
  
-   Helping cost types, such as cost types 9901, 9902, and 9903 in the FIX INCLUDE HERE<!--[!INCLUDE[demoname](../BusinessFunctionality/IntegratingWithMicrosoftDynamicsCRM/includes/demoname_md.md)] --> database, are used as credit and debit accounts for allocations.  
  
-   The helping account, 9920 in the FIX INCLUDE HERE<!--[!INCLUDE[demo](../ApplicationDesign/includes/demo_md.md)] --> database, contains actual accruals that show the difference between costs and the expense from the general ledger.  
  
## See Also  
 [How to: Set Up Cost Types](../Finance/how-to-set-up-cost-types.md)   
 [Set Up Cost Accounting](../Finance/set-up-cost-accounting.md)   
 [About Cost Accounting](../Finance/about-cost-accounting.md)