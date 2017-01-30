---
title: 'How to: Set Up Time Sheets| Microsoft Docs'
description: Describes how to prepare the system to use time sheets to manage projects.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: project-madeira
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/27/2016
ms.author: sgroespe

---
# How to: Set Up Time Sheets
Time sheets in Financials handle time registration in weekly increments of seven days. You use them to track the time used on jobs, and you can use them to record simple resource time registration. Before you can use time sheets, you must specify how you want them to be set up and configured.

After you have set up how your organization will use time sheets, you can specify if and how time sheets are approved. Depending on the needs of your organization, you can designate:

* One or more users as the time sheet administrator and approver for all time sheets.
* A time sheet approver for each resource.

When you have set up time sheets, you can create time sheets for resources, assign them to job planning lines, and post time sheet lines. For more information, see [How to: Use Time Sheets](projects-how-use-time-sheets.md).

## To set up general information for time sheets
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Resources Setup**, and then choose the related link.  
2. Fill in the fields as necessary. Choose a field to read a short description of the field or link to more information.
3. For the **Time Sheet by Job Approval** field, select one of the following options.

| Option | Description |
| --- | --- |
| **Never** |The user in the **Time Sheet Approver User ID** field on the resource card approves the time sheet. |
| **Always** |The user in the **Person Responsible** field on the job card approves the time sheet. |
| **Machine Only** |If the machine time sheet is linked with a job, then the user in the **Person Responsible** field on the job card approves the time sheet. If the machine time sheet is linked with a resource, then the user in the **Time Sheet Approver User ID** field on the resource card approves the time sheet. |

## To assign a time sheet administrator
1. In the top right corner, choose the **Search for Page or Report** icon, enter **User Setup**, and then choose the related link.  
2. Add a new user, if the user list does not include the person who you want to be the time sheet administrator. For more information, see the "Creating Users" section in [Get Ready for Business](ui-get-ready-business.md).  
3. Select a user to be a time sheet administrator, and then select the **Time Sheet Admin.** check box.  

**Tip**: It is recommended that you designate only one user to be the time sheet administrator for a company. In the following procedure, you set up a time sheet owner and approver where the time sheet approver is assigned for each resource.  

## To assign a time sheets owner and approver
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Resources**, and then choose the related link.
2. Select the resource for which you want to set up the ability to use time sheets, and then select the **Use Time Sheet** check box.  
3. In the **Time Sheet Owner User ID** field, enter the ID of the owner of the time sheet. The owner can enter time usage on a time sheet and submit it for approval. In general, when the resource is a person, that person is also the owner.  
4. In the **Time Sheet Approver User ID** field, enter the ID of the approver of the time sheet. The approver can approve, reject, or reopen a time sheet.  

**Note**: You cannot change the ID of the time sheet approver if there are time sheets that have not yet been processed and have the status of **Submitted** or **Open**.

## See Also
[Setting Up Project Management](projects-setup-projects.md)  
[Project Management](projects-manage-projects.md)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)         
[Sales](sales-manage-sales.md)      
[Working With Financials](ui-work-product.md)  

