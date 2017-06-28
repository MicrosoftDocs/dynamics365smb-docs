---
title: "How to: Set Up the Chart of Cash Flow Accounts"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "chart of accounts, cash flow"
  - "cash flow, setting up chart of accounts"
ms.assetid: 58c7c796-ed39-4e52-9107-8f303bf4e11a
caps.latest.revision: 15
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Set Up the Chart of Cash Flow Accounts
In the cash flow forecast, the individual values that affect the cash flow of your company are arranged by using cash flow accounts. You can set up the chart of cash flow accounts.  
  
### To set up cash flow accounts  
  
1.  In the **Search** box, enter **Cash Flow Accounts**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New** to create a new cash flow account.  
  
3.  In the **\($ T\_841\_1 No. $\)** field, enter the cash flow account number.  
  
4.  In the **\($ T\_841\_2 Name $\)** field, enter the cash flow account name.  
  
5.  In the **\($ T\_841\_4 Account Type $\)** field, select an account type to identify the purpose of the cash flow account.  
  
    -   Entry \- An account type that you register forecasted amounts to.  
  
    -   Total – An account type that creates a total. You must fill in the **\($ T\_841\_34 Totaling $\)** field.  
  
    -   End\-total – An account type that is filled in automatically by the **Indent Chart of Cash Flow Accounts** batch job.  
  
6.  In the **\($ T\_841\_35 Source Type $\)**  field, select a source type.  
  
    > [!NOTE]  
    >  The source type that is specified in the chart of cash flow accounts is used when you enter lines manually in the cash flow worksheet. When you use the **\($ B\_840 Suggest Worksheet Lines $\)** batch job, the source type is controlled by the batch job.  
  
7.  In the **\($ T\_841\_36 G\/L Integration $\)** field, select an option.  
  
    > [!NOTE]  
    >  When a cash flow account is integrated with the general ledger, either the balances of the general ledger accounts or their budget values are included in cash flow forecast.  
  
8.  In the **\($ T\_841\_37 G\/L Account Filter $\)** field, enter a filter to specify that only the entries that are registered to the filtered accounts are included in cash flow forecast.  
  
9. Choose the **OK** button to close the window.  
  
10. Repeat steps 2\-9 to set up a new cash flow account.  
  
11. After you have set up all the cash flow accounts, on the **Home** tab, in the **Process** group, select **Indent Chart of Cash Flow Accounts** to update the structure of cash flow accounts.  
  
> [!NOTE]  
>  If you have entered definitions in the **\($ T\_841\_34 Totaling $\)** field for accounts of the **End\-Total** type before you perform the indent function, you must enter them again because the function overwrites the values in the **\($ T\_841\_34 Totaling $\)** field. The indent function moves all **End\-Totals** to the corresponding **Begin\-Totals** and indents the accounts that lie in between.  
  
### To add comments to cash flow accounts  
  
1.  On the **Navigate** tab, in the **Cash Flow Forecast** group, select **Comments** to enter additional information to a cash flow account. This information can be about the contents of the fields. You add these comments as text lines.  
  
2.  Choose the **OK** button to close the window.  
  
> [!NOTE]  
>  This procedure is optional.  
  
## See Also  
 [\($ N\_851 Chart of Cash Flow Accounts $\)](assetId:///31304b24-56c5-4b6e-b2cd-cb54d5f21699)   
 [Cash Flow Overview](../Finance/cash-flow-overview.md)   
 [How to: Set Up Cash Flow Forecasts](../Finance/how-to-set-up-cash-flow-forecasts.md)   
 [How to: Configure Accounts for Cash Flow Setup](../Finance/how-to-configure-accounts-for-cash-flow-setup.md)   
 [\($ B\_840 Suggest Worksheet Lines $\)](../Topic/\($%20B_840%20Suggest%20Worksheet%20Lines%20$\).md)