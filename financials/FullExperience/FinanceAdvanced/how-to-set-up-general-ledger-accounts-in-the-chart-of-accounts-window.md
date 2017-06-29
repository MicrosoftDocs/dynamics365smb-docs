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
# How to: Set Up General Ledger Accounts in the Chart of Accounts Window
If you want to set up a completely new chart of accounts or add new accounts to an existing one, you must set up each account individually. When you set up a completely new chart of accounts, it is easier to use the **Chart of Accounts** window.  
  
### To set up general ledger accounts in the chart of accounts window  
  
1.  In the **Search** box, enter **Chart of Accounts**, and then choose the related link.  
  
2.  In the **Chart of Accounts** window, on the **Home** tab, choose **Edit**.  
  
3.  Enter the account number in the **No.** field. All accounts must have a number.  
  
4.  In the **Name** field, enter the account name.  
  
5.  In the **Income\/Balance** field, select **Income Statement** or **Balance Sheet**, depending on whether the account will be part of the income statement or the balance sheet.  
  
6.  In the **Account Type** field, identify the purpose of the account. To view the options, choose the field. Only the first type, **Posting**, represents an account that you can post to; the others are used to create totals and headings in the chart of accounts.  
  
7.  For accounts of the **Total** account type, you must fill in the **Totaling** field. For **End\-Total** accounts, this field is filled in automatically by the Indent function.  
  
     In addition to the fields described earlier in this section, you must fill in the **Gen. Bus. Posting Group**, **Gen. Prod. Posting Group**, **VAT Bus. Posting Group**, and **VAT Prod. Posting Group** fields. For Help about a specific field, choose the field and press F1.  
  
8.  Choose the next empty line to set up a new account, and then repeat steps 3 through 6.  
  
9. After you have set up all the accounts, on the **Actions** tab, in the **Functions** group, choose **Indent Chart of Accounts**. Choose the **Yes** button.  
  
> [!IMPORTANT]  
>  If you have entered definitions in the **Totaling** fields for **End\-Total** accounts before executing the indent function, you must enter them again because the function overwrites the values in all **End\-Total** fields.  
  
## See Also  
 [How to: Insert Page Breaks in the Chart of Accounts](../Finance/how-to-insert-page-breaks-in-the-chart-of-accounts.md)   
 [How to: Use More Than One Line for General Ledger Account Names](../Finance/how-to-use-more-than-one-line-for-general-ledger-account-names.md)   
 [How to: Make Windows Editable](../WorkingWithDynamics/how-to-make-windows-editable.md)