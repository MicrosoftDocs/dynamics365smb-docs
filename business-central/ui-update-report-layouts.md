---
title: (Obsolete) Update Custom Report Layouts
description: Test and update legacy custom report layouts after dataset changes in Business Central, and find guidance for changes that require manual fixes.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.form: 9652, 9650
ms.date: 11/11/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---
# (Obsolete) Update custom report layouts

[!INCLUDE[legacy-custom-layouts](includes/legacy-custom-layouts.md)]

These procedures apply only to versions that still include the legacy pages. For the current workflow, learn more in [Manage report and document layouts](ui-manage-report-layouts.md).

Occasionally, you may need to update a custom report layout after the report's dataset changes. If a report layout requires updating, you'll get an error when you try to preview, print, or save the report.

You can automatically update a report layout from the error message that appears when you run the report by choosing the **Yes** button on the error message. Or, in advance of running reports, you can update specific report layouts or all custom report layouts that might be affected by dataset changes.  

You also have the option to test updates without applying the required changes to the custom report layouts. This enables you to see what changes will be applied to the report layout and identify possible issues in the process. From the test results, you can open the custom report layouts directly for editing to fix any issues. We recommend that you test the report layout update before you apply the updates.  

Not all report dataset changes can be automatically updated in the report layouts. Some changes require you to manually edit the report layout. Learn more in [Limitations of custom report layout updates](#UpdateLimitations).

## Update one or more custom report layouts

1.  [!INCLUDE[open-search](includes/open-search.md)], enter **Report Layout Selection**, and then choose the related link.  

1.  To update one layout, select its report, choose **Custom Layouts**, then select the layout on the **Custom Report Layouts** page and choose **Update Layout**. To update all custom layouts, choose **Update All layouts** on the **Report Layout Selection** page.

If no errors occur, the updates are applied to the report layouts. If errors occur, a message lists them. You must then manually edit the custom report layout to fix the errors. Learn more in [Fix layout update errors](#FixErrors).

## Test custom report layout updates

1.  [!INCLUDE[open-search](includes/open-search.md)], enter **Report Layout Selection**, and then choose the related link.  

1.  On the **Report Layout Selection** page, choose **Test Layout Updates**.

Changes to the report layouts are tested but not applied. The **Report Layout Update Log** page shows the status of potential updates for each report layout. If there are errors, you can open the report layout from the log to fix them. Learn more in [Fix layout update errors](#FixErrors).

<a name="UpdateLimitations"></a>

## Limitations of custom report layout updates

The automatic update can apply supported dataset changes to custom report layouts. However, it can't handle the following changes:

- Deleted fields, labels, or data items.
- Duplicate field names in the report layout after a field has been renamed in the dataset. Treat this condition as a design error.
- Upgrade scenarios where multiple iterations of a report layout cause multiple rename actions on the same fields, labels, or data items.

 If the update process detects any one of these issues, the update cannot be applied. You will have to fix the issues manually, for example by editing the report layout in Word, or programmatically by using upgrade codeunits.  

<a name="FixErrors"></a>

## Fix layout update errors
 If you get an error message when you update or test report layout updates, you most likely will have to modify the report layout to fix the problem. Read the error message to help determine the cause of the problem.  

 The most typical problem occurs when a field that is used on the layout has been removed from the report dataset. In this case, you will see a line in the error message that states that an item has been removed. To fix this issue, you will have to modify the layout and remove the field in question.  

Learn more in [Create and modify a custom report layout](ui-how-create-custom-report-layout.md#ModifyCustomLayout).

After you modify the layout, try to update the layout again.  

## Related information
 [Managing Report Layouts](ui-manage-report-layouts.md)  
 [Work with Reports, Batch Jobs, and XMLports](ui-work-report.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
