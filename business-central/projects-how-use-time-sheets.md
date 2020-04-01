---
title: Work with Time Sheets for Jobs| Microsoft Docs
description: Describes how to create a time sheet for a job, copy planning lines to it, define work types, fill in the time sheet, and submit it for approval.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: project management, capacity, staff, resource
ms.date: 04/01/2020
ms.author: sgroespe

---
# Use Time Sheets for Jobs
You use the **Create Time Sheets** batch job to set up time sheets for a specified number of time periods or weeks. You must have permissions to be able to create time sheets.

You can copy and use your job planning lines in a time sheet. In that way, you must only enter the information in one place and the line information is always correct.

After you have approved time sheet entries for a job, you can post them to the relevant job journal or resource journal.

Before you can use time sheets, you must set up general information and specify an administrator and one or more approvers of time sheets. For more information, see [Set Up Time Sheets](projects-how-setup-time-sheets.md).

## To create a time sheet
You can use the **Create Time Sheets** batch job to set up time sheets for a specified number of time periods or weeks. Then, the time sheet owner can open it and record time that has been spent on a task.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Time Sheets**, and then choose the related link.
2. On the **Time Sheet List** page, choose the **Create Time Sheets** action.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]  
>   The **Use Time Sheet** and **Time Sheet Owner User ID** fields must be filled in on the card for the resource of the time sheet.

1. Choose the **OK** button.  

You can view the time sheets that you have created on the **Time Sheet list** page.

## To copy job planning lines to a time sheet
The following procedure describes how to quickly add job planning lines to a time sheet.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Time Sheets**, and then choose the related link.  
2. On the **Time Sheet List** page, select a time sheet for the relevant time period, and then choose the **Edit Time Sheet** action.  
3. Choose the **Create lines from job planning** action. Any job planning lines in the time sheet time period are copied to the time sheet for the person or machine in the **Resource No.** field on the time sheet.

## To define work types and add one to a time sheet
You can define the work type for all time sheet lines for jobs. In this way, you can add information that you need to bill the customer for different types of work.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Time Sheets**, and then choose the related link.   
2. Open the relevant time sheet.
3. Choose the **Description** field.  
4. On the **Time Sheet Line Job Detail** page, choose the **Work Type Code** field, and select a work type from the list, such as **Miles**.  
5. If no work types exist, chose the **New** action.
6. On the **Work Types** page, fill in the fields as necessary.
7. Repeat step 4 to assign the new work type to the time sheet.

## To reuse time sheet lines in other time sheets
If your time sheet information remains the same from time period to time period, you can save time by copying the lines from the previous time period. Then, you just enter your time usage for the new period.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Time Sheets**, and then choose the related link.  
2. Open the time sheet for a period later than the period for an existing time sheet with lines.  
3. Choose the **Copy Lines from Previous Time Sheet** action.

The lines are copied, including details such as type and description. For example, if the line is related to a job, the **Job No.** is copied. All copied lines have the status **Open**. You can now modify the lines as needed.

## To fill in a time sheet lines and submit for approval
Time sheet registration is tracked in hours, the standard base unit of measure for resources. By default, a time sheet shows the common work days of Monday through Friday.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Time Sheets**, and then choose the related link.  
2. Select a time sheet for the relevant time period, and then choose the **Edit Time Sheet** action.  
3. Fill in the fields on a line as necessary. Enter the number of hours used by the resource on each day of the week.

    > [!TIP]  
    >   You can review the sum of time sheet hours that you have entered in the **Actual/Budgeted Summary** FactBox.  
4. Repeat step 3 for other work types that the resource performs.
5. Choose the **Submit** action, and then choose the **All open lines** action to submit all lines or the **Selected lines only** action to submit only the lines that are selected on the **Time Sheet** page.  

    > [!NOTE]  
    >   You can only submit time sheet lines for which you have entered time.  
6. To modify information on a line that has been set to **Submitted**, select the line, and then choose the **Reopen** action.

    > [!NOTE]  
    >   A manager may reject a time sheet line that is submitted for approval. If a line has a status of **Rejected**, you can make changes to the line, and then choose **Submit** again.  
