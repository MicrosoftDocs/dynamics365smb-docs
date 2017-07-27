---
    title: Walkthrough: Making Cash Flow Forecasts by Using Account Schedules | Microsoft Docs
    description: This walkthrough describes how you can use account schedules to make cash flow forecasts. Account schedules perform calculations that cannot be done directly in the chart of cash flow accounts. In the account schedules, you can set up subtotals for cash flow receipts and disbursements. These subtotals can be included in new totals that can then be used in making cash flow forecasts.
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
  
-   ADD INCLUDE<!--[!INCLUDE[dyn_nav](includes/demolong_md.md)]--> installed.  
  
-   The cash flow worksheet lines are registered.  
  
## Roles  
 This walkthrough demonstrates tasks that are performed by the following user role:  
  
-   Controller  
  
## Story  
 Ken is a controller at ADD INCLUDE<!--[!INCLUDE[demoname](includes/demoname_md.md)]--> who makes monthly cash flow forecasts. He includes finance, sales, purchase, and fixed assets in the forecast, and then he presents it to CFO Sara for business insight.  
  
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
    |---
    title: Walkthrough: Making Cash Flow Forecasts by Using Account Schedules | Microsoft Docs
    description: This walkthrough describes how you can use account schedules to make cash flow forecasts. Account schedules perform calculations that cannot be done directly in the chart of cash flow accounts. In the account schedules, you can set up subtotals for cash flow receipts and disbursements. These subtotals can be included in new totals that can then be used in making cash flow forecasts.
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

----------------|-------------------|-----------------|-----------------------|-----------------|----------|  
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
 [How to: Create New Account Schedules](how-to-create-new-account-schedules.md)   
 [How to: Set Up Account Schedule Rows Manually](how-to-set-up-account-schedule-rows-manually.md)   
 [How to: Set Up Account Schedule Columns Manually](how-to-set-up-account-schedule-columns-manually.md)   
 [How to: Assign Predefined Column Layouts to Account Schedules](how-to-assign-predefined-column-layouts-to-account-schedules.md)   
 [How to: Create Account Schedule Columns That Calculate Percentages](how-to-create-account-schedule-columns-that-calculate-percentages.md)   
 [How to: Set Up Account Schedules with Overviews](how-to-set-up-account-schedules-with-overviews.md)   
 Account Schedule Names   
 Account Schedule