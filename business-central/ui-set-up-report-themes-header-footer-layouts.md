---
title: Set Up Report Themes and Header/Footer Layouts
description: Learn how to manage reusable report themes and header/footer layouts, approve them, and assign defaults across reports and companies in Business Central.
author: SusanneWindfeldPedersen
ms.author: solsen
ms.reviewer: jswymer
ms.topic: how-to
ms.search.keywords: report theme, header footer, composite layout, report branding, document layout
ms.search.form: 9660, 9663, 9666, 9670
ms.date: 09/09/2026
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Set up reusable themes and header and footer layouts

Use reusable themes and header and footer layouts to apply consistent branding to reports that use Word layouts. You can define a default for all reports and companies, then override it for a company, a report, or an individual body layout.

The theme, header and footer, and report-specific body are combined when the report runs. This combination is called a *composite layout*. When you update a reusable part, the change applies to the body layouts that use it.

> [!NOTE]
> This experience is available when the **Document Report Experience** feature is enabled on the **Feature Management** page. Learn more in [Enabling new and upcoming features ahead of time](admin-feature-management.md).

## Understand the parts of a composite layout

A composite Word layout can contain the following parts:

| Part | Purpose |
|---|---|
| Body | Contains the report-specific data, tables, totals, and other content. Only a Word layout with the **Body** subtype can use reusable parts. |
| Theme | Defines reusable design settings, such as fonts and colors. A theme file has the .dotx extension. |
| Header and footer | Defines reusable content for page headers and footers. A header and footer file has the .docx extension. |

Themes and header and footer layouts can come from an installed extension or be uploaded by an administrator. You can export extension-provided parts to inspect them, but you can't edit, replace, or delete them. You can manage all these actions for user-defined parts.

## Understand how reusable parts are selected

The theme and header/footer resolve independently. For example, a body layout can use a layout-specific header/footer and inherit its theme from the company default.

An extension can include a theme or header/footer together with a report layout. If you store a part with the selected layout, the system uses that part first, before any administrator assignment. For each part that is still unspecified, the system checks administrator assignments in the following order, from most specific to least specific:

| Order | Scope | Source |
|---|---|---|
| 1 | The body layout in the current company | **This layout** |
| 2 | The body layout in all companies | **This layout** |
| 3 | All body layouts for the report in the current company | **Report default** |
| 4 | All body layouts for the report in all companies | **Report default** |
| 5 | All reports in the current company | **Company** |
| 6 | All reports in all companies | **Global default** |

At each level, an empty theme or header/footer value passes that part to the next level. If no administrator assignment applies, [!INCLUDE [prod_short](includes/prod_short.md)] checks the parts declared for the body layout, and then uses the defaults declared for the report.

> [!NOTE]
> The **Details** FactBox and the **Theme and header-footer per layout** page show the result of administrator assignments. They don't include fallback parts declared in an extension. As a result, these pages can show **None** even though an extension-defined part is used when the report runs.

## Add a theme or header/footer layout

New user-defined parts start with the **Draft** status. Approve a part before you assign it.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Manage themes and header-footer layouts**, and then select the related link.
1. Select **New theme** or **New header/footer**.
1. Enter a name and an optional description, and then select **OK**.
1. Select the .dotx theme file or .docx header/footer file to upload.
1. Select the new part, and then select **Part Status** > **Set Approved**.

The approved part is now available when you set a default or an override.

## Manage the status of a reusable part

Use status to control whether a user-defined part is available to assign as a default or an override.

| Status | Use |
|---|---|
| **Draft** | The part is being prepared and can't be selected for a new assignment. |
| **Pending Approval** | The part is ready for review and can't be selected for a new assignment. |
| **Approved** | The part can be selected for a new assignment. |
| **Retired** | The part is no longer offered for a new assignment. |

1. Open the **Manage themes and header-footer layouts** page.
1. Select one or more user-defined parts.
1. Select **Part Status**, and then select **Set Draft**, **Set Pending Approval**, **Set Approved**, or **Set Retired**.

Changing an assigned part from **Approved** to another status doesn't remove the existing assignment. The part continues to apply when the report runs. Change or clear the assignment; that is, empty the part field, if you no longer want the report to use the part. Learn more about clearing an assignment in [Clear an assignment](#clear-an-assignment).

## Set the global default

Set a global default to provide the theme or header and footer that applies when no more specific assignment exists.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Report defaults for theme and header-footer**, and then select the related link.
1. Select **Add global default**.
1. In the **Header/Footer Part** field, select the assist-edit button, and then select an approved header and footer layout.
1. In the **Theme Part** field, select the assist-edit button, and then select an approved theme.

The **Applies to** field shows **All reports** for the global default row. Leave either part empty if you don't want to define it at the global level.

## Set the default for a company

A company default overrides the global default for reports that run in that company. You can set one part and continue to inherit the other part from the global default.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Company Information**, and then select the related link.
1. Expand the **Reporting** FastTab.
1. In the **Default Theme** field, select the assist-edit button, and then select an approved theme.
1. In the **Default Header/Footer** field, select the assist-edit button, and then select an approved header and footer layout.

Clear a field to remove that company default. The affected body layouts then inherit the part from the next applicable level.

## Set the default for a report

A report default applies to all body layouts for one report unless a layout-specific assignment exists.

1. Open the **Report defaults for theme and header-footer** page.
1. Select **Set for one report**.
1. Select a body layout for the report, and then select **OK**.
1. In the new row, set the **Header/Footer Part** and **Theme Part** fields.
1. To limit the default to one company, set the **Company Name** field. Leave the field empty to apply the default in all companies.

The **Applies to** field identifies the report and indicates that the row applies to all its layouts.

## Set the parts for one body layout

A layout-specific assignment overrides broader defaults for that body layout.

1. [!INCLUDE [open-report-layouts-page](includes/open-report-layouts-page.md)]
1. Select a Word layout whose **Subtype** is **Body**.
1. Select **Composite layout** > **Set report theme and header-footer**.
1. Select an approved **Header/Footer Part**, **Theme Part**, or both.
1. Select **OK**.

If a company-specific assignment already exists for the layout, a warning explains that the more specific company setting continues to apply.

You can also create a layout-specific row - an assignment that applies to a single body layout - from the **Report defaults for theme and header-footer** page. Select **Set for one layout**, choose the body layout, and optionally enter a **Company Name**.

## Review the effective theme and header/footer

Use the **Details** FactBox on the **Report Layouts** page to see the theme and header/footer that result from administrator assignments for the selected body layout. The source fields show whether each assigned part comes from **This layout**, **Report default**, **Company**, or **Global default**. The FactBox doesn't show fallback parts declared in an extension.

To compare all body layouts for one report:

1. Open the **Report Layouts** page.
1. Select a Word layout for the report.
1. Select **Composite layout** > **Set all report theme and header-footer**.
1. Review the **Theme**, **Theme source**, **Header/Footer**, and **Header/Footer source** columns.
1. To change one body layout, select it, and then select **Set theme and header-footer**.

## Clear an assignment

Clear an assignment when you want a body layout to inherit a reusable part from a broader scope.

1. On the **Report Layouts** page, select the body layout.
1. Select **Composite layout** > **Set report theme and header-footer**.
1. Clear the **Header/Footer Part**, **Theme Part**, or both.
1. Select **OK**.

The theme and header/footer resolve independently. Clearing both fields removes the layout-specific configuration row.

To clear a company default, clear the corresponding field on the **Company Information** page. To clear a global or report default, delete its row on the **Report defaults for theme and header-footer** page. If you want to keep only one part, recreate the row and set that part.

## Replace or delete a user-defined part

You can replace the file for a user-defined part without recreating its assignments.

1. Open the **Manage themes and header-footer layouts** page.
1. Select the user-defined part.
1. Select **Replace**, and then confirm the action.
1. Select the replacement file.

To delete a user-defined part, select it, and then select **Delete**. A message shows how many report configurations use the part and asks you to confirm the deletion. Deleting the part clears those direct assignments. Affected layouts can then inherit a broader default if one exists.

## Related information

[Report and document layouts overview](ui-manage-report-layouts.md)  
[Get started creating report layouts](ui-get-started-layouts.md)  
[Design Word layouts with the Business Central add-in](ui-design-word-layouts-business-central-add-in.md)  
[Set the layout used by a report](ui-set-report-layout.md)  
[Map data fields with the XML Mapping Pane](ui-how-add-fields-word-report-layout.md)  
[Enabling new and upcoming features ahead of time](admin-feature-management.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
