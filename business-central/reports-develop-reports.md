---
title: Develop Business Central Report Layouts and Datasets
description: Find guidance for customizing Business Central report layouts in Word, Excel, or RDLC, and learn when a developer must change the report dataset.
author: kennieNP
ms.topic: overview
ms.devlang: al
ms.reviewer: bholtorf
ms.search.keywords: feature overview
ms.date: 11/11/2026
ms.author: kepontop
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Develop Business Central report layouts and datasets

Reports in [!INCLUDE[prod_short](includes/prod_short.md)] have a report object that defines their dataset and layouts. The dataset provides the data in the report, and the layouts control how the data is presented.  

## Develop custom report layouts

Want to modify the layout of a report? For Excel and Word layouts, you can do that yourself. If you want pixel-perfect RDLC layouts though, you might need help from a developer. 

The following table provides links to articles that describe options for customizing reports.

| To | See |
|--|--|
| Learn about the different types of report layouts (Word, Excel, and RDLC) | [Layout types (Word, Excel, and RDLC)](ui-manage-report-layouts.md) |
| Learn how to create a new report layout. | [Create a new Layout](ui-get-started-layouts.md?tabs=copy#create) |
| Learn which fonts in [!INCLUDE[prod_short](includes/prod_short.md)] online you can use in report layouts. | [Using fonts in Layouts](ui-fonts.md) |
| Learn how to work with Word layouts. | [Work with Word Layouts](ui-how-add-fields-word-report-layout.md) |
| Learn how to import and export layout files. | [Export and import report layouts](ui-get-started-layouts.md#export-a-layout-copy-and-import-it-as-a-new-layout) |
| Learn how to update a layout definition in [!INCLUDE[prod_short](includes/prod_short.md)] with a new layout file. | [Replace a report layout](ui-get-started-layouts.md#replace-a-layout) |
| Learn how to change the default layout for a report. | [Set the layout used by a report](ui-set-report-layout.md) |
<!-- | To learn how to work with Excel layouts | [Work with Excel Layouts](ui-how-add-fields-word-report-layout.md) | -->

## Develop report datasets

Datasets define the data that's available in a report. To change the dataset for a report, you need a developer that knows about the AL programming language and the tools to develop report objects and report extensions.

| To | Go to |
|--|--|
| Learn how to program reports in AL. | [Report Development Guide](/dynamics365/business-central/dev-itpro/developer/devenv-reports) |
| Learn how to make reports perform. | [Report Performance Tuning Guide](/dynamics365/business-central/dev-itpro/performance/performance-developer#writing-efficient-reports) |

## Related information

[Analytics, business intelligence, and reporting overview](reports-bi-reporting.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]