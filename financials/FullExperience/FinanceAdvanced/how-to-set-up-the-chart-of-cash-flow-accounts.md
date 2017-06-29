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
# How to: Set Up the Chart of Cash Flow Accounts
In the cash flow forecast, the individual values that affect the cash flow of your company are arranged by using cash flow accounts. You can set up the chart of cash flow accounts.  
  
### To set up cash flow accounts  
  
1.  In the **Search** box, enter **Cash Flow Accounts**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New** to create a new cash flow account.  
  
3.  In the **No.** field, enter the cash flow account number.  
  
4.  In the **Name** field, enter the cash flow account name.  
  
5.  In the **Account Type** field, select an account type to identify the purpose of the cash flow account.  
  
    -   Entry - An account type that you register forecasted amounts to.  
  
    -   Total – An account type that creates a total. You must fill in the **Totaling** field.  
  
    -   End-total – An account type that is filled in automatically by the **Indent Chart of Cash Flow Accounts** batch job.  
  
6.  In the **Source Type**  field, select a source type.  
  
    > [!NOTE]  
    >  The source type that is specified in the chart of cash flow accounts is used when you enter lines manually in the cash flow worksheet. When you use the **Suggest Worksheet Lines** batch job, the source type is controlled by the batch job.  
  
7.  In the **G\/L Integration** field, select an option.  
  
    > [!NOTE]  
    >  When a cash flow account is integrated with the general ledger, either the balances of the general ledger accounts or their budget values are included in cash flow forecast.  
  
8.  In the **G\/L Account Filter** field, enter a filter to specify that only the entries that are registered to the filtered accounts are included in cash flow forecast.  
  
9. Choose the **OK** button to close the window.  
  
10. Repeat steps 2-9 to set up a new cash flow account.  
  
11. After you have set up all the cash flow accounts, on the **Home** tab, in the **Process** group, select **Indent Chart of Cash Flow Accounts** to update the structure of cash flow accounts.  
  
> [!NOTE]  
>  If you have entered definitions in the **Totaling** field for accounts of the **End-Total** type before you perform the indent function, you must enter them again because the function overwrites the values in the **Totaling** field. The indent function moves all **End-Totals** to the corresponding **Begin-Totals** and indents the accounts that lie in between.  
  
### To add comments to cash flow accounts  
  
1.  On the **Navigate** tab, in the **Cash Flow Forecast** group, select **Comments** to enter additional information to a cash flow account. This information can be about the contents of the fields. You add these comments as text lines.  
  
2.  Choose the **OK** button to close the window.  
  
> [!NOTE]  
>  This procedure is optional.  
  
## See Also  
 Chart of Cash Flow Accounts   
 [Cash Flow Overview](../FullExperience/cash-flow-overview.md)   
 [How to: Set Up Cash Flow Forecasts](../FullExperience/how-to-set-up-cash-flow-forecasts.md)   
 [How to: Configure Accounts for Cash Flow Setup](../FullExperience/how-to-configure-accounts-for-cash-flow-setup.md)   
 Suggest Worksheet Lines