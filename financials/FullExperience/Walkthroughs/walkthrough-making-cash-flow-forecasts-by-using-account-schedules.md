---
title: "Walkthrough: Making Cash Flow Forecasts by Using Account Schedules"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "cash flow, account schedules"
  - "cash flow, forecast example"
ms.assetid: 3190b6bb-e955-4975-93f5-0f562ba23626
caps.latest.revision: 15
ms.author: "sgroespe"
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
# Walkthrough: Making Cash Flow Forecasts by Using Account Schedules
This walkthrough describes how you can use account schedules to make cash flow forecasts. Account schedules perform calculations that cannot be done directly in the chart of cash flow accounts. In the account schedules, you can set up subtotals for cash flow receipts and disbursements. These subtotals can be included in new totals that can then be used in making cash flow forecasts.  
  
## About This Walkthrough  
 This walkthrough describes the following tasks:  
  
-   Setting up a new cash flow account schedule name.  
  
-   Setting up account schedule lines.  
  
-   Setting up a new column layout.  
  
-   Assigning a column layout to an account schedule.  
  
-   Viewing and printing the cash flow forecast.  
  
### Prerequisites  
 To complete this walkthrough, you will need:  
  
-   [!INCLUDE[dyn_nav](../ApplicationDesign/includes/dyn_nav_md.md)] with the [!INCLUDE[demolong](../ApplicationDesign/includes/demolong_md.md)] installed.  
  
-   The cash flow worksheet lines are registered.  
  
## Roles  
 This walkthrough demonstrates tasks that are performed by the following user role:  
  
-   Controller  
  
## Story  
 Ken is a controller at [!INCLUDE[demoname](../BusinessFunctionality/IntegratingWithMicrosoftDynamicsCRM/includes/demoname_md.md)] who makes monthly cash flow forecasts. He includes finance, sales, purchase, and fixed assets in the forecast, and then he presents it to CFO Sara for business insight.  
  
## Setting Up a New Account Schedule Name  
 An account schedule consists of a cash flow account schedule name with a series of lines and a column layout.  
  
### To set up a new account schedule name  
  
1.  In the **Search** box, enter **Account Schedules**, and then choose the related link.  
  
2.  In the **Account Schedule Names** window, on the **Home** tab, in the **New** group, choose **New** to create a new cash flow account schedule name.  
  
3.  In the **Name** field, enter **Forecast**.  
  
4.  In the **Description** field, enter **Cash Flow Forecast**.  
  
5.  Leave the **Default Column Layout** and **Analysis View Name** fields blank.  
  
## Setting Up Account Schedule Lines  
 After an account schedule name is set up, Ken defines each line that appears in the cash flow account schedule. Ken defines lines that can be shown in reports in addition to lines that are only for calculation purposes.  
  
### To set up account schedule lines  
  
1.  In the **Account Schedule Names** window, select the new **Forecast** account schedule name that you have created. On the **Home** tab, in the **Process** group, choose **Edit Account Schedule**.  
  
2.  In the **Account Schedule** window, enter each line exactly as shown in the following table.  
  
    > [!NOTE]  
    >  Using the **Insert CF Accounts** function, you can quickly mark the cash flow accounts from the chart of cash flow accounts and copy them to account schedule lines.  
  
    |Row No.|Description|Totaling Type|Totaling|Row Type|Amount Type|Show|  
    |-------------|-----------------|-------------------|--------------|--------------|-----------------|----------|  
    |R10|Receivables|Cash Flow Entry Accounts|0010|Net Change|Net Amount|Yes|  
    |R10|Open sales orders|Cash Flow Entry Accounts|0020|Net Change|Net Amount|Yes|  
    |R10|Rentals|Cash Flow Entry Accounts|0030|Net Change|Net Amount|Yes|  
    |R10|Financial assets|Cash Flow Entry Accounts|0040|Net Change|Net Amount|Yes|  
    |R10|Fixed assets disposal|Cash Flow Entry Accounts|0050|Net Change|Net Amount|Yes|  
    |R10|Private investments|Cash Flow Entry Accounts|0060|Net Change|Net Amount|Yes|  
    |R10|Miscellaneous receipts|Cash Flow Entry Accounts|0070|Net Change|Net Amount|Yes|  
    |R10|Open service orders|Cash Flow Entry Accounts|0080|Net Change|Net Amount|Yes|  
    |R20|Total Cash Receipts|Formula|R10|Net Change|Net Amount|Yes|  
    |R30|Payables|Cash Flow Entry Accounts|1010|Net Change|Net Amount|Yes|  
    |R30|Open purchase orders|Cash Flow Entry Accounts|1020|Net Change|Net Amount|Yes|  
    |R30|Personnel costs|Cash Flow Entry Accounts|1030|Net Change|Net Amount|Yes|  
    |R30|Running costs|Cash Flow Entry Accounts|1040|Net Change|Net Amount|Yes|  
    |R30|Finance costs|Cash Flow Entry Accounts|1050|Net Change|Net Amount|Yes|  
    |R30|Investments|Cash Flow Entry Accounts|1070|Net Change|Net Amount|Yes|  
    |R30|Private consumptions|Cash Flow Entry Accounts|1090|Net Change|Net Amount|Yes|  
    |R30|VAT due|Cash Flow Entry Accounts|1100|Net Change|Net Amount|Yes|  
    |R30|Other expenses|Cash Flow Entry Accounts|1110|Net Change|Net Amount|Yes|  
    |R40|Total cash disbursements|Formula|R30|Net Change|Net Amount|Yes|  
    |R50|Surplus|Formula|R20\+R40|Net Change|Net Amount|Yes|  
    |R60|Cash Flow Funds|Cash Flow Entry Accounts|2100|Net Change|Net Amount|Yes|  
    |R70|Total Cash Flow|Formula|R50\+R60|Net Change|Net Amount|Yes|  
  
    > [!NOTE]  
    >  The row number R10 is used to capture the account totals for receivables. The row number R20 is used to calculate the sum of all cash receipts. The row number R30 is used to capture the account totals for payables. The row number R40 is used to calculate the sum of all cash disbursements. The row number R50 is used to capture the sum of cash surplus. The row number R60 is used to capture the liquid funds. The row number R70 is used to calculate the forecasted cash flow.  
  
