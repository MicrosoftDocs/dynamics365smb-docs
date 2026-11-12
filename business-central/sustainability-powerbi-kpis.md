---
title: Sustainability KPIs and Measures (Power BI)
description: Explore sustainability KPIs and measures in the Business Central Power BI app semantic model, including emissions, workforce, water, and waste metrics.
author: altotovi
ms.author: altotovi
ms.reviewer: bholtorf
ms.topic: reference
ai-usage: ai-assisted
ms.search.keywords: reporting
ms.date: 11/12/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Power BI sustainability app KPIs and measures

[!INCLUDE[applies-to-2025w2](includes/2025_releasewave1.md)]

This article provides a list of the key performance indicators (KPIs) that are included in the semantic model for the Power BI Sustainability report. Explore the list of KPIs to learn more about how they can help you achieve your business goals.

Each KPI is described, including how they're calculated and what data the calculations use.

The measures use imported data from the latest semantic model refresh. If the date filters in **Power BI Reports Setup** limit the loaded data, include the goal and baseline periods needed for your comparisons.

Percentage measures that divide by zero or a blank value return a blank result.

## Emission fees table

**Emissions Fees Measures**

- [CH4 Carbon Equivalent](#ch4-carbon-equivalent)
- [CO2 Carbon Equivalent](#co2-carbon-equivalent)
- [N2O Carbon Equivalent](#n2o-carbon-equivalent)
- [CO2e Target](#co2e-target)

### CH4 carbon equivalent

**Formula**  

A sum of the **Carbon Equivalent Factor** where the **Emission Type** is **CH4**.

**Data Sources**

- Emissions Fees

### CO2 carbon equivalent

**Formula**  

A sum of the **Carbon Equivalent Factor** where the **Emission Type** is **CO2**.

**Data Sources**

- Emissions Fees

### N2O carbon equivalent

**Formula**  

A sum of the **Carbon Equivalent Factor** where the **Emission Type** is **N2O**.

**Data Sources**

- Emissions Fees

### CO2e target

**Formula**  

Converts the CO2, CH4, and N2O targets to CO2 equivalents and adds them together.

([CO2 Target](#co2-target) \* [CO2 Carbon Equivalent](#co2-carbon-equivalent)) + ([CH4 Target](#ch4-target) \* [CH4 Carbon Equivalent](#ch4-carbon-equivalent)) + ([N2O Target](#n2o-target) \* [N2O Carbon Equivalent](#n2o-carbon-equivalent))

**Data Sources**

- Emissions Fees
- Sustainability Goals

## Employee absences table

**Employee Absences Measures**

- [Employee Absences](#employee-absences)
- [Employee Absences (%)](#employee-absences-)

### Employee absences

**Formula**  

A sum of **Quantity (Base)** from **Employee Absence**.

**Data Sources**

- Employee Absence

### Employee absences (%)

**Formula**  

The semantic model names this measure **Absence Hours (%)**. It divides absence quantities for active employees by the number of active employees multiplied by the number of working days in the selected period.

Employee Absences for Active Employees / ([Active Employees](#active-employees) \* Working Days)

The numerator uses absence quantities in base units. The denominator counts employee working days, not working hours.

The Date table filters the working-day count but isn't related to Employee Absences. A report date filter doesn't restrict the absence records included in the numerator.

**Data Sources**

- Employees
- Employee Absence
- Working Days
- Date

## Employee ledger entries table

**Employee Ledger Entries Measures**

- [Employee Amount](#employee-amount)

### Employee amount

**Formula**  

Sum of the **Amount** field from **Employee Ledger Entries**.

**Data Sources**

- Employee Ledger Entries

## Employee qualifications table

**Employee Qualifications Measures**

- [Employee Qualifications](#employee-qualifications)

### Employee qualifications

**Formula**  

A count of employee qualification records in the current filter context. It isn't a distinct count of qualification codes.

**Data Sources**

- Employee Qualifications

## Employee table

**Employee Measures**

- [Active Employees](#active-employees)
- [Age](#age)
- [Age Distribution](#age-distribution)
- [Female Employees (%)](#female-employees-)
- [Male Employees (%)](#male-employees-)
- [No. of Employees](#no-of-employees)
- [No. of Female Employees](#no-of-female-employees)
- [No. of Male Employees](#no-of-male-employees)
- [No. of Other Employees](#no-of-other-employees)
- [Other Employees (%)](#other-employees-)

### Active employees

**Formula**  

A filter on the [No. of Employees](#no-of-employees) where the **Status** of the **Employee** is **Active**.

**Data Sources**

- Employee

### Age

**Formula**  

A calculated column that determines an employee's age from their date of birth and the date of the semantic model refresh.

**Data Sources**

- Employee

### Age distribution

**Formula**  

A calculated column to group employees into one of three different age distributions.

> [!NOTE]
> The age distribution is defined in the semantic model. The bundled calculation groups ages under 30 as **Under 30**, ages 30 through 49 as **30 - 50**, and ages over 50 as **Over 50**. The current calculation leaves age 50 ungrouped.

**Data Sources**

- Employee

### Female employees (%)

**Formula**  

The **No. of Female Employees** divided by the **No. of Employees**.

[No. of Female Employees](#no-of-female-employees) / [No. of Employees](#no-of-employees)

**Data Sources**

- Employee

### Male employees (%)

**Formula**  

The **No. of Male Employees** divided by the **No. of Employees**.

[No. of Male Employees](#no-of-male-employees) / [No. of Employees](#no-of-employees)

**Data Sources**

- Employee

### No. of employees

**Formula**  

A count of Employees.

**Data Sources**

- Employee

### No. of female employees

**Formula**  

A filter on the [No. of Employees](#no-of-employees) where the **Employee Gender** is **Female**.

**Data Sources**

- Employee

### No. of male employees

**Formula**  

A filter on the [No. of Employees](#no-of-employees) where the **Employee Gender** is **Male**.

**Data Sources**

- Employee

### No. of other employees

**Formula**  

A filter on the [No. of Employees](#no-of-employees) where the **Employee Gender** is not **Male** or **Female**.

**Data Sources**

- Employee

### Other employees (%)

**Formula**  

The **No. of Other Employees** divided by the **No. of Employees**.

[No. of Other Employees](#no-of-other-employees) / [No. of Employees](#no-of-employees)

**Data Sources**

- Employee

## Responsibility centre table

**Responsibility Centre Measures**

- [Facility Capacity](#facility-capacity)

### Facility capacity

**Formula**  

Multiplies the sum of the responsibility centers' **Water Capacity Quantity(Month)** values by the number of months from the earliest to the latest selected date, inclusive. A partial month counts as a month.

**Data Sources**

- Responsibility Centre
- Date

## Sustainability goals table

**Sustainability Goals Measures**

Current values for CO2, CH4, N2O, CO2e, water, and waste ignore filters on the Date table. For each selected scorecard, they use the earliest goal start date and latest goal end date, then add the scorecard totals. The water and waste realized percentages use the selected period's intensity measures instead of these current-value measures.

- [CO2 Current Value](#co2-current-value)
- [CO2 Target](#co2-target)
- [CO2 Realized (%)](#co2-realized-)
- [CH4 Current Value](#ch4-current-value)
- [CH4 Target](#ch4-target)
- [CH4 Realized (%)](#ch4-realized-)
- [N2O Current Value](#n2o-current-value)
- [N2O Target](#n2o-target)
- [N2O Realized (%)](#n2o-realized-)
- [Waste Current Value](#waste-current-value)
- [Waste Target](#waste-target)
- [Waste Realized (%)](#waste-realized-)
- [Water Current Value](#water-current-value)
- [Water Target](#water-target)
- [Water Realized (%)](#water-realized-)
- [CO2e Current Value](#co2e-current-value)
- [CO2e Realized (%)](#co2e-realized-)

### CO2 current value

**Formula**  

A sum of [CO2 Emissions](#co2-emissions) based on the start and end date from the selected scorecards.

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals

### CO2 target

**Formula**  

Sum of the **Target Value** for **CO2**.

**Data Sources**

- Sustainability Goals

### CO2 realized (%)

**Formula**  

The **CO2 Current Value** divided by the **CO2 Target**.

[CO2 Current Value](#co2-current-value) / [CO2 Target](#co2-target)

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals

### CH4 current value

**Formula**  

A sum of [CH4 Emissions](#ch4-emissions) based on the start and end date from the selected scorecards.

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals

### CH4 target

**Formula**  

Sum of **Target Value** for **CH4**.

**Data Sources**

- Sustainability Goals

### CH4 realized (%)

**Formula**  

The **CH4 Current Value** divided by the **CH4 Target**.

[CH4 Current Value](#ch4-current-value) / [CH4 Target](#ch4-target)

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals

### N2O current value

**Formula**  

A sum of [N2O Emissions](#n2o-emissions) based on the start and end date from the selected scorecards.

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals

### N2O target

**Formula**  

A sum of **Target Value** for **N2O** from the **Sustainability Goals**.

**Data Sources**

- Sustainability Goals

### N2O realized (%)

**Formula**  

The **N2O Current Value** divided by the **N2O Target**.

[N2O Current Value](#n2o-current-value) / [N2O Target](#n2o-target)

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals

### Waste current value

**Formula**  

A sum of [Waste Intensity](#waste-intensity) based on the start and end date from the selected scorecards.

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals

### Waste target

**Formula**  

A sum of **Target Value** for **Waste**.

**Data Sources**

- Sustainability Goals

### Waste realized (%)

**Formula**  

The **Waste Intensity** in the current filter context divided by the **Waste Target**.

[Waste Intensity](#waste-intensity) / [Waste Target](#waste-target)

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals

### Water current value

**Formula**  

A sum of [Water Intensity](#water-intensity) based on the start and end date from the selected scorecards.

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals

### Water target

**Formula**  

A sum of **Target Value** for **Water**.

**Data Sources**

- Sustainability Goals

### Water realized (%)

**Formula**  

The **Water Intensity** in the current filter context divided by the **Water Target**.

[Water Intensity](#water-intensity) / [Water Target](#water-target)

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals

### CO2e current value

**Formula**  

A sum of [CO2e Emissions](#co2e-emissions) based on the start and end date from the selected scorecards.

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals

### CO2e realized (%)

**Formula**  

The **CO2e Current Value** divided by the **CO2e Target**.

[CO2e Current Value](#co2e-current-value) / [CO2e Target](#co2e-target)

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals
- Emissions Fees

## Sustainability ledger entries table

**Sustainability Ledger Entries Measures**

Baseline measures ignore filters on the Date table and use the baseline dates from the selected sustainability goals. The CO2, CH4, N2O, and CO2e baselines calculate a total for each selected scorecard and add those totals. Water, waste, and discharged-water baselines use one period from the earliest selected baseline start date to the latest selected baseline end date.

The semantic model names the water and waste baseline measures **Water Baseline** and **Waste Baseline**. Their comparison measures are **Water vs Baseline (%)** and **Waste vs Baseline (%)**.

- [CO2 Emissions](#co2-emissions)
- [CO2 Emissions Balance](#co2-emissions-balance)
- [CO2 Emissions Balance at Date ](#co2-emissions-balance-at-date)
- [CO2 Baseline](#co2-baseline) 
- [CO2 vs Baseline (%)](#co2-vs-baseline-)

- [CH4 Emissions](#ch4-emissions)
- [CH4 Emissions Balance at Date ](#ch4-emissions-balance-at-date)
- [CH4 Emissions Balance](#ch4-emissions-balance)
- [CH4 Baseline](#ch4-baseline) 
- [CH4 vs Baseline (%)](#ch4-vs-baseline-)

- [N2O Emissions](#n2o-emissions)
- [N2O Emissions Balance](#n2o-emissions-balance)
- [N2O Emissions Balance at Date](#n2o-emissions-balance-at-date)
- [N2O Baseline](#n2o-baseline) 
- [N2O vs Baseline (%)](#n2o-vs-baseline-)

- [CO2e Emissions](#co2e-emissions)
- [CO2e Emissions (Excl Credits)](#co2e-emissions-excl-credits)
- [CO2e Emissions Balance](#co2e-emissions-balance)
- [CO2e Emissions Balance at Date](#co2e-emissions-balance-at-date)
- [CO2e Baseline](#co2e-baseline) 
- [CO2e vs Baseline (%)](#co2e-vs-baseline-)

- [Discharged Into Water](#discharged-into-water)
- [Discharged Into Water Balance](#discharged-into-water-balance)
- [Discharged Into Water Balance at Date](#discharged-into-water-balance-at-date)
- [Discharged Into Water DOD](#discharged-into-water-dod)
- [Discharged Into Water PD](#discharged-into-water-pd)
- [Discharged Into Water PY](#discharged-into-water-py)
- [Discharged Into Water YOY](#discharged-into-water-yoy)
- [Discharged Into Water Baseline](#discharged-into-water-baseline)
- [Discharged Into Water vs Baseline (%)](#discharged-into-water-vs-baseline-)

- [Water Intensity](#water-intensity)
- [Water Intensity Balance](#water-intensity-balance)
- [Water Intensity Balance at Date](#water-intensity-balance-at-date)
- [Water Intensity DOD](#water-intensity-dod)
- [Water Intensity PD](#water-intensity-pd)
- [Water Intensity PY](#water-intensity-py)
- [Water Intensity YOY](#water-intensity-yoy)
- [Water Intensity Baseline](#water-intensity-baseline)
- [Water Intensity vs Baseline (%)](#water-intensity-vs-baseline-)
- [Water Available](#water-available)

- [Waste Intensity](#waste-intensity)
- [Waste Intensity Balance](#waste-intensity-balance)
- [Waste Intensity Balance at Date](#waste-intensity-balance-at-date)
- [Waste Intensity DOD](#waste-intensity-dod)
- [Waste Intensity PD](#waste-intensity-pd)
- [Waste Intensity PY](#waste-intensity-py)
- [Waste Intensity YOY](#waste-intensity-yoy)
- [Waste Intensity Baseline](#waste-intensity-baseline)
- [Waste vs Baseline (%)](#waste-intensity-vs-baseline-)

- [Purchased Carbon Credits](#purchased-carbon-credits)

### CO2 emissions

**Formula**  

A sum of **CO2** from the **Sustainability Ledger Entry**.

**Data Sources**

- Sustainability Ledger Entry
- Sustainability Goals

### CO2 emissions balance

**Formula**  

Calculates the total [CO2 Emissions](#co2-emissions) across all dates and ignores filters on the Date table. By removing date-based filtering, this measure provides the full value from the start to the end of the dataset.

**Data Sources**

- Sustainability Ledger Entry

### CO2 emissions balance at date

**Formula**  

Calculates cumulative [CO2 Emissions](#co2-emissions) up to the latest date in the current selection. The calculation filters the Date column to dates up to and including that date.

**Data Sources**

- Sustainability Ledger Entry

### CO2 baseline

**Formula**  

A sum of [CO2 Emissions](#co2-emissions) based on the **Baseline Start** and **End Date** from the selected scorecards to determine a **Baseline** value.

**Data Sources**

- Sustainability Ledger Entry
- Sustainability Goals

### CO2 vs baseline (%)

**Formula**  

The **CO2 Current Value** divided by the **CO2 Baseline**.

[CO2 Current Value](#co2-current-value) / [CO2 Baseline](#co2-baseline)

**Data Sources**

- Sustainability Ledger Entry
- Sustainability Goals

### CH4 emissions

**Formula**  

A sum of **CH4** from the **Sustainability Ledger Entry**.

**Data Sources**

- Sustainability Ledger Entry

### CH4 emissions balance at date

**Formula**  

Calculates cumulative [CH4 Emissions](#ch4-emissions) up to the latest date in the current selection. The calculation filters the Date column to dates up to and including that date.

**Data Sources**

- Sustainability Ledger Entry

### CH4 emissions balance

**Formula**  

Calculates the total [CH4 Emissions](#ch4-emissions) across all dates, and ignore filters on the Date table. By removing date-based filtering, this measure provides the full value from the start to the end of the dataset.

**Data Sources**

- Sustainability Ledger Entry

### CH4 baseline

**Formula**  

A sum of [CH4 Emissions](#ch4-emissions) based on the **Baseline Start** and **End Date** from the selected scorecards to determine a **Baseline** value.

**Data Sources**

- Sustainability Ledger Entry
- Sustainability Goals

### CH4 vs baseline (%)

**Formula**  

The **CH4 Current Value** divided by the **CH4 Baseline**.

[CH4 Current Value](#ch4-current-value) / [CH4 Baseline](#ch4-baseline)

**Data Sources**

- Sustainability Ledger Entry
- Sustainability Goals

### N2O emissions

**Formula**  

A sum of **N2O** from the **Sustainability Ledger Entry**.

**Data Sources**

- Sustainability Ledger Entry

### N2O emissions balance at date

**Formula**  

Calculates cumulative [N2O Emissions](#n2o-emissions) up to the latest date in the current selection. The calculation filters the Date column to dates up to and including that date.

**Data Sources**

- Sustainability Ledger Entry

### N2O emissions balance

**Formula**  

Calculates the total [N2O Emissions](#n2o-emissions) across all dates, and ignore filters on the Date table. By removing date-based filtering, this measure provides the full value from the start to the end of the dataset.

**Data Sources**

- Sustainability Ledger Entry

### N2O baseline

**Formula**  

A sum of [N2O Emissions](#n2o-emissions) based on the **Baseline Start** and **End Date** from the selected scorecards to determine a **Baseline** value.

**Data Sources**

- Sustainability Ledger Entry
- Sustainability Goals

### N2O vs baseline (%)

**Formula**  

The **N2O Current Value** divided by the **N2O Baseline**

[N2O Current Value](#n2o-current-value) / [N2O Baseline](#n2o-baseline)

**Data Sources**

- Sustainability Ledger Entry
- Sustainability Goals

### CO2e emissions

**Formula**  

A sum of **CO2e** from the **Sustainability Ledger Entry**.

**Data Sources**

- Sustainability Ledger Entry

### CO2e emissions (excl credits)

**Formula**  

Uses the existing [CO2e Emissions](#co2e-emissions) and filters to where the document type isn't **GHG Credit**.

**Data Sources**

- Sustainability Ledger Entry

### CO2e emissions balance at date

**Formula**  

Calculates cumulative [CO2e Emissions](#co2e-emissions) up to the latest date in the current selection. The calculation filters the Date column to dates up to and including that date.

**Data Sources**

- Sustainability Ledger Entry

### CO2e emissions balance

**Formula**  

Calculates the total [CO2e Emissions](#co2e-emissions) across all dates, and ignores filters on the Date table. By removing date-based filtering, this measure provides the full value from the start to the end of the dataset.

**Data Sources**

- Sustainability Ledger Entry

### CO2e baseline

**Formula**  

A sum of [CO2e Emissions](#co2e-emissions) based on the **Baseline Start** and **End Date** from the selected scorecards to determine a **Baseline** value.

**Data Sources**

- Sustainability Ledger Entry
- Sustainability Goals

### CO2e vs baseline (%)

**Formula**  

The **CO2e Current Value** divided by the **CO2e Baseline**.

[CO2e Current Value](#co2e-current-value) / [CO2e Baseline](#co2e-baseline) 

**Data Sources**

- Sustainability Ledger Entry
- Sustainability Goals

### Discharged into water

**Formula**  

A sum of **Discharged Into Water** from the **Sustainability Ledger Entry**.

**Data Sources**

- Sustainability Ledger Entry

### Discharged into water balance

**Formula**  

Calculates the total [Discharged Into Water](#discharged-into-water) value across all dates, and ignores filters on the Date table. By removing date-based filtering, this measure provides the full value from the start to the end of the dataset.

**Data Sources**

- Sustainability Ledger Entry

### Discharged into water balance at date

**Formula**  

Calculates cumulative [Discharged Into Water](#discharged-into-water) up to the latest date in the current selection. The calculation filters the Date column to dates up to and including that date.

**Data Sources**

- Sustainability Ledger Entry

### Discharged into water DOD

**Formula**  

Calculates the percentage change from the prior day to the current period. A positive value indicates an increase.

([Discharged Into Water](#discharged-into-water) - [Discharged Into Water PD](#discharged-into-water-pd)) / [Discharged Into Water PD](#discharged-into-water-pd)

**Data Sources**

- Sustainability Ledger Entry

### Discharged into water PD

**Formula**  

Calculates the [Discharged Into Water](#discharged-into-water) for the prior day.

**Data Sources**

- Sustainability Ledger Entry

### Discharged into water PY

**Formula**  

Calculates the [Discharged Into Water](#discharged-into-water) for the prior year.

**Data Sources**

- Sustainability Ledger Entry

### Discharged into water YOY

**Formula**  

Calculates the percentage change from the prior year to the current period. A positive value indicates an increase.

([Discharged Into Water](#discharged-into-water) - [Discharged Into Water PY](#discharged-into-water-py)) / [Discharged Into Water PY](#discharged-into-water-py)

**Data Sources**

- Sustainability Ledger Entry

### Discharged into water baseline

**Formula**  

A sum of [Discharged Into Water](#discharged-into-water) based on the **Baseline Start** and **End Date** from the selected scorecards to determine a **Baseline** value.

**Data Sources**

- Sustainability Ledger Entry
- Sustainability Goals

### Discharged into water vs baseline (%)

**Formula**  

The **Discharged Into Water** divided by the **Discharged Into Water Baseline**.

[Discharged Into Water](#discharged-into-water) / [Discharged Into Water Baseline](#discharged-into-water-baseline)

**Data Sources**

- Sustainability Ledger Entry

### Water intensity

**Formula**  

Sum of **Water Intensity** from the **Sustainability Ledger Entry**.

**Data Sources**

- Sustainability Ledger Entry

### Water intensity balance at date

**Formula**  

Calculates cumulative [Water Intensity](#water-intensity) up to the latest date in the current selection. The calculation filters the Date column to dates up to and including that date.

**Data Sources**

- Sustainability Ledger Entry

### Water intensity balance

**Formula**  

Calculates the total [Water Intensity](#water-intensity) across all dates, and ignores filters on the Date table. By removing date-based filtering, this measure provides the full value from the start to the end of the dataset.

**Data Sources**

- Sustainability Ledger Entry

### Water intensity DOD

**Formula**  

Calculates the percentage change from the prior day to the current period. A positive value indicates an increase.

([Water Intensity](#water-intensity) - [Water Intensity PD](#water-intensity-pd)) / [Water Intensity PD](#water-intensity-pd)

**Data Sources**

- Sustainability Ledger Entry

### Water intensity PD

**Formula**  

Calculates the [Water Intensity](#water-intensity) for the prior day.

**Data Sources**

- Sustainability Ledger Entry

### Water intensity PY

**Formula**  

Calculates the [Water Intensity](#water-intensity) for the prior year.

**Data Sources**

- Sustainability Ledger Entry

### Water intensity YOY

**Formula**  

Calculates the percentage change from the prior year to the current period. A positive value indicates an increase.

([Water Intensity](#water-intensity) - [Water Intensity PY](#water-intensity-py)) / [Water Intensity PY](#water-intensity-py)

**Data Sources**

- Sustainability Ledger Entry

### Water intensity baseline

**Formula**  

A sum of [Water Intensity](#water-intensity) based on the **Baseline Start** and **End Date** from the selected scorecards to determine a **Baseline** value.

**Data Sources**

- Sustainability Ledger Entry
- Sustainability Goals

### Water intensity vs baseline (%)

**Formula**  

The **Water Intensity** divided by the **Baseline**.

[Water Intensity](#water-intensity) / [Baseline](#water-intensity-baseline)

**Data Sources**

- Sustainability Ledger Entry
- Sustainability Goals

### Water available

**Formula**  

Calculated as **Facility Capacity** minus **Water Intensity**.

[Facility Capacity](#facility-capacity) - [Water Intensity](#water-intensity)

**Data Sources**

- Sustainability Ledger Entry
- Responsibility Centre
- Date

### Waste intensity

**Formula**  

A sum of **Waste Intensity** from the **Sustainability Ledger Entry**.

**Data Sources**

- Sustainability Ledger Entry

### Waste intensity balance at date

**Formula**  

Calculates cumulative [Waste Intensity](#waste-intensity) up to the latest date in the current selection. The calculation filters the Date column to dates up to and including that date.

**Data Sources**

- Sustainability Ledger Entry

### Waste intensity balance

**Formula**  

Calculates the total [Waste Intensity](#waste-intensity) across all dates, and ignores filters on the Date table. By removing date-based filtering, this measure provides the full value from the start to the end of the dataset.

**Data Sources**

- Sustainability Ledger Entry

### Waste intensity DOD

**Formula**  

Calculates the percentage change from the prior day to the current period. A positive value indicates an increase.

([Waste Intensity](#waste-intensity) - [Waste Intensity PD](#waste-intensity-pd)) / [Waste Intensity PD](#waste-intensity-pd)

**Data Sources**

- Sustainability Ledger Entry

### Waste intensity PD

**Formula**  

Calculates the [Waste Intensity](#waste-intensity) for the prior day.

**Data Sources**

- Sustainability Ledger Entry

### Waste intensity PY

**Formula**  

Calculates the [Waste Intensity](#waste-intensity) for the prior year.

**Data Sources**

- Sustainability Ledger Entry

### Waste intensity YOY

**Formula**  

Calculates the percentage change from the prior year to the current period. A positive value indicates an increase.

([Waste Intensity](#waste-intensity) - [Waste Intensity PY](#waste-intensity-py)) / [Waste Intensity PY](#waste-intensity-py)

**Data Sources**

- Sustainability Ledger Entry

### Waste intensity baseline

**Formula**  

A sum of [Waste Intensity](#waste-intensity) based on the **Baseline Start** and **End Date** from the selected scorecards to determine a **Baseline** value.

**Data Sources**

- Sustainability Ledger Entry
- Sustainability Goals

### Waste intensity vs baseline (%)

**Formula**  

The **Waste Intensity** divided by the **Baseline**.

[Waste Intensity](#waste-intensity) / [Baseline](#waste-intensity-baseline) 

**Data Sources**

- Sustainability Ledger Entry
- Sustainability Goals

### Purchased carbon credits

**Formula**  

Uses the existing [CO2e Emissions](#co2e-emissions) and filters to where the document type is **GHG Credit**.

**Data Sources**

- Sustainability Ledger Entry

## Related information

[Sustainability Overview (Power BI Report)](sustainability-powerbi-sustainability-overview.md)  
[Sustainability management overview](finance-manage-sustainability.md)  
[Sustainability reports and analytics in Business Central](sustainability-reports.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
