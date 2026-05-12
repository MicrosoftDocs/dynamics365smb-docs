---
title: Set Up Expense Users and Teams
description: Learn how to create expense users, link them to employees, and organize them into teams for expense management in Business Central.
author: brentholtorf
ms.topic: how-to
ms.date: 04/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ms.search.form: 6939, 6949, 6951, 6990
ai-usage: ai-generated
---

# Set up expense users and teams

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Before employees can create expenses, they must be set up as expense users in [!INCLUDE[prod_short](../includes/prod_short.md)]. A user with SUPER or admin rights must define which employees become expense users. You can also organize expense users into teams for easier management and reporting.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Create an expense user

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Expense Users**, and then choose the related link.
2. Choose **New** to open the **Expense User** card.
3. In the **Employee No.** field, select the employee to link to this expense user.
4. Assign the appropriate **Employee Posting Group** to control how the user's expenses are posted to the general ledger.
5. Optionally, assign an **Expense Team Code** to add the user to a team. If you assigned an **Expense Team Code** and the user is team manager, turn on the **Team Manager** field.

> [!IMPORTANT]
> Each expense user must be linked to an employee record that has a valid company email address set in the **Company E-Mail** field. The employee posting group can't be empty.

> [!NOTE]
> When an expense user is linked to an employee, the user inherits the employee’s posting groups and assigned dimensions.

> [!NOTE]
> Only one team manager is allowed per expense team.

## Import expense users from Microsoft Entra ID

Instead of creating users one by one, you can import them from your Microsoft Entra tenant.

1. Open the **Expense Users** page.
2. Choose **More options** > **Import Expense Users**.

This imports all Entra ID users into the expense users table. After importing, open each user's **Expense User Card** and complete the required fields, including the **Employee No.** link and **Employee Posting Group**.

## Set up expense approvers

If your organization uses the approval workflow, you must define who can approve expense reports.

1. Open the **Expense User Card** for the user who should act as an approver.
2. Turn on the **Can Approve** toggle.
3. The **Can approve for these expense users** FastTab displays. Add the expense users that this approver is responsible for.

> [!NOTE]
> An expense user can act as an approver only if their email matches the **Authentication Email** on the **User Card** page. Approvers must have a [!INCLUDE [prod_short](../includes/prod_short.md)] license.

Expense Agent supports a simple approval process with one-to-many relationships. Each approver has a list of users they can approve. Interim approvals aren't supported.

You can also view and edit all approval relationships on the **Expense Approval Setup** page.

## Organize expense users into teams

Expense teams let you group users for reporting and management purposes. Each team can have one team manager. Defining teams simplifies classification and approval structures.

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Expense Teams**, and then choose the related link.
2. Choose **New** to create a team.
3. Enter a code and description for the team.
4. To add expense users to the team, click the number in the **Number of Team Members** field to open the **Expense Users** page. The page is filtered to show only members of the selected team. Choose **New** to add members to the team.

## Next steps

[Set up expense categories and rules](expense-management-categories-rules.md)

## Related information

[Set up expense management](expense-management-setup.md)  
[Manage employee expenses](expense-management-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
