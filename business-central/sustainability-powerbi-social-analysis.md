---

title: Social Analysis for ESG Reporting Power BI Report
description: Review employee absences, qualifications, and workforce distributions in Business Central with the Social Analysis Power BI report for ESG reporting.
author: altotovi
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ai-usage: ai-assisted
ms.search.keywords: reporting
ms.date: 11/12/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Social analysis (Power BI report)

[!INCLUDE[applies-to-2025w2](includes/2025_releasewave1.md)]

The Social Analysis report expands the report pack beyond the environmental aspects of ESG to include employee information. The report highlights key metrics for employee absences, gender distributions, activities, qualifications, and union memberships.

:::image type="content" source="media\sustainability\social analysis.png" alt-text="Screenshot of the Social Analysis Power BI report" lightbox="media\sustainability\social analysis.png":::

## Use the report

The executive team can use the report to review employee inactivity and grounds for termination, along with workforce distributions by age, gender, and union affiliation. The report doesn't calculate an employee turnover rate.

HR Managers can analyze employee qualifications, unions, gender distributions, and employee ledger amounts. Employee ledger amounts aren't a measure of salary or payroll.

Employee counts and statuses reflect the imported employee records, not a historical headcount for each reporting period. The Date table filters employee ledger amounts, but it doesn't filter employee absence records.

## Key performance indicators (KPIs)

The Social Analysis report includes the following KPIs and measures:

- [Male Employee (%)](sustainability-powerbi-kpis.md#male-employees-)
- [Female Employee (%)](sustainability-powerbi-kpis.md#female-employees-)
- [Other Employee (%)](sustainability-powerbi-kpis.md#other-employees-)
- [Absence Hours (%)](sustainability-powerbi-kpis.md#employee-absences-)
- [Employee Amount](sustainability-powerbi-kpis.md#employee-amount)
- [No. of Employees](sustainability-powerbi-kpis.md#no-of-employees)
- [Employee Qualifications](sustainability-powerbi-kpis.md#employee-qualifications)

Choose the link for a KPI to learn more about what it means, how it's calculated, and what data is used in the calculations.

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The Social Analysis report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Employee
- Employee Ledger Entries
- Employee Qualifications
- Employee Absence

## Try the report

Try the report here: [Social Analysis](https://businesscentral.dynamics.com?page=6278)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sustainability Overview (Power BI Report)](sustainability-powerbi-sustainability-overview.md)  
[Sustainability management overview](finance-manage-sustainability.md)  
[Sustainability reports and analytics in Business Central](sustainability-reports.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
