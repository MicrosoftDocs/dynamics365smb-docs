---
title: Manage Notifications in Business Central
description: You can receive notifications that inform you about status changes or events, for example, an overdue balance or low inventory.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.date: 09/27/2026
ms.search.form: 
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---
# Manage notifications

[!INCLUDE[prod_short](includes/prod_short.md)] can help you work smarter by notifying you about events or changes in status. For example, a notification can warn you that a customer has an overdue balance or that available inventory is lower than the quantity you're about to sell. Notifications appear in the context of your current task. You can review the notification, use an available action, or dismiss it.

Notifications offer advice and recommendations, but you decide how to respond. For example, you might contact the customer or buy more inventory.

## Work with notifications on a page

The notification bar experience in this section applies to the [!INCLUDE[prod_short](includes/prod_short.md)] desktop web client.

### View one notification

When a category contains one notification, the notification appears directly in the notification bar. System notifications appear before regular page notifications. Within each category, the newest notification appears first.

### Expand multiple notifications

When a category contains two or more notifications, the notifications initially collapse behind a row that shows the category and notification count. The collapsed row can preview up to five notification messages, with the newest first. Select the chevron on the row to expand or collapse the category.

### Use an action or dismiss a notification

An expanded notification can include inline actions that help you respond without leaving the page. Select the action that fits your task. To remove a notification, select **Dismiss** when that option is available.

## View notifications while reviewing agent changes

In Business Central version 30.0 and later, page notifications are initially hidden when the data review bar is also present. Select **Show other notifications (N)** to display the notification bar below the data review bar. The button then changes to **Hide other notifications (N)**. Here, *N* is the number of page notifications.

Learn more in [Show page notifications during review](supervise-agent-tasks.md#show-page-notifications-during-review).

## Choose which notifications you receive

When you first start using [!INCLUDE[prod_short](includes/prod_short.md)], all notifications are turned on. You can turn off notifications about events or status changes that don't interest you.

Some notifications also let you specify when they're sent. For example, you can receive a low-inventory notification only for items that you buy from a specific vendor.

Your notification choices and conditions apply only to you.

1. In the upper-right corner, select the **Settings** icon ![Settings.](media/ui-experience/settings_icon_small.png "Settings icon for role center"), and then select **My Settings**.
1. On the **My Settings** page, in the **Notifications** field, select **Change when I receive notifications**.
1. On the page that opens, select or clear the **Enabled** checkbox for a notification.
1. To specify conditions that trigger a notification, select **View filter details**, and then fill in the fields.

## Related information

[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
