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
# How to: Create Budgets
In ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]-->, the create budget function allows you to do the following:  
  
-   Create budget amounts by period.  
  
-   Create budget amounts from historical general ledger entries.  
  
-   Export a budget.  
  
-   Import a budget.  
  
### To create budget amounts by period  
  
1.  In the **Search** box, enter **G\/L Budgets**, and then choose the related link.  
  
2.  Select a budget. On the **Home** tab, in the **Process** group, choose **Edit Budget**.  
  
3.  On then **Navigate** tab, in the **Balance** group, choose **G\/L Balance\/Budget**.  
  
4.  Select a general ledger account.  
  
5.  On the **Actions** tab, in the **Functions** group, select **Create Budget**, and then choose **Amount by Period**.  
  
6.  In the **Budget Amount by Period** batch job, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Budget Beginning Date**|The start date of the first budget period to be created.|  
    |**No. of Periods**|The number of budget periods to be created.|  
    |**Period Length**|The length of each of the budget periods to be created. A budget amount is created for each budget period.|  
    |**Budget Amount**|The starting budget amount.|  
    |**Amount Type**|**Total Amount** – The amount that is entered in the **Budget Amount** field is allocated among the periods for which you are budgeting. The amount will be duplicated in each period.<br /><br /> –or–<br /><br /> **Beginning Amount** – The amount in the **Budget Amount** field is the amount that is budgeted for each period. The amount will be divided evenly among all of the periods.|  
    |**Period Percent Change**|Enter zero to spread budgets evenly over all periods. **Note:**  The budget amount for this period is increased or decreased with regard to the previous period by the positive or negative percentage amount entered.|  
    |**Round To**|The percentage used to round the budget amount.|  
  
7.  On the **G\/L Account** FastTab, select the appropriate filters.  
  
8.  Choose the **OK** button.  
  
### To create budget amounts from history  
  
1.  In the **G\/L Budgets** window, select a budget. On the **Home** tab, in the **Process** group, choose **Edit Budget**.  
  
2.  On the **Navigate** tab, in the **Balance** group, choose **G\/L Balance\/Budget**.  
  
3.  Select a general ledger account.  
  
4.  On the **Actions** tab, in the **Functions** group, select **Create Budget**, and then choose **From History**.  
  
    > [!NOTE]  
    >  When you create a budget with the **From History** option, you get the same result as you would if use the **Copy Budget** function with **G\/L Entry** as the **Source**. The budget is based on actual general ledger entries for the specified period. For more information, see Copy G-L Budget.  
  
5.  In the **Budget from History** batch job, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**History Beginning Date**|The start date of the first historical period to be analyzed for the creation of the budget.|  
    |**Budget Beginning Date**|The start date of the first budget period to be created.|  
    |**No. of Periods**|The number of budget periods to be created.|  
    |**Period Length**|The length of each of the budget periods to be created.|  
    |**Percent Change**|Enter zero if you want the budget to be the same as it is in the corresponding historical period. **Note:**  The fields in the **Budget from History** window and **Budget Amount by Period** window work similarly. The one exception is the **Percent Change** field. In the **Budget Amount by Period** window, the percent change is from one period to the next. In the **Budget from History** window, the percent change is from the historical value to the new budget value for the corresponding period.|  
    |**Round To**|The percentage used to round the budget amount.|  
  
6.  On the **G\/L Account** FastTab, select the appropriate filters.  
  
7.  Choose the **OK** button.  
  
## See Also  
 Copy G-L Budget   
 [How to: Import or Export a Budget](../how-to-import-or-export-a-budget.md)   
 [Budgets](../budgets.md)   
 Export Budget to Excel   
 Import Budget from Excel