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
# How to: Set Up Liquid Funds for Cash Flow Forecasts
To include the liquid funds in the general ledger for the cash flow forecast, you must identify the accounts that have balances that influence the prediction of net cash flow.  
  
### To set up liquid funds for cash flow forecasts  
  
1.  In the **Search** box, enter **Cash Flow Accounts**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New** to create a new cash flow account.  
  
3.  In the **No.** field, enter the cash flow account number.  
  
4.  In the **Name** field, enter **Cash Flow Liquid Funds** as the cash flow account name.  
  
5.  In the **Account Type** field, select **Entry** to identify the purpose of the cash flow account.  
  
6.  In the **Source Type** field, select **Liquid Funds**.  
  
7.  In the **G\/L Integration** field, select **Balance**.  
  
8.  In the **G\/L Account Filter** field, enter a filter, for example **2910..2940**, to specify that only the entries that are registered to the filtered accounts from 2910 through 2940 are included in liquid funds for the cash flow forecast.  
  
9. Choose the **OK** button to close the window.  
  
10. On the **Home** tab, in the **Process** group, choose **Indent Chart of Cash Flow Accounts** to update the structure of cash flow accounts.  
  
## See Also  
 Chart of Cash Flow Accounts   
 [How to: Set Up the Chart of Cash Flow Accounts](../how-to-set-up-the-chart-of-cash-flow-accounts.md)   
 [Cash Flow Overview](../cash-flow-overview.md)