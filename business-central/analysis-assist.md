---
title: Analyze data in list pages and queries using data analysis mode
description: Learn how to use the data analysis mode in Business central to analyze data.
author: jswymer 
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to
ms.date: 12/08/2023
ms.custom: bap-template
ms.service: dynamics-365-business-central
ms.search.form: 456, 457, 458, 459, 460, 461, 16, 22, 25, 26, 27, 31, 143, 144, 9300, 9301, 9303, 9304, 9305, 9306, 9307, 9309, 9310, 9311
---
# Analyze data in the analysis mode with Copilot

[!INCLUDE[production-ready-preview-dynamics365](includes/production-ready-preview-dynamics365.md)]

This article explains how to use analysis assist to help you analyze data on list pages.

## About analysis assist

Analysis assist is a Copilot for the data analysis mode on list pages in Business Central. The analysis mode provides an interactive and versatile way to calculate, summarize, and examine data. To analyze data in the anaysis mode, you create a  *analysis* tab where you transform the data to display the desired aggregations and summarizations by arranging fields in rows and columns, specifying filters, sorting, and pivoting. Instead of doing this task manually, analysis assist lets you do it using words. By expressing the structure you want in natural language, like  "sort on quantity from smallest to largest" or "show average cost per category", analysis assist uses AI to generate suggested layout on an analysis tab.
<!-- 

 However, the data analysis mode requires some understanding of how to structure fields to meet the desired aggregations and summarizations. It requires you to move fields around to the appropriate areas within analysis mode pane which data rows and columns to display, specify filters, sorting, grouping, pivoting and totals. Analysis assist minimizes these requirments by enabling you to express the desired layout in words. , like "group which data rows and columns to display, specify filters, sorting, grouping, pivoting and totals
--> 
## Prerequisites

- Analysis assist capability is activated. This task is typically done by an admin. [Learn more about configuring Copilot and AI capabilities](enable-ai.md).
- Your user account is assigned the **DATA ANALYSIS - EXEC** permission set or includes execute permission on the system object **9640 Allow Data Analysis mode**. This task is typically done by an admin. Admins can exclude these permissions on users who you don't want to have access to the analysis mode and analysis assist.

<!--
> [!NOTE]
> You may notice some list pages that don't include the **Analyze** switch for changing to the analysis mode. The reason is that developers can disable analysis mode on specific pages by using the [AnalysisModeEnabled property](/dynamics365/business-central/dev-itpro/developer/properties/devenv-analysismodeenabled-property) in AL.-->

## Get started 

1. Open the list page you want to analyze.

   For example, to work with **Items** page, select the ![Magnifying glass that opens the Tell Me feature.](media/ui-search/search_small.png) icon (<kbd>Alt</kbd>+<kbd>Q</kbd>), enter *items*, and then choose the related link. 

1. You can start analyzing data with Copilot directly from the list page or by first entering the analysis mode. To get started, do one of the following steps:

    - In the action bar at the top of the page, select ![Shows the copilot icon](media/copilot-icon.png) **Copilot** > **Analyze list**. 
    - In the action bar at the top of the page, select ![Shows the enter analysis mode icon](media/analysis-mode-icon.png) **Enter analysis mode**, then select ![Shows the copilot icon](media/copilot-icon.png) **Copilot** > **Create new analysis**

1. In the **Analyze** with Copilot window, enter a description of the layout you want (known as a *prompt*).

    ![Shows the analysis assist Coplit ](media/alalysis-assist.png)

    > [!TIP]
    > For help in writing a prompt, select ![Shows the view prompt icon](media/prompt-guide-icon.png) **Prompt guide**, and choose one of the options to get you started. The text in brackets `[ ]` is shown only as an example and isn't included in the Coplit window.

1. Select **Generate** and then wait while Coplit generates the layout on new analysis tab.
1. 

## See also

[Responsible AI FAQ for analysis assist](faqs-analysis-assist.md)  
[Ad-hoc Data Analysis](reports-adhoc-analysis.md)  
