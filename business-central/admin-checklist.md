---
title: Onboarding Checklists for Business Central Users
description: Configure onboarding checklists in Business Central by selecting tasks, assigning roles or users, and setting completion requirements and task order.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: setup, wizard, checklist
ms.search.form: 1992, 1993, 1994, 1995, 1996
ms.date: 10/14/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---
# Set up onboarding checklists for users

Help users get started in [!INCLUDE[prod_short](includes/prod_short.md)] with a checklist of setup and learning tasks. As an administrator or partner, you can customize the items in the **Get started** checklist, assign them to roles or specific users, and control their order and completion requirements.

Users see checklist items assigned to them or to their current role when the checklist is visible on their Role Center. Checklists aren't limited to a user's first sign-in.

## Add an item to the checklist

Checklist items use existing *guided experience items*, such as setup guides, learning links, videos, and tours. The **Checklist Administration** page lets you select these tasks, not enter an arbitrary link or create a new setup guide.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Checklist Administration**, and select the related link.
2. Select **Create checklist item**.
3. In the **Guided Experience Type** field, select the type of task, such as **Assisted Setup**, **Learn**, or **Video**.
4. In the **Task** field, open the lookup and select an existing task.
5. In the **Completion Requirements** field, select who must complete the item. The options are described in the next section.
6. Assign the item to roles in **Checklist Item Roles**, or to users in **Checklist Users**, depending on the completion requirements.
7. In the **Order ID** field, enter a number greater than zero. Items with lower numbers appear earlier in the checklist.
8. Close the card to return to the checklist.

> [!NOTE]
> The task's description, expected duration, and destination come from the selected guided experience item and are read-only on this page. If the task you need isn't available, ask your partner or developer to add a guided experience item through an extension.

## Choose completion requirements and assignments

The **Completion Requirements** field determines whether you assign the item to roles or specific users.

| Option | Assignment | Completion behavior |
|---|---|---|
| **Anyone with roles** | Add one or more **Role ID** values in **Checklist Item Roles**. | When one user completes the item, it appears completed for other users who see the same item. Use this option for shared tasks. |
| **Everyone with roles** | Add one or more **Role ID** values in **Checklist Item Roles**. | Each user with an assigned role completes the item individually. Use this option for tasks that everyone needs to do. |
| **Specific users** | Add one or more **User ID** values in **Checklist Users**. | Each assigned user completes the item individually. Use this option for tasks intended for named users. |

Roles here are profiles that determine a user's Role Center, not permission sets. Assign at least one role or user so that the item has an audience. Learn more about profiles in [Manage user profiles](admin-users-profiles-roles.md).

> [!NOTE]
> An assisted setup item can appear completed because the underlying setup guide is already completed for the company, regardless of the item's completion requirements.

## Edit an existing checklist item

1. Open **Checklist Administration**.
2. Select the item's **Task** to open its card.
3. To replace the task, select its type in **Guided Experience Type**, then open the **Task** lookup and select the replacement task.
4. Change the completion requirements, assignments, or order as needed.
5. Close the card.

If you select a task that already has a checklist item, you're prompted to open and edit the existing item instead of creating a duplicate.

If existing assignments are present, changing between role-based and specific-user completion requirements asks you to confirm their removal. Assign the appropriate roles or users after changing the requirements. If you replace the task, you can also be prompted to reset users' progress.

## Related information

[Get ready for doing business](ui-get-ready-business.md)  
[Administration](admin-setup-and-administration.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
