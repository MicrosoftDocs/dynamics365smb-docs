---
    title: How to Set Up a Chart of Cost Types | Microsoft Docs
    description: Chart of cost types are similar to the chart of accounts in the general ledger.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: cost types, general ledger, accounts
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Set Up Cost Types
The chart of cost types is similar to the chart of accounts in the general ledger. You can set up the chart of cost types in the following ways:  

-   Structure the chart of cost types similar to the income statement accounts in the general ledger chart of accounts. Then, you can transfer the general ledger chart of accounts to the chart of cost types. You can make any necessary adjustments after the transfer.  
-   Create new chart of cost types or add new cost types to existing chart of cost types. You must create each new cost type individually.  

## To transfer the general ledger chart of accounts to the chart of cost types  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Chart of Cost Types**, and then choose the related link.  
2.  Choose the **Get Cost Types from Chart of Accounts** action. In the dialog box, choose the **Yes** button to confirm the transfer. The function uses the chart of accounts to create a chart of cost types.  

    The chart of cost types now contain all income statement accounts in the general ledger and include headings and subtotals. You can change the chart of cost types, as necessary. For example, you can delete duplicate existing cost types.  

    > [!IMPORTANT]  
    >  The **Register Cost Types in Chart of Accounts** function updates the relationship between the chart of accounts and the chart of cost types. The **No.** field is filled and verified to make sure that each general ledger account is related to only one cost type. The function runs automatically before transferring general ledger entries to cost accounting.  

## To set up new cost types in the Chart of Cost Types window  
1.  Open the **Chart of Cost Types** window in edit mode.  
2.  Fill in the fields as described as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]  
    >  You can set up and maintain cost types in either the **Cost Type Card** window or in the **Chart of Cost Types** window. In this procedure, you set up cost types in the **Chart of Cost Types** window.

3.  After you have created all cost types, choose the **Indent Cost Types** action. In the dialog box, choose the **Yes** button.  
4.  Link the new cost type to the corresponding general ledger account.  

    > [!IMPORTANT]  
    >  If you have entered definitions in the **Totaling** fields for the line type of **End-Total** before you run the **Indent Cost Types** function, then you must enter the definitions again because the function overwrites the values in all **End-Total** fields.  

## To update cost types  
1.  In the **Cost Accounting Setup** window, select if you want the chart of cost types to be automatically updated when the chart of accounts is changed.  
2.  In the **Align G/L Account** field, you can choose from the following options.  

- **No Alignment** - There is no corresponding change in the chart of cost types when you change the chart of accounts.  
- **Automatic** - A corresponding change is made in the chart of cost types when you change the chart of accounts.  
- **Prompt** - A message is displayed asking if you want to make a corresponding change in the chart of cost types when you change the chart of accounts.  

## See Also  
[Accounting for Costs](finance-manage-cost-accounting.md)  
[Defining the Relationship Between Cost Types and General Ledger Accounts](finance-defining-the-relationship-between-cost-types-and-general-ledger-accounts.md)   
[Defining Cost Centers and Cost Objects for Chart of Accounts](finance-defining-cost-centers-and-cost-objects-for-chart-of-accounts.md)   
[Balances Between Cost Type, Cost Center, and Cost Object](finance-balances-between-cost-type-cost-center-and-cost-object.md)   
[Setting Up Cost Accounting](finance-set-up-cost-accounting.md)   
[Terminology in Cost Accounting](finance-terminology-in-cost-accounting.md)   
[About Cost Accounting](finance-about-cost-accounting.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
