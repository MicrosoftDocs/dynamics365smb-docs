---
    title: How to Indent and Validate Chart of Accounts
    description: You can indent and validate the chart of accounts on the G/L Account Card page. You can enter a maximum of 20 numbers. Accounts are sorted in string order.

    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Indent and Validate Chart of Accounts
You can indent and validate the chart of accounts on the **G/L Account Card** page. You can enter a maximum of 20 numbers. Accounts are sorted in string order, as shown in the following example.  

1  
10  
101  
2  
20  
2100001  
3  
31  

## To indent and validate the chart of accounts  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Chart of Accounts**, and then choose the related link.  
2.  Choose the **New** action.  
3.  On the **General** FastTab, in the **No.** field, enter the number of the general ledger account that you are setting up.  
4.  In the **Account type** field, select **Posting** or **Heading**. **Posting** implies that entries can be posted to the account. **Heading** implies that entries cannot be posted to the account.  

    > [!NOTE]  
    >  For Portugal, select **Posting** or **Total** in the **Account type** field.  

5.  In the **Income Stmt. Bal. Acc.** field, select the account to which the changes will be sent after correction.  
6.  Enter information into the other relevant fields.  
7.  Choose the **OK** button to close the **G/L Account Card** page.  
8.  On the **Chart of Accounts** page, select an account, and then choose **Indent Chart of Accounts**.  
9. To validate the chart of accounts, choose the **Yes** button in the dialog box. After validation, you will be notified whether the chart of accounts is correct.  
10. Choose the **OK** button.  

## To validate the chart of accounts in Portugal  

1.  On the **Chart of Accounts** page, choose the **Check Chart of Accounts** action.  
2.  Choose the **Yes** button.  

## See Also  
[Spain Local Functionality](spain-local-functionality.md)
