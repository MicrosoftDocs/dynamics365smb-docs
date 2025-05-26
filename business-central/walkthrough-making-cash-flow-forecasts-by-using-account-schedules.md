---
title: Make cash flow forecasts using financial reports
description: This walkthrough describes how you can use financial reports to make cash flow forecasts in Business Central. 
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.date: 08/01/2024
ms.author: bholtorf
ms.search.form: 103, 104, 108, 488, 489, 490
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Walkthrough: Make cash flow forecasts using financial reports

This walkthrough describes how you can use the financial reports feature to make cash flow forecasts. Financial reports perform calculations that cannot be done directly in the chart of cash flow accounts. In the financial reports, you can set up subtotals for cash flow receipts and disbursements. These subtotals can be included in new totals that can then be used to make cash flow forecasts.  

## About this walkthrough

This walkthrough describes the following tasks:  

- Setting up a new cash flow financial report name.  
- Setting up financial report lines.  
- Setting up a new column definition.  
- Assigning a column definition to a financial report.  
- Viewing and printing the cash flow forecast.  

### Prerequisites

To complete this walkthrough, you will need:  

- [!INCLUDE[prod_short](includes/prod_short.md)]  
- A cash flow worksheet with registered lines  

## Roles

This walkthrough demonstrates tasks that are performed by the following user role:  

- Controller  

## Story

Ken is a controller at CRONUS who makes monthly cash flow forecasts. Ken includes finance, sales, purchase, and fixed assets in the forecasts, and presents to CFO Sara for business insight.  

## Set up a new financial report name

The financial report name is the name you give the cash flow forecast that includes a series of defined lines and a column definition.  

### Set up a new financial report name  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, and then choose the related link.  
2. On the **Financial Reports** page, choose **New** to create a new cash flow financial report name.  
3. In the **Name** field, enter **Forecast**.  
4. In the **Description** field, enter **Cash Flow Forecast**.  
5. Leave the **Row Definition** and **Column Definition** fields blank.

## Set up row definition lines

After a financial report name is set up, Ken defines each line in the cash flow financial report. Ken defines lines to be shown in reports in addition to lines that are only for calculation purposes.  

### Set up row definition lines  

1. On the **Financial Reports** page, select the new **Forecast** financial report you created, then choose the **Edit Row Definition** action.  
2. On the **Row Definition** page, enter each line as shown in the following table.  

    > [!TIP]  
    > Use the **Insert CF Accounts** function to quickly mark, in the cash flow accounts chart, the cash flow accounts you want and copy them to row definition lines.  

    | Row No. | Description              | Totaling Type            | Totaling | Row Type   | Amount Type | Show |
    |---------|--------------------------|--------------------------|----------|------------|-------------|------|
    | R10     | Receivables              | Cash Flow Entry Accounts | 10       |Net Change | Net Amount  | Yes  |
    | R10     | Open sales orders        | Cash Flow Entry Accounts | 20       |Net Change | Net Amount  | Yes  |
    | R10     | Rentals                  | Cash Flow Entry Accounts | 30       |Net Change | Net Amount  | Yes  |
    | R10     | Financial assets         | Cash Flow Entry Accounts | 40       |Net Change | Net Amount  | Yes  |
    | R10     | Fixed assets disposal    | Cash Flow Entry Accounts | 50       |Net Change | Net Amount  | Yes  |
    | R10     | Private investments      | Cash Flow Entry Accounts | 60       |Net Change | Net Amount  | Yes  |
    | R10     | Miscellaneous receipts   | Cash Flow Entry Accounts | 70       |Net Change | Net Amount  | Yes  |
    | R10     | Open service orders      | Cash Flow Entry Accounts | 80       |Net Change | Net Amount  | Yes  |
    | R20     | Total cash receipts      | Formula                  | R10      |Net Change | Net Amount  | Yes  |
    | R30     | Payables                 | Cash Flow Entry Accounts | 1010     |Net Change | Net Amount  | Yes  |
    | R30     | Open purchase orders     | Cash Flow Entry Accounts | 1020     |Net Change | Net Amount  | Yes  |
    | R30     | Personnel costs          | Cash Flow Entry Accounts | 1030     |Net Change | Net Amount  | Yes  |
    | R30     | Running costs            | Cash Flow Entry Accounts | 1040     |Net Change | Net Amount  | Yes  |
    | R30     | Finance costs            | Cash Flow Entry Accounts | 1050     |Net Change | Net Amount  | Yes  |
    | R30     | Investments              | Cash Flow Entry Accounts | 1070     |Net Change | Net Amount  | Yes  |
    | R30     | Private consumptions     | Cash Flow Entry Accounts | 1090     |Net Change | Net Amount  | Yes  |
    | R30     | VAT due                  | Cash Flow Entry Accounts | 1100     |Net Change | Net Amount  | Yes  |
    | R30     | Other expenses           | Cash Flow Entry Accounts | 1110     |Net Change | Net Amount  | Yes  |
    | R40     | Total cash disbursements | Formula                  | R30      |Net Change | Net Amount  | Yes  |
    | R50     | Surplus                  | Formula                  | R20+R40  |Net Change | Net Amount  | Yes  |
    | R60     | Cash flow funds          | Cash Flow Entry Accounts | 2100     |Net Change | Net Amount  | Yes  |
    | R70     | Total cash flow          | Formula                  | R50+R60  |Net Change | Net Amount  | Yes  |

    > [!NOTE]
    > The row number R10 is used to capture the account totals for receivables. The row number R20 is used to calculate the sum of all cash receipts. The row number R30 is used to capture the account totals for payables. The row number R40 is used to calculate the sum of all cash disbursements. The row number R50 is used to capture the sum of cash surplus. The row number R60 is used to capture the liquid funds. The row number R70 is used to calculate the forecasted cash flow.

## Set up a new column definition

Before printing the cash flow forecast, Ken needs to create the column definition for the numerical information. In the columns, Ken defines the information needed to use from the lines.

- The first column has the number *C10* with the title **Amount** and contains the net change.  
- The second column has the number *C20* with the title **Balance at Date** and contains the transactions for the period.  
- The third column has the number *C30* with the title **Entire Year** and contains the net change in the balances for the entire fiscal year.  
- Finally, Ken assigns the column definition as the default option for the **Forecast** financial report.  

### Set up a new column definition

1. On the **Financial Reports** page, select the new **Forecast** financial report name you created. On the **Home** tab, in the **Process** group, choose **Edit Column Definition**.

2. Create a new column definition with the name **Cash Flow**.

3. Choose the **OK** button.

4. Enter each line exactly as shown in the following table.

    |Column No.|Column Header|Column Type|Ledger Entry Type|Amount Type|Show|  
    |----------|-------------|-----------|-----------------|-----------|----|
    |C10|Amount|Net Change|Entries|Net Amount|Always|  
    |C20|Amount Until Date|Balance at Date|Entries|Net Amount|Always|  
    |C30|Entire Fiscal Year|Entire Fiscal Year|Entries|Net Amount|Always|

## Assig the column definition to the financial report name

Ken is now ready to assign the column definition to the financial report name.  

### Assign the column definition to the financial report name

1. In the **Financial Reports** page, select the **Forecast** financial report, then choose the **Edit Column Definition** action.  
2. In the **Name** field, choose the column definition **Cash Flow** to assign as the default column definition.  

## View and print the cash flow forecast

1. On the **Financial Reports** page, choose the **Forecast** financial report [Financial analytics overview](bi.md)  to view the cash flow forecast.  
2. On the **Financial Report** page, you can select an amount and then view the cash flow forecast entries that make up the amount. In addition, you can view the formula used to calculate that amount. You can also filter the amounts by date and dimension.  
3. Choose the **Print** action to print the cash flow forecast.  

## Related information

[Prepare financial reporting](bi-how-work-account-schedule.md)  
[Analyzing Cash Flow in Your Company](finance-analyze-cash-flow.md)  
[Financial analytics overview](bi.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