3.  Choose the **OK** button.  
  
## Setting Up a New Column Layout  
 Before Ken can print the cash flow forecast, he needs to create the column layout for the numerical information. In the columns, he defines the information that he wants to use from the lines.  
  
-   The first column has the number C10 with the title Amount and contains the Net Change.  
  
-   The second column has the number C20 with the title Balance at Date and contains the transactions for the period.  
  
-   The third column has the number C30 with the title Entire Year and contains the net change in the balances for the entire fiscal year.  
  
-   Finally, he assigns the column layout as the default column layout for the account schedule **Forecast**.  
  
### To set up a new column layout  
  
1.  In the **Account Schedule Names** window, select the new **Forecast** account schedule name that you have created. On the **Home** tab, in the **Process** group, choose **Edit Column Layout Setup**.  
  
2.  Create a new column layout with the name **Cash Flow**.  
  
3.  Enter each line exactly as shown in the following table.  
  
    |Column No.|Column Header|Column Type|Ledger Entry Type|Amount Type|Show|  
    |----------------|-------------------|-----------------|-----------------------|-----------------|----------|  
    |C10|Amount|Net Change|Entries|Net Amount|Always|  
    |C20|Amount until Date|Balance at Date|Entries|Net Amount|Always|  
    |C30|Entire Fiscal Year|Entire Fiscal Year|Entries|Net Amount|Always|  
  
4.  Choose the **OK** button.  
  
## Assigning the Column Layout to the Account Schedule Name  
 Ken is now ready to assign the column layout to the account schedule name.  
  
### To assign the column layout to the account schedule name  
  
1.  In the **Account Schedule Names** window, select **Forecast** in the **Name** field.  
  
2.  In the **Default Column Layout** field, choose the column layout **Cash Flow** to assign as the default column layout.  
  
### To view and print the cash flow forecast  
  
1.  In the **Account Schedule Names** window, on the **Home** tab, in the **Process** group, choose **Overview** to view the cash flow forecast.  
  
2.  In the **Acc. Schedule Overview** window, you can select an amount and then view the cash flow forecast entries that make up the amount. In addition, you can view the formula that is used to calculate the amount. You can also filter the amounts by date and dimension.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Print** to print the cash flow forecast.  
  
## See Also  
 [How to: Create New Account Schedules](../BusinessIntelligence/how-to-create-new-account-schedules.md)   
 [How to: Set Up Account Schedule Rows Manually](../BusinessIntelligence/how-to-set-up-account-schedule-rows-manually.md)   
 [How to: Set Up Account Schedule Columns Manually](../BusinessIntelligence/how-to-set-up-account-schedule-columns-manually.md)   
 [How to: Assign Predefined Column Layouts to Account Schedules](../BusinessIntelligence/how-to-assign-predefined-column-layouts-to-account-schedules.md)   
 [How to: Create Account Schedule Columns That Calculate Percentages](../BusinessIntelligence/how-to-create-account-schedule-columns-that-calculate-percentages.md)   
 [How to: Set Up Account Schedules with Overviews](../BusinessIntelligence/how-to-set-up-account-schedules-with-overviews.md)   
 Account Schedule Names   
 Account Schedule