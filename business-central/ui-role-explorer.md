---
title: Exploring and navigating pages and reports per role
description: You can get an overview of all the business features that are available for your role, and for other roles, with the Role Explorer.
author: jswymer
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: role explorer, find features, navigate
ms.search.form: RoleExplorer, 9020, 9022, 9027, 9024
ms.date: 03/10/2025
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Finding pages and reports with the role explorer

You can get an overview of the pages and reports that make up the features that people your business role often use. You can also explore what's available for other roles. This article refers to the overview of pages and reports as the *role explorer*.

In addition to the overview, the role explorer provides actions that open pages or reports, for example, so you can explore the information that the page or report includes. You can also use the role explorer as a way to get around in [!INCLUDE[prod_short](includes/prod_short.md)].

[!INCLUDE [about-ui-learn](includes/about-ui-learn.md)]

## Open the role explorer

You can open the role explorer from role centers, list pages, and the **Tell Me** window.

- On your role center or any list page, choose the ![Menu button.](media/ui_menu_button.png "Menu button") button, or select <kbd>Shift</kbd>+<kbd>F12</kbd>.
- In the **Tell Me** window, choose the **exploring pages** action.

## Open the role explorer filtered to show reports

You can open the role explorer in a filtered view that only shows reports:

- On your role center or any list page, choose the **All Reports** action.
- In the **Tell Me** window, choose the **exploring reports** action.

## Open pages and reports

The actions that open pages or reports are organized under nodes that are named after application areas. You can collapse or expand each node individually, or all nodes together.

- To expand/collapse an individual top-level or subnode, choose the node.
- To expand/collapse all top-level nodes on the page, but leave the subnodes as they are, choose **...** at the top, then choose **Expand** or **Collapse**.
- To expand/collapse all top-levels node and all subnodes under it, choose **...** at the top, then choose the **Expand All** or **Collapse All** action.

## Search for pages and reports

To quickly locate a page or report, select **Find**, and then enter a word or phrase for what you want to find. Role explorer highlights any matching text. If the page or report is hidden in a collapsed node, the collapsed node is marked with a dot.

## Explore other roles

To explore roles other than your own, select **Explore more roles**. Role explorer displays each role under its own heading, with links to its features. You can find and go to features just like you do when exploring your role.

> [!NOTE]
> You can only access roles that are set up to show in the role explorer. If a role isn't available, it probably isn't set up to show. To learn more, go to [Manage Profiles](admin-users-profiles-roles.md).

When you explore other roles, you can also narrow down your exploration by using the **Report & Analysis** and **Administration** actions.

- **Report & Analysis** filters the role explorer to show only reports and analysis features.
- **Administration** filters the role explorer to show only pages for administrative tasks, such as pages related to how you set up your [!INCLUDE [prod_short](includes/prod_short.md)].

> [!TIP]
> For developers, you categorize pages and reports by setting the [UsageCategory property](/dynamics365/business-central/dev-itpro/developer/properties/devenv-usagecategory-property) in the object's AL code.
<!--
 
## Role explorer actions

There a several actions along the top of the role explorer to help you locate features of your role and other roles.

|Action|Description|
|------|------|
|**All**|Shows all features that are related to the role.|
|**Find**|Lets you enter a word or phrase to quickly locate feature names that match.|
|**Explore more roles**|All business features that are available for all roles including your own. When exploring all roles, the other actions work the same way, except for all roles shown. **NOTE:** You can only access roles that are set up to show in role explorer. For more information, see [Manage Profiles](admin-users-profiles-roles.md).  |
|**Report & Analysis**|This action Shows only those features that are categorized as reports and analysis features.|
|**Administration**|Shows only those features that are categorized as administration features.|

<!--
Choose the **Find** action at the top of the role explorer to quickly locate feature names that contain a certain term.

Choose the **Explore more roles** action at the top of the role explorer to get an overview of all business features that are available for all roles including your own.

> [!NOTE]
> Only Role Center actions for profiles where the **Show in Role Explorer** check box is selected will appear on the extended version of the role explorer (shown with the **Explore more roles** action). For more information, see [Manage Profiles](admin-users-profiles-roles.md).
-->

## Expand and collapse nodes

The actions that open pages or reports are organized under nodes named after the features or application areas. You can collapse or expand each node individually, and you can collapse or expand all nodes.

- To expand or collapse a top-level or subnode, choose the node.
- To expand or collapse all top-level nodes on the page, choose the **Expand** or **Collapse** action.
- To expand or collapse all top-level nodes and their subnodes:
  - Select the <kbd>Ctrl</kbd>+<kbd>Shift</kbd> keys while you choose the **Expand** or **Collapse** action.
  - Choose **...**, and then choose the **Expand All** or **Collapse All** action.

## Learn more about a page or report

[!INCLUDE[2025_releasewave1](includes/2025_releasewave1.md)]

Teaching tips are available for some pages and reports. When that's the case, when you hover over the action for the page or report an information icon displays next to the name. Select the icon to learn more about the page or report.

:::image type="content" source="media/report-explorer-more-information.png" alt-text="Example of how the more information window is shown on an element on the role explorer." lightbox="media/report-explorer-more-information.png":::

## Explore a page or report

[!INCLUDE[2025_releasewave1](includes/2025_releasewave1.md)]

You can open the pages or reports in a new window while keeping the role explorer open. To explore an element, choose the **Open in a new window** icon to the left of the element's name. If the page or report has a teaching tip, the tip contains the **Open in a new window** icon.

## Related information

[Finding Pages and Information with Tell Me](ui-search.md)  
[Manage Profiles](admin-users-profiles-roles.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
