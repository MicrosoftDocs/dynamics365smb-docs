---
title: Set up time sheets and their approval
description: Learn how to use time sheets to track time for projects and resources.
ms.reviewer: bholtorf
author: brentholtorf
ms.author: bholtorf
mw.reviewer: ivkoleti
ms.topic: how-to
ms.search.keywords: project management, capacity, staff, resource, time sheet
ms.search.form: 977, 462, 76, 77, 462, 946_Primary, 949_Primary
ms.date: 07/27/2023
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Set up time sheets

Time sheets in [!INCLUDE[prod_short](includes/prod_short.md)] handle time registration in weekly increments of seven days. You can use them to track the time used on projects, and you can use them to record simple resource time registration. Before you use time sheets, you must specify which users will submit time sheets and how you want to configure time sheets.  

> [!TIP]
> The people who use time sheets are *resources*. For example, that lets you use time sheets to track the work of non-employees. To track the work of employees, or to use time sheets to track employee absence, you must associate employees with resources. There's an assisted setup guide that can help you do that. To learn about the guide, go to [Set up time sheets with the assisted setup guide](#set-up-time-sheets-with-the-assisted-setup-guide).  

Optionally, specify whether and how time sheets are approved. Depending on the needs of your organization, you can designate:

* One or more users as the time sheet administrator and approver for all time sheets.
* A time sheet approver for each resource.

When you have set up time sheets, you can create time sheets for resources, and the resources can post time sheet lines. Optionally, assign time sheets to project planning lines. To learn more, go to [Use Time Sheets](projects-how-use-time-sheets.md).  

## Set up time sheets with the assisted setup guide

An assisted setup guide can help you set up time sheets.  

> [!TIP]
> If you're a version earlier than 2023 release wave 1 (v22), you must enable the **Feature Update: New time sheet experience** feature in the [Feature Management](https://businesscentral.dynamics.com/?page=2610) page to use this capability.
>
> This setting also lets you use time sheets on mobile devices.

Open the **Set Up Time Sheets** assisted setup guide from the [Assisted Setup](https://businesscentral.dynamics.com/?page=1801) page.

The assisted setup guide takes you through the following steps:

1. Set up the participants in the time sheet processes.

    The first page in the guide shows you the number of users in your [!INCLUDE [prod_short](includes/prod_short.md)]. It also shows other required and optional information.  
2. Specify the first day of a work week in this organization.

    The first day of a work week is the default first day for all time sheets.
3. Specify the person who administers time sheets.

    This person can edit and delete all time sheets. Optionally, add the same role to other people in the **User Setup** page.
4. Set up the resources who will use time sheets, and the people who will approve time sheets.

At the end of the setup guide, you can choose to let [!INCLUDE [prod_short](includes/prod_short.md)] create time sheets based on your configuration. View the new time sheets in the **Time Sheets** page, which you can open [here](https://businesscentral.dynamics.com/?page=951). Alternatively, run the assisted setup guide again, or complete the setup manually.

> [!IMPORTANT]
> If you're using 2023 release wave 1 (v22) or later, to ensure that you can manage time sheets on mobile devices, you must manually turn on the **Use New Time Sheet Experience** option for the time sheet setup, as described in the next procedure.

## Set up time sheets manually

The following sections describe how to set up time sheets if you don't use the **Set Up Time Sheets** assisted setup guide.  

### Set up general information for time sheets manually

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Resources Setup**, and then choose the related link.  
1. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

   > [!IMPORTANT]
   > If you're using 2023 release wave 1 (v22) or later, to ensure that you can manage time sheets on mobile devices, turn on the **Use New Time Sheet Experience** option.
1. For the **Time Sheet by Job Approval** field, select one of the following options.

| Option | Description |
| --- | --- |
| **Never** |The user in the **Time Sheet Approver User ID** field on the resource card approves the time sheet. |
| **Always** |The user in the **Person Responsible** field on the Project Card approves the time sheet. |
| **Machine Only** |If the machine time sheet is linked with a job, then the user in the **Person Responsible** field on the Project Card approves the time sheet. If the machine time sheet is linked with a resource, then the user in the **Time Sheet Approver User ID** field on the resource card approves the time sheet. |

### Assign a time sheet administrator manually

1. [!INCLUDE[open-search](includes/open-search.md)], enter **User Setup**, and then choose the related link.  
2. Select the user who will be the time sheet administrator, and then select the **Time Sheet Admin.** checkbox.  

> [!TIP]  
> We recommend that you designate only one user as the time sheet administrator for a company. In the following procedure, you set up a time sheet owner and approver where the time sheet approver is assigned for each resource.  

### Assign a time sheets owner and approver manually

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Resources**, and then choose the related link.
2. Select the resource for which you want to set up the ability to use time sheets, and then select the **Use Time Sheet** checkbox.  
3. In the **Time Sheet Owner User ID** field, enter the ID of the owner of the time sheet. The owner can enter time usage on a time sheet and submit it for approval. Typically, when the resource is a person, that person is also the owner.  
4. In the **Time Sheet Approver User ID** field, enter the ID of the approver of the time sheet. The approver can approve, reject, or reopen a time sheet.  

> [!NOTE]  
> You can't change the ID of the time sheet approver if there are time sheets that haven't been processed and have the status of **Submitted** or **Open**.

## Related information

[Use Time Sheets for Projects](projects-how-use-time-sheets.md)  
[How To Create Time Sheets](projects-how-use-time-sheets.md#create-time-sheets)  
[Record Consumption or Usage for Projects](projects-how-record-job-usage.md)  
[Setting Up Project Management](projects-setup-projects.md)  
[Project Management](projects-manage-projects.md)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