7. Choose the **OK** button.

## To approve or reject a time sheet
A time sheet must be submitted for approval before it can be used. You can approve and reject individual lines on a time sheet or send them back to the submitter for additional action. A time sheet can be approved in two ways:

* A time sheet administrator can approve any time sheet.
* The person who is specified in the **Time Sheet Approver User ID** field on a resource card can approve that resource's time sheets. For more information, see [Set Up Time Sheets](projects-how-setup-time-sheets.md).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Manager Time Sheets**, and then choose the related link.
2. Select a time sheet from the list.  
3. On the **Time Sheet** page, choose the **Approve** action, and then choose the **All submitted lines** action to approve all lines or the **Selected lines only** action to approve only the lines that are selected on the **Time Sheet** page.
4. Choose the **OK** button.  
5. Alternatively, choose the **Reject** action and follow steps 4 through 5.  

> [!TIP]  
>   Use the **Time Sheet Status** and **Actual/Budgeted Summary** FactBoxes to get an overview of time sheet information.

After you have approved or rejected a time sheet, it cannot be modified unless it is first reopened. The following procedure explains how to reopen an approved or rejected time sheet.

## To reopen a time sheet
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Manager Time Sheets** or **Time Sheets**, and then choose the related link.
2. Open a time sheet from the list.  

    > [!NOTE]  
    >   You can only reopen lines that have the status **Approved**. You cannot reopen lines that have the status **Rejected**. You cannot reopen a time sheet if it has been posted.  
3. On the **Time Sheet** page, choose the **Reopen** action, and then choose the **All submitted lines** action to reopen all lines or the **Selected lines only** action to reopen only the lines that are selected on the **Time Sheet** page.
4. Choose the **OK** button. The status of the time sheets line or lines is changes to **Submitted**.  

## To post time sheet lines in a resource journal
After you have approved time sheet entries for a resource, you can post them to the relevant resource journal.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Resource Journal**, and then choose the related link.  
2. Choose the **Suggest Lines from Time Sheets** action.  
3. Fill in the fields as necessary.  
4. Choose the **OK** button. Entries for usage are created in the resource journal, where you can modify the information as needed.  
5. Choose the **Post** action.  
6. To verify the posting, choose the **Ledger Entries** action. The **Resource Ledger Entries** page opens showing the result of posting the resource journal.

## To post time sheet lines in a job journal
After you have approved time sheet entries for a job, you can post them to the relevant job journal.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Journal**, and then choose the related link.  
2. Choose the **Suggest Lines from Time Sheets** action.  
3. Fill in the fields as necessary.  
4. Choose the **OK** button. Entries for usage are created in the job journal, where you can modify the information as needed.  

    > [!NOTE]  
    >   Information about work type and whether the work is chargeable is copied from the time sheet line. If needed, you can reduce the quantity of hours and do a partial posting. If you reduce the quantity, then the next time that you choose the **Suggest Lines From Time Sheets** action, the line that is created will contain the remaining quantity of hours.  
5. Choose the **Post** action.  
6. To verify the posting, choose the **Ledger Entries** action. The **Job Ledger Entries** page opens showing the result of posting the resource journal.

## To archive time sheets
After you have posted time sheets, you can archive them for future reference. All time sheets lines must be posted before a time sheet can be archived.

> [!NOTE]  
>   When you archive a time sheet, it is removed from the lists in both the **Time Sheets** page and the **Manager Time Sheets** page.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Move Time Sheets to Archive**, and then choose the related link.  
2. Fill in the fields as necessary, and then choose the **OK** button.  
3. To review archived time sheets, choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Time Sheet Archives** or **Manager Time Sheet Archives**, and then choose the related link.

## See Also
[Project Management](projects-manage-projects.md)  
[Setting Up Project Management](projects-setup-projects.md)    
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)         
[Sales](sales-manage-sales.md)     
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
