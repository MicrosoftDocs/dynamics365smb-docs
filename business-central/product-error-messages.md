---
title: Warnings and error messages
description: Learn how you can troubleshoot and find solutions to error messages when you work in Business Central.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.date: 03/08/2024
ms.service: dynamics-365-business-central
ms.custom: bap-temeplate
---
# Warnings and error messages

During your work day, you might see notifications in [!INCLUDE [prod_short](includes/prod_short.md)] that something went wrong, or that it wasn't possible to post something, for example. In many cases, the notification makes it easy to resolve the matter, or to roll back any changes that you made. In other cases, you might not have the information that you need to get unblocked. This article provides tips on how to make progress.  

## In-product user assistance

The default version of [!INCLUDE [prod_short](includes/prod_short.md)] includes descriptions for most fields, columns, and actions that can be accessed when you choose the name. In combination with teaching tips for important pages, descriptive captions, and instructional text, these tooltips, or callouts, are our current implementation of *embedded user assistance*, which is an important principle in today's world of software design.  

If you have a question about a field or another element of the user interface, choose the name to read a short description. Choose the **Ask Copilot** link if that isn't enough. You can also use the in-product Help pane to find answers to your questions.  

For more information, see [Dynamics 365 Business Central User Assistance Model](/dynamics365/business-central/dev-itpro/user-assistance) in the administration content for [!INCLUDE [prod_short](includes/prod_short.md)].  

## Help and Support page

In [!INCLUDE[prod_short](includes/prod_short.md)], the Help menu item (the question mark in the top right corner) gives you access to the **Help and Support** page, where you can find links to resources that can help you find answers to your questions. For more information, see [Resources for Help and Support](product-help-and-support.md).  

## Help others

If you're an administrator or superuser, you can help others by looking up error messages in the **Error Message Register** page or in the administration center. In many cases, the warning or error message is about setup or lack of permission and similar issues that the superuser or administrator can easily help with. In other cases, you might have to inspect pages to identify the cause. For more information, see [Finding technical information](/dynamics365/business-central/dev-itpro/administration/manage-technical-support#finding-technical-information) in the administration content for [!INCLUDE [prod_short](includes/prod_short.md)].  

## Share error details for faster assistance

To overcome obstacles and minimize downtime, apply the expertise of colleagues or subject matter experts. When an error blocks you, you can easily share the error details when you get assistance.

The details include the error message, error code, and other information that's helpful when troubleshooting an error. By sharing the error details, you can effectively communicate the specific issue you're facing, which helps your colleagues help you.  

You can copy details by choosing the **Share icon** in in-line validation dialogs, or the **Share details** menu in error dialogs.  

In addition to copying error details, you can also choose to share details through Microsoft Teams by choosing **Share details to Teams** to do the following:

* Copy the error details.
* Open the **Share to Teams** window, where you can paste the error details you copied and specify who you want to ask for help. [!INCLUDE [prod_short](includes/prod_short.md)] adds a link to the page where you experienced the error to make troubleshooting easier.

You can also choose to share details by email by choosing **Share details via email** to do the following:

* Copy the error details.
* Open your default email editor, where you can paste the error details you copied and specify who you want to ask for help. [!INCLUDE [prod_short](includes/prod_short.md)] adds a link to the page where you experienced.

## Help yourself

Error messages provide information and actions that make it easier to understand, go to, and resolve errors that come from the platform.

The error messages that the [!INCLUDE [prod_short](includes/prod_short.md)] platform generates contain the full technical details, including field names, in the **Detailed error message** section. Select the **Copy details** icon on inline validation errors or in an error message to access the technical information.

Actions on error messages take you directly to the page where a field is causing the error. You don't have to take time to find the page or field yourself. To resolve the error, just choose the action in the error message and [!INCLUDE [prod_short](includes/prod_short.md)] takes you to the appropriate location.

The following video shows how to use actionable error messages to get unblocked.

> [!VIDEO https://learn-video.azurefd.net/vod/player?id=e104e107-e297-4994-b612-d13349a78bda]

### Tip for developers

If you're a developer, when you call the [TestField](/dynamics365/business-central/dev-itpro/developer/methods-auto/record/record-testfield-joker-joker-errorinfo-method) method, but don't pass in the `ErrorInfo` object, [!INCLUDE [prod_short](includes/prod_short.md)] automatically generates the link to a page where a user can correct the issue. [!INCLUDE [prod_short](includes/prod_short.md)] first gets the lookup or drill-down page for the record, and then finds the card page or lookup page and adds a navigation link to that card page. [!INCLUDE [prod_short](includes/prod_short.md)] doesn't add a link in the following situations:

* If the error is on the page that's currently open.
* If the user doesn't have permission to modify the underlying record.

## Related information

[Resources for Help and Support](product-help-and-support.md)  
[Frequently Asked Questions](across-faq.yml)  
[Tell Me FAQ](ui-search-faq.md)  
[Searching and Filtering FAQ](ui-search-filter-faq.yml)  
[Copy and Paste FAQ](faq-copy-paste.yml)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
