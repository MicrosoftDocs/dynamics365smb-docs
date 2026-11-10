---
title: Inspect Pages in Business Central
description: Use page inspection in Business Central to identify page and table details, troubleshoot data, and manage access to inspection information.
ms.topic: concept-article
author: jswymer
ms.author: jswymer
ms.date: 11/10/2026
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Inspect pages in Business Central

The page inspection feature enables you to get details about a page, providing insight into the page design, the different elements that comprise the page, and the source behind the data it displays. Page inspection is especially designed for administrators, power users, support personnel, and developers. It's ideal for learning the data model behind a page and troubleshooting. For example, if you're experiencing a problem with a page, you can use page inspection to get information to pass on to your system administrator or support personnel.

> [!TIP]  
> Through page inspection, you can start Visual Studio Code from within the web client to further investigate and debug source code of an extension. Learn more in [Troubleshoot in Visual Studio Code directly from the web client](/dynamics365/business-central/dev-itpro/developer/devenv-troubleshoot-vscode-webclient) in the Business Central Developer and IT Pro help.

[!INCLUDE [send-report-excel](includes/send-report-excel.md)]

## Work with page inspection

You start page inspection from the **Help & Support** page. Choose the question mark in the top right corner, choose **Help & Support**, and then choose **Inspect pages and data**. Or, you can just use the keyboard shortcut <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>F1</kbd>.

The **Page inspection** pane opens on the side. When the pane first opens, it shows information that pertains to the main page object.

Use the keyboard or pointing device to move focus to different elements on the page. When you select a FactBox or a part on the main page, the bounding area is highlighted by a border, and the **Page Inspection** pane shows information about the selected element. For example, select the list part on the **Sales Order** page to inspect that part. As you navigate to other pages in the application, the **Page Inspection** pane will automatically update with page information as you move along.

Refer to [Inspecting and Troubleshooting Pages](/dynamics365/business-central/dev-itpro/developer/devenv-inspecting-pages) in the [!INCLUDE[dev-itpro-docs](includes/dev-itpro-docs.md)] for information about what is shown in page inspection.

If you don't see the details that you expect to see in the **Page Inspection** pane, you probably don't have the required permissions, as described in the next section.

## Control access to page inspection details

As an administrator, you can control access to the details shown in the **Page Inspection** pane by configuring users' permissions. To grant access to the detailed inspection tabs, give users **Execute** permission on the **System** object **5330**, **Tools, Zoom**. You can assign a permission set that includes this permission, such as **Troubleshoot Tools**. Learn more in [Assign permissions to users and security groups](ui-define-granular-permissions.md).

To view the **Extensions** tab, users also need read permission on the **AllObjWithCaption** and **NAV App Installed App** tables.

Users who don't have **Execute** permission on **System object 5330** can still access the **Page Inspection** pane and see basic page and source details. They can't access the **Table Fields**, **Extensions**, or **Page Filters** tabs.

## Related information

[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
