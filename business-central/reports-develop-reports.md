---
title: Developing Report Layouts and Datasets
description: Provides a overview of Business Central data.
author: kennieNP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.reviewer: bholtorf
ms.search.keywords: feature overview
ms.date: 02/03/2022
ms.author: kepontop
---

# Developing Business Central Report Layouts and Datasets

A report in [!INCLUDE[prod_short](includes/prod_short.md)] consists of a report object that defines the _dataset_ of the report (what data is available) and a number of _report layouts_ (how data is presented).  

## Developing report layouts

Maybe you want to modify existing report layouts provided in [!INCLUDE[prod_short](includes/prod_short.md)]? Depending on the technology used for the layout, this is something you might be able to do yourself (Excel and maybe also Word layouts), or maybe you need a developer to do it (pixel-perfect RDLC layouts).

| To | See |
|--|--|
| Learn more about the different layout types (Word, Excel, and RDLC) | [Layout types (Word, Excel, and RDLC)](ui-manage-report-layouts.md) |
| Learn about how you can create a new report layout. | [Create a new Layout](ui-how-create-custom-report-layout.md) |
| Learn about which fonts are installed in [!INCLUDE[prod_short](includes/prod_short.md)] online so that they can be used in report layouts. | [Using fonts in Layouts](ui-fonts.md) |
| To learn how to work with Word layouts. | [Work with Word Layouts](ui-how-add-fields-word-report-layout.md) |
| To learn how to import/export layout files. | [Import/Export a Layout](ui-how-import-and-export-report-layout.md) |
| To learn how to update a layout definition in [!INCLUDE[prod_short](includes/prod_short.md)] with a new layout file. | [Import/Export a Layout](ui-how-import-and-export-report-layout.md) |
| To learn how to change the default layout for a report. | [Change the default Layout](ui-how-change-layout-currently-used-report.md) |
<!-- | To learn how to work with Excel layouts | [Work with Excel Layouts](ui-how-add-fields-word-report-layout.md) | -->

## Developing report datasets

 To change the dataset definitions that define what data is available in the report, you need a developer that knows about the AL programming language and the tools to develop report objects and report extensions.

| To | See |
|--|--|
| Learn how to program reports in AL | [Report Development Guide](/dynamics365/business-central/dev-itpro/developer/devenv-reports) |
| Learn how to make reports perform | [Report Performance Tuning Guide](/dynamics365/business-central/dev-itpro/performance/performance-developer#writing-efficient-reports) |

## See Also

[Business Intelligence and Reporting Overview](reports-use-reports.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]