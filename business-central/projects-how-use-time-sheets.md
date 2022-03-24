---
title: Use Time Sheets
description: Describes how to create a time sheet, define work types, fill in the time sheet, and submit it for approval.
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: project management, capacity, staff, resource, time sheets
ms.search.form: 950, 951, 973
ms.date: 03/01/2022
ms.author: edupont

---
# Use Time Sheets

You can use time sheets in [!INCLUDE [prod_short](includes/prod_short.md)] to track absence, and to track time and resources that are spent on a project. With time management, you can identify issues early, and avoid delays or cost overruns. With time sheets, a resource can easily report time usage for an individual or a machine, and a manager can easily review the usage and its allocation. This article describes how to create a time sheet, define work types, fill in the time sheet, and submit it for approval.  

You can copy and use your job planning lines in a time sheet. In that way, you must only enter the information in one place and the line information is always correct.

After you have approved time sheet entries for a job, you can post them to the relevant job journal or resource journal.

Before you can use time sheets, you must set up general information and specify an administrator and one or more approvers of time sheets. For more information, see [Set Up Time Sheets](projects-how-setup-time-sheets.md).  

> [!TIP]
> Starting in 2021 release wave 2, you can manage assigned time sheets on a mobile device. However, your administrator may have to enable the **Feature Update: New time sheet experience** feature in the [Feature Management](https://businesscentral.dynamics.com/?page=2610) page to use this capability. For more information, see [Set Up Time Sheets](projects-how-setup-time-sheets.md).

## To create time sheets

You can use the **Create Time Sheets** batch job to set up time sheets for a specified number of time periods or weeks. Then, the time sheet owner can open it and record time that has been spent on a task. You can also [schedule the batch job to run automatically](ui-work-report.md#ScheduleReport).  

> [!IMPORTANT]
> You must have permissions to be able to create time sheets. For more information, see [Set Up Time Sheets](projects-how-setup-time-sheets.md).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Time Sheets**, and then choose the related link.
2. On the **Time Sheets** page, choose the **Create Time Sheets** action.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]  
    > The **Use Time Sheet** and **Time Sheet Owner User ID** fields must be filled in on the card for the resource of the time sheet.

    Optionally, choose the **Schedule** action to specify how often you want the task to run automatically. For example, to configure the task to run weekly for four weeks, in the **Schedule a Report - Create Time Sheets** page, set the **Next Run Date Formula** field to *4W*. For more information, see [Scheduling a Report to Run](ui-work-report.md#ScheduleReport).  
4. Choose the **OK** button.  

You can view the time sheets that you have created on the **Time Sheets** page. Each time sheet consists of one or more lines that define the time that you want to submit for approval. The following table describes the types of lines that you can add to the time sheet.

| **Field** | **Description** |
|---|---|
| | Use to add a note or marker in the **Description** field of the time sheet line. For example, you can use this field to categorize time sheet entries. If you leave the **Type** field empty for a time sheet line, you cannot enter time values in the weekday fields for that line. |
| Absence | Use to register the time you are absent during a work week. To complete the information for the line, specify the type of absence in the **Cause of Absence Code** field. |
| Assembly Order | Used to register time for assembly orders. A time sheet line of this type is created during the posting of assembly order lines for which the resource is set up to use time sheets. You cannot manually select a line of this type. |
| Job | Use to register time usage for a project. To complete the information for the line, specify the job number and the job task number for which you want to register time. You can register time for lines that you have not scheduled.|
| Resource | Use to register time usage for a resource. To complete the information for the line, provide a description of the work. |
| Service | Use to register time usage for a service order or service credit memo. |

For example, to submit a time sheet for a work week where you worked on cleaning tasks most days but had one day off due to medical appointments, you would add lines as illustrated in the following table.

| Type | Description | Work Type Code | Absence Type Code |
|--|--|--|--|
| Resource | Work hours | Cleaning |  |
| Absence | Time off |  | Health |
|  | I had to take Tuesday off due to a medical appointment. |  |  |

In this hypothetical example, you would then register the relevant hours across the relevant days in the fields for each weekday.  

> [!TIP]
> In most cases, your company will have predefined work types for the various types of lines. In those cases, you just choose the relevant work type from the list, and then you add your own description.  
>
> Choose the work type by choosing the :::image type="icon" source="media/assist-edit-icon.png" border="false"::: button in the **Description** field, by choosing the **Activity Details** action and then specifying it in the page that opens, or by choosing it in the **Work Type Code** field or the **Absence Type Code** field, respectively. In this case, you can ignore the [To define work types and add one to a time sheet](#to-define-work-types-and-add-one-to-a-time-sheet) section.  

## To reuse time sheet lines in other time sheets

If your time sheet information remains the same from time period to time period, you can save time by copying the lines from the previous time period. Then, you just enter your time usage for the new period.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Time Sheets**, and then choose the related link.  
2. Open the time sheet for a period later than the period for an existing time sheet with lines.  
3. Choose the **Copy Lines from Previous Time Sheet** action.

The lines are copied, including details such as type and description. For example, if the line is related to a job, the **Job No.** is copied. All copied lines have the status **Open**. You can now modify the lines as needed.

## To copy job planning lines to a time sheet
The following procedure describes how to quickly add job planning lines to a time sheet.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Time Sheets**, and then choose the related link.  
2. On the **Time Sheets** page, select a time sheet for the relevant time period.  
3. Choose the **Create lines from job planning** action. Any job planning lines in the time sheet time period are copied to the time sheet for the person or machine in the **Resource No.** field on the time sheet.

## To define work types and add one to a time sheet

You can define the work type for all time sheet lines for service orders, job orders, and resources. In this way, you can add information that you need to bill the customer for different types of work.  

1. In the **Time Sheets** page, choose the relevant time sheet.
2. On the first of the lines in the **Lines** section, choose the **Type** field, and then choose the relevant type, such as *Resource*.  
3. Choose the **Description** field, and then, in the **Time Sheet Line Resource Detail** page, fill in the fields. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  
    1. If no work types exist, chose the **New** action.
    2. On the **Work Types** page, fill in the fields as necessary, and then return to the time sheet.
4. Fill in the rest of the time sheet. For more information, see the [To fill in time sheet lines and submit for approval](#to-fill-in-time-sheet-lines-and-submit-for-approval) section.  

> [!TIP]
> Similar steps apply to defining absence codes.

## To fill in time sheet lines and submit for approval

Time sheet registration is tracked in hours, the standard base unit of measure for resources. By default, a time sheet shows the common work days of Monday through Friday.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Time Sheets**, and then choose the related link.  
2. Select a time sheet for the relevant period.
3. Fill in the fields on a line as necessary. Enter the number of hours used by the resource on each day of the week.  

    In most cases, to track work, you add a line of type *Resource*, and then you register hours spent each day. If you want to register absence, you add a line of type *Absence*.  

    > [!TIP]  
    > You can review the sum of time sheet hours that you have entered in the **Actual/Budgeted Summary** FactBox.  
4. Repeat step 3 for other work types that the resource performs.  

    Next, you must decide if you want to submit all lines on the time sheet, or if you want to submit individual lines.  

    * To submit the time sheet for one or more lines, choose the relevant line, and then choose the **Submit** action.

        In the submission page, choose the **Selected lines only** option. The line changes state from *Open* to *Submitted*.
    * To submit the time sheet for all open lines, choose the **Submit** action at the top of the **Time Sheet** page.  

        You'll be asked to confirm that you want to submit all open lines on the current time sheet.  

    > [!NOTE]  
    > You can only submit time sheet lines for which you have entered time.  
5. To modify information on a line that has been set to **Submitted**, select the line, and then choose the **Reopen** action.

    > [!NOTE]  
    >   A manager may reject a time sheet line that is submitted for approval. If a line has the status **Rejected**, you can make changes to the line, and then choose **Submit** again.  
6. Choose the **OK** button.

## To approve or reject a time sheet
A time sheet must be submitted for approval before it can be used. You can approve and reject individual lines on a time sheet or send them back to the submitter for additional action. A time sheet can be approved in two ways:

* A time sheet administrator can approve any time sheet.
* The person who is specified in the **Time Sheet Approver User ID** field on a resource card can approve that resource's time sheets. For more information, see [Set Up Time Sheets](projects-how-setup-time-sheets.md).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Manager Time Sheets**, and then choose the related link.
2. Select a time sheet from the list.  
3. On the **Time Sheet** page, 
    1. Choose the **Process** action, then choose the **Approve** action.
    2. Choose the **All submitted lines** action to approve all lines or the **Selected lines only** action to approve only the lines that are selected on the **Time Sheet** page.
4. Choose the **OK** button.  
5. Alternatively, choose the **Reject** action and follow steps 4 through 5.  

> [!TIP]  
>   Use the **Time Sheet Status** and **Actual/Budgeted Summary** FactBoxes to get an overview of time sheet information.

After you have approved or rejected a time sheet, it cannot be modified unless it is first reopened. The following procedure explains how to reopen an approved or rejected time sheet.

## To reopen a time sheet
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Manager Time Sheets** or **Time Sheets**, and then choose the related link.
2. Open a time sheet from the list.  

    > [!NOTE]  
    >   You can only reopen lines that have the status **Approved**. You cannot reopen lines that have the status **Rejected**. You cannot reopen a time sheet if it has been posted.  
3. On the **Time Sheet** page, choose the **Reopen** action, and then choose the **All submitted lines** action to reopen all lines or the **Selected lines only** action to reopen only the lines that are selected on the **Time Sheet** page.
4. Choose the **OK** button. The status of the time sheets line or lines is changes to **Submitted**.  

## To view and approve time sheets by job

On a job, you can specify a person who is responsible for the job. That information is linked to time sheet lines, and can be used to provide a list of the time sheets that a project manager is required to review and approve. For example, the team project manager may be responsible for certain jobs in your company. In that case, the manager should be designated as the **Person Responsible** on the job card. In this view of time sheet information, you can see the job tasks associated with a job and the quantity of hours used.

> [!NOTE]
> To be able to approve time sheets in the **Manager Time Sheet by Job** window, you must first select a **Time Sheet by Job Approval** option in the **Resources Setup** page. For more information, see [Set Up Resources](projects-how-setup-resources.md).

### To approve or reject a time sheet by job

1. In the **Search** box, enter **Manager Time Sheet by Job**, and then choose the related link. [!INCLUDE[prod_short](includes/prod_short.md)] displays a list of time sheet lines associated with the jobs for which you have responsibility.
2. Choose the **Approve** action, and then choose the **All submitted lines** action to approve all lines or the **Selected lines only** action to approve only the lines that are selected on the **Time Sheet** page.

    > [!NOTE]
    > You can only approve time sheets that have the status of **Submitted**.

3. To provide additional information about the approval or rejection, select the **Related** action, then select **Comments** and then **Line Comments** and enter comments.
4. Choose the **OK** button.

> [!NOTE]
> After you have approved or rejected a time sheet line by job, it cannot be reopened or modified in the **Time Sheet** window.

## To post time sheet lines in a resource journal
After you have approved time sheet entries for a resource, you can post them to the relevant resource journal.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Resource Journals**, and then choose the related link.  
2. Choose the **Suggest Lines from Time Sheets** action.  
3. On the **Suggest Res Jnl. Lines** page, in the fields as necessary.  
4. Choose the **OK** button. Entries for usage are created in the resource journal, where you can modify the information as needed.  
5. Choose the **Post** action.  
6. To verify the posting, choose the **Ledger Entries** action. The **Resource Ledger Entries** page opens showing the result of posting the resource journal.

## To post time sheet lines in a job journal
After you have approved time sheet entries for a job, you can post them to the relevant job journal.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Journals**, and then choose the related link.  
2. Choose the **Suggest Lines from Time Sheets** action.  
3. On the **Suggest Job Jnl. Lines** page, fill in the fields as necessary.  
4. Choose the **OK** button. Entries for usage are created in the job journal, where you can modify the information as needed.  

    > [!NOTE]  
    >   Information about work type and whether the work is chargeable is copied from the time sheet line. If needed, you can reduce the quantity of hours and do a partial posting. If you reduce the quantity, then the next time that you choose the **Suggest Lines From Time Sheets** action, the line that is created will contain the remaining quantity of hours.  
5. Choose the **Post** action.  
6. To verify the posting, choose the **Ledger Entries** action. The **Job Ledger Entries** page opens showing the result of posting the resource journal.

## To archive time sheets
After you have posted time sheets, you can archive them for future reference. All time sheets lines must be posted before a time sheet can be archived.

> [!NOTE]  
>   When you archive a time sheet, it is removed from the lists in both the **Time Sheets** page and the **Manager Time Sheets** page.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Time Sheets**, and then choose the related link.
2. Select the **Move Time Sheets to Archive** action.  
3. On the **Move Time Sheets to Archive** page, fill in the fields as necessary, and then choose the **OK** button.  
4. To review archived time sheets, choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Time Sheet Archives** or **Manager Time Sheet Archives**, and then choose the related link.

## See Also
[Project Management](projects-manage-projects.md)  
[Setting Up Project Management](projects-setup-projects.md)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]