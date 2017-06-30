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
# How to: Register Cash Flow Worksheet Lines
In the worksheet for the cash flow forecast, you use a batch job to predict the cash flow forecast. With this batch job, you can fill the worksheet automatically. This is only preliminary information that can be changed if it is in the worksheet, then you can check the entries and register them.  
  
> [!NOTE]  
>  Before you register the worksheet entries, the relevant postings from the areas of general ledger, sales, purchasing, service, and fixed assets must be entered. In addition, possible manual revenues and manual expenses must be recorded.  
  
> [!NOTE]  
>  In the cash flow worksheet, you update negative or positive amounts of cash inflows and outflows in single lines to cash flow accounts. This is different than the general journal, in which single-line or multiple-line accounts can be posted to an account.  
  
### To register the cash flow worksheet lines  
  
1.  In the **Search** box, enter **Cash Flow Worksheet**, and then choose the related link.  
  
2.  On the **Home** tab, in the **Process** group, choose **Suggest Worksheet Lines** to open the **Suggest Worksheet Lines** batch job.  
  
3.  In the **\($ B\_840\_F\_1\_1 Cash Flow Forecast $\)** field, select a cash flow forecast number.  
  
4.  Select the relevant source types that should be included in the forecast.  
  
5.  If you select the **\($ B\_840\_F\_1\_16 G\/L Budget $\)** check box, then enter the budget name in the **\($ B\_840\_F\_1\_17 G\/L Budget Name $\)** field, which is the budget from which the values are taken into the forecast.  
  
6.  Select the **\($ B\_840\_F\_1\_18 Group by Document Type $\)** check box.  
  
7.  Choose the **OK** button to get the forecasted amounts in the worksheet.  
  
8.  On the **Home** tab, in the **Process** group, choose **Register** to register the entries of the forecasted cash inflows and outflows.  
  
> [!NOTE]  
>  If you run the batch job for the second time for the same cash flow forecast, all existing entries for this cash flow forecast are deleted.  
  
## See Also  
 [Cash Flow Overview](../cash-flow-overview.md)   
 Suggest Worksheet Lines   
 [How to: Set Up Cash Flow Forecasts](../how-to-set-up-cash-flow-forecasts.md)   
 [How to: Set Up the Chart of Cash Flow Accounts](../how-to-set-up-the-chart-of-cash-flow-accounts.md)   
 [How to: Configure Accounts for Cash Flow Setup](../how-to-configure-accounts-for-cash-flow-setup.md)   
 [How to: Record Manual Revenues](../how-to-record-manual-revenues.md)