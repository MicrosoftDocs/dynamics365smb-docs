---
title: Project Timeline Power BI Report
description: Review project task start dates, end dates, and durations derived from planning lines in Business Central with the Project Timeline Power BI report.
author: kennienp
ms.author: kepontop
ms.topic: concept-article
ai-usage: ai-assisted
ms.search.keywords: reporting
ms.search.form: 37106_Primary
ms.date: 11/12/2026
ms.service: dynamics-365-business-central

---

# Project timeline (Power BI report)

[!INCLUDE[applies-to-2025w1](includes/applies-to-2025w1.md)]

The **Project Timeline** report shows task dates and durations based on project planning lines. A task's starting date is its earliest planning date, and its ending date is its latest planning date. The report includes the project number, task number, and description.

:::image type="content" source="media/projects/project-timeline.png" alt-text="Screenshot of the Project Timeline Power BI Report" lightbox="media/projects/project-timeline.png":::

## Use the report

Project managers and team members use the report to effectively monitor and plan project timelines.

As a manager, you can use the report to monitor the duration of individual tasks within a project. Review the dates to identify potential scheduling issues and decide whether to adjust timelines or resource allocations. The report doesn't calculate a critical path or task dependencies.

For team members involved in project execution, the report serves as a tool for understanding their task timelines. By referring to this report, staff can prioritize their tasks, collaborate with other team members effectively, and meet project deadlines.

## Key performance indicators (KPIs)

The report includes the following calculated date columns and duration measures:

- [**Project Task Starting Date**](projects-powerbi-kpis.md#project-task-starting-date)
- [**Project Task Ending Date**](projects-powerbi-kpis.md#project-task-ending-date)
- [Project Task Duration Days](projects-powerbi-kpis.md#project-task-duration-days)
- [Project Task Duration Weeks](projects-powerbi-kpis.md#project-task-duration-weeks)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)] 

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Job
- Job Task
- Job Planning Line

## Try the report

Try the report here: [Project Timeline](https://businesscentral.dynamics.com?page=37106)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track your business KPIs with Power BI goals](track-kpis-with-power-bi-metrics.md)  
[Power BI Projects app](projects-powerbi-app.md)  
[Built-in Projects reports](project-reports.md)  
[Project management analytics overview](projects-analytics-overview.md)  
[Project management overview](projects-manage-projects.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
