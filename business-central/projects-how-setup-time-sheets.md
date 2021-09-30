---
title: Set Up Time Sheets and Their Approval
description: You set up time sheets to track the time used on jobs and using resources, helping you with project management, staffing, and capacity
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: project management, capacity, staff, resource, time sheet
ms.date: 10/01/2021
ms.author: edupont

---
# Set Up Time Sheets

Time sheets in [!INCLUDE[prod_short](includes/prod_short.md)] handle time registration in weekly increments of seven days. You use them to track the time used on jobs, and you can use them to record simple resource time registration. Before you can use time sheets, you must specify how you want them to be set up and configured.

After you have set up how your organization will use time sheets, you can specify if and how time sheets are approved. Depending on the needs of your organization, you can designate:

* One or more users as the time sheet administrator and approver for all time sheets.
* A time sheet approver for each resource.

When you have set up time sheets, you can create time sheets for resources, assign them to job planning lines, and post time sheet lines. For more information, see [Use Time Sheets](projects-how-use-time-sheets.md).  

## Set up time sheets with the assisted setup guide

[!INCLUDE [2021_releasewave2](includes/2021_releasewave2.md)]

Starting in 2021 release wave 2, you can use an assisted setup guide to help you set up time sheets.  

> [!TIP]
> You must enable the **Feature Update: New time sheet experience** feature in the [Feature Management](https://businesscentral.dynamics.com/?page=2610) page to use this capability.
>
> The same feature also makes it easy to manage time sheets on a mobile device.

The assisted setup guide takes you through the following steps:

1. Set up the participants in the time sheet processes
2. Specify the first day of a work week in this organization

    The first day of a work week will be the default first day for all time sheets.
3. Specify the person who administers time sheets

    This person can edit and delete all time sheets. Optionally, add the same role to other people in the **User Setup** page.
4. Set up the resources who will use time sheets, and the people who will approve time sheets

    > [!NOTE]
    > For projects and jobs, the users of time sheets are *resources*, not employees. So to be able to track the work of your employees, you must associate resources with employees in the setup guide.

At the end of the setup guide, you can choose to let [!INCLUDE [prod_short](includes/prod_short.md)] create time sheets based on your configuration. Alternatively, run the assisted setup guide again, or complete the setup manually.  

## Set up time sheets manually

The following sections describe how to set up time sheets if you do not use the **Set up time sheets** assisted setup guide.  

### To set up general information for time sheets manually

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Resources Setup**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. For the **Time Sheet by Job Approval** field, select one of the following options.

| Option | Description |
| --- | --- |
| **Never** |The user in the **Time Sheet Approver User ID** field on the resource card approves the time sheet. |
| **Always** |The user in the **Person Responsible** field on the job card approves the time sheet. |
| **Machine Only** |If the machine time sheet is linked with a job, then the user in the **Person Responsible** field on the job card approves the time sheet. If the machine time sheet is linked with a resource, then the user in the **Time Sheet Approver User ID** field on the resource card approves the time sheet. |

### To assign a time sheet administrator manually

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Setup**, and then choose the related link.  
2. Add a new user if the user list does not include the person who you want to be the time sheet administrator. For more information, see [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).
3. Select a user to be a time sheet administrator, and then select the **Time Sheet Admin.** check box.  

> [!TIP]  
> It is recommended that you designate only one user to be the time sheet administrator for a company. In the following procedure, you set up a time sheet owner and approver where the time sheet approver is assigned for each resource.  

### To assign a time sheets owner and approver manually

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Resources**, and then choose the related link.
2. Select the resource for which you want to set up the ability to use time sheets, and then select the **Use Time Sheet** check box.  
3. In the **Time Sheet Owner User ID** field, enter the ID of the owner of the time sheet. The owner can enter time usage on a time sheet and submit it for approval. In general, when the resource is a person, that person is also the owner.  
4. In the **Time Sheet Approver User ID** field, enter the ID of the approver of the time sheet. The approver can approve, reject, or reopen a time sheet.  

> [!NOTE]  
> You cannot change the ID of the time sheet approver if there are time sheets that have not yet been processed and have the status of **Submitted** or **Open**.

## See Also

[Use Time Sheets for Jobs](projects-how-use-time-sheets.md)  
[To create time sheets](projects-how-use-time-sheets.md#to-create-time-sheets)  
[Record Consumption or Usage for Jobs](projects-how-record-job-usage.md)  
[Setting Up Project Management](projects-setup-projects.md)  
[Project Management](projects-manage-projects.md)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]