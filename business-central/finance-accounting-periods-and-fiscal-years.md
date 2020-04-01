---
    title: Working with Accounting Periods and Fiscal Years | Microsoft Docs
    description: Learn how to work with accounting periods to define when your company reports financial performance.
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: bholtorf

---
# Working with Accounting Periods and Fiscal Years
Accounting periods, which are also known as reporting periods, are periods of time for which a company or organization reports financial performance, for example, by generating their income statement or balance sheet. Typically, accounting periods refer to the company's fiscal year, which can contain several accounting periods, such as months or quarters.

For many companies the fiscal year does not align with the calendar year. For example, the fiscal year might end on June 30th rather than December 31st. For newly created companies, the fiscal might actually be longer than 12 months. 

[!INCLUDE[d365fin](includes/d365fin_md.md)] only requires accounting periods only if you want to close an income statement, or run data compression tasks. 

You can use accounting periods in reporting. For example, when you are reviewing posted entries on the **Balance/Budget** page where the reporting interval can be specified. One of the options you may specify to report by accounting period. You can also build an account schedule that compares results for different accounting periods.

## Creating a new fiscal year
You can create accounting periods in bulk, by using eh **Create Fiscal Year** batch job, or manually.

### How to create accounting periods in-bulk
Use the **Create Fiscal Year** batch job to divide a fiscal year into periods of equal length.  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Accounting Periods**, and then choose the related link.  
2. Choose the **Create Year** action.  <!--What about the Scheduling option? Should we mention that? There's also the Report Output Type field...-->
3. In the **Starting Date** field, enter the date on which the fiscal year starts.  
4. In the **No. of Periods** field, enter the number of accounting periods to divide the fiscal year into. There can be up to 365 periods in a year.  
5. In the **Period Length** field, enter a duration for each period. For example, 1M for one month, 1Q for one quarter, and 1Y for one year.  
6. Choose **OK**.  

### How to create accounting periods manually
If the accounting periods in your fiscal year have different durations, like the 4-4-5 calendar used in retail, you can manually set it up.  
  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Accounting Periods**, and then choose the related link.  
2. In the **Starting Date** field, enter the date on which the fiscal year starts. The **Name** field will show the name of the month.  
3. Choose the **New Fiscal Year** check box to indicate that this is the first period in the year. [!INCLUDE[d365fin](includes/d365fin_md.md)] will use this period to determine which periods to close at year-end.
4. Repeat steps 2 and 3 for each remaining period.  

## Closing a Fiscal Year
Closing the fiscal year is one of the tasks for closing the books. After you close a fiscal year, the **Closed** and **Date Locked** check boxes are selected for all periods in the year. You cannot reopen a year or clear the check boxes.

> [!NOTE]  
>  You must always have at least one open fiscal year. When closing a year, ensure that a new year has been created. Also, note that after you close one year, you cannot change the starting date of the following year.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Accounting Periods**, and then choose the related link.  
2. Choose the **Close Year** action.  

## Posting Entries to a Closed Fiscal Year
Although a fiscal year is closed, you can still post general ledger entries to it. When you do, the entries are marked as posted to a closed fiscal year and the **Prior Year Entry** check box is selected. By default, the check box is not displayed on the page, but you can add it. The next steps are to close the income statement accounts and transfer the year's results to an account in the balance sheet. Repeat these steps each time you post entries to a closed fiscal year.

## See Also
[Closing the Books](year-close-books.md)  
[Closing Years and Periods](year-close-years-periods.md)  
[How to Work with Account Schedules](bi-how-work-account-schedule.md)  
  





