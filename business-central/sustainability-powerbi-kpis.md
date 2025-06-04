---
title: Sustainability KPIs and measures (Power BI)
description: Get an overview of all the KPIs and measures in the semantic model for the Sustainability Power BI app.
author: altotovi
ms.author: altotovi
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: 
ms.date: 05/26/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Power BI Sustainability app KPIs and measures

[!INCLUDE[applies-to-2025w2](includes/2025_releasewave1.md)]

This article provides a list of the key performance indicators (KPIs) that are included in the semantic model for the Power BI Sustainability report. Explore the list of KPIs to learn more about how they can help you achieve your business goals.

Each KPI is described, including how they're calculated and what data the calculations use.

## Emission Fees Table

**Emissions Fees Measures**

- [CH4 Carbon Equivalent](#ch4-carbon-equivalent)
- [CO2 Carbon Equivalent](#co2-carbon-equivalent)
- [N2O Carbon Equivalent](#n2o-carbon-equivalent)
- [CO2e Target](#co2e-target)

### CH4 Carbon Equivalent

**Formula**  

A sum of the **Carbon Equivalent Factor** where the **Emission Type** is **CH4**.

**Data Sources**

- Emissions Fees

### CO2 Carbon Equivalent

**Formula**  

A sum of the **Carbon Equivalent Factor** where the **Emission Type** is **CO2**.

**Data Sources**

- Emissions Fees

### N2O Carbon Equivalent

**Formula**  

A sum of the **Carbon Equivalent Factor** where the **Emission Type** is **N2O**.

**Data Sources**

- Emissions Fees

### CO2e Target

**Formula**  

A calculation of all carbon equivalent factors and their targets shown as one figure.

**Data Sources**

- Emissions Fees
- Sustainability Goals

## Employee Absences Table

**Employee Absences Measures**

- [Employee Absences](#employee-absences)
- [Employee Absences (%)](#employee-absences-)

### Employee Absences

**Formula**  

A sum of **Employee Absences Quantity**.

**Data Sources**

- Employee Absence

### Employee Absences (%)

**Formula**  

A calculation of the [Employee Absences](#employee-absences) multiplied by [Active Employees](#active-employees) and divided by **Working Days** to calculate the percentage of **Absence Hours**.

**Data Sources**

- Employees
- Employee Absence

## Employee Ledger Entries Table

**Employee Ledger Entries Measures**

- [Employee Amount](#employee-amount)

### Employee Amount

**Formula**  

Sum of the **Amount** field from **Employee Ledger Entries**.

**Data Sources**

- Employee Ledger Entries

## Employee Qualifications Table

**Employee Qualifications Measures**

- [Employee Qualifications](#employee-qualifications)

### Employee Qualifications

**Formula**  

A count of the different qualifications per employee.

**Data Sources**

- Employee Qualifications

## Employee Table

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

### Active Employees

**Formula**  

A filter on the [No. of Employees](#no-of-employees) where the **Status** of the **Employee** is **Active**.

**Data Sources**

- Employee

### Age

**Formula**  

A calculated column for the **Employee** to determine the age of the employee based on their date of birth.

**Data Sources**

- Employee

### Age Distribution

**Formula**  

A calculated column to group employees into one of three different age distributions.

[!NOTE]
> The age distribution is defined directly in Power BI. The grouping is under 30, between 30 and 50, and then over 50. You can't change the distributions.

**Data Sources**

- Employee

### Female Employees (%)

**Formula**  

The **No. of Female Employees** divided by the **No. of Employees**.

[No. of Female Employees](#no-of-female-employees) / [No. of Employees](#no-of-employees)

**Data Sources**

- Employee

### Male Employees (%)

**Formula**  

The **No. of Male Employees** divided by the **No. of Employees**.

[No. of Male Employees](#no-of-male-employees) / [No. of Employees](#no-of-employees)

**Data Sources**

- Employee

### No. of Employees

**Formula**  

A count of Employees.

**Data Sources**

- Employee

### No. of Female Employees

**Formula**  

A filter on the [No. of Employees](#no-of-employees) where the **Employee Gender** is **Female**.

**Data Sources**

- Employee

### No. of Male Employees

**Formula**  

A filter on the [No. of Employees](#no-of-employees) where the **Employee Gender** is **Male**.

**Data Sources**

- Employee

### No. of Other Employees

**Formula**  

A filter on the [No. of Employees](#no-of-employees) where the **Employee Gender** is not **Male** or **Female**.

**Data Sources**

- Employee

### Other Employees (%)

**Formula**  

The **No. of Other Employees** divided by the **No. of Employees**.

[No. of Other Employees](#no-of-other-employees) / [No. of Employees](#no-of-employees)

**Data Sources**

- Employee

## Responsibility Centre Table

**Responsibility Centre Measures**

- [Facility Capactity](#facility-capactity)

### Facility Capactity

**Formula**  

Measures the water capacity of the facility (Responsibility Centre). The measure is based on the **Month in Period** when filtering.

**Data Sources**

- Responsibility Centre

## Sustainability Goals Table

**Sustainability Goals Measures**

- [CO2 Current Value](#co2-current-value)
- [CO2 Target](#co2-target)
- [CO2 Realized (%)](#co2-target)
- [CH4 Current Value](#ch4-target)
- [CH4 Target](#ch4-target)
- [CH4 Realized (%)](#ch4-target)
- [N2O Current Value](#n2o-current-value)
- [N2O Target](#n2o-target)
- [N2O Realized (%)](#n2o-target)
- [Waste Current Value](#waste-target)
- [Waste Target](#waste-target)
- [Waste Realized (%)](#waste-target)
- [Water Current Value](#water-target)
- [Water Target](#water-target)
- [Water Realized (%)](#water-target)
- [CO2e Current Value](#co2e-current-value)
- [CO2e Realized (%)](#co2e-realized-)

### CO2 Current Value

**Formula**  

A sum of [CO2 Emissions](#co2-emissions) based on the start and dnd date from the selected scorecards.

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals

### CO2 Target

**Formula**  

Sum of the **Target Value** for **CO2**.

**Data Sources**

- Sustainability Goals

### CO2 Realized (%)

**Formula**  

The **CH4 Current Value** divided by the **CH4 Emissions**.

[CO2 Current Value](#co2-current-value) / [CO2 Target](#co2-target)

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals

### CH4 Current Value

**Formula**  

A sum of [CH4 Emissions](#ch4-emissions) based on the start and end date from the selected scorecards.

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals

### CH4 Target

**Formula**  

Sum of **Target Value** for **CH4**.

**Data Sources**

- Sustainability Goals

### CH4 Realized (%)

**Formula**  

The **CH4 Current Value** divided by the **CH4 Emissions**.

[CH4 Current Value](#ch4-current-value) / [CH4 Target](#ch4-target)

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals

### N2O Current Value

**Formula**  

A sum of [N2O Emissions](#n2o-emissions) based on the start and end date from the selected scorecards.

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals

### N2O Target

**Formula**  

A sum of **Target Value** for **N2O** from the **Sustainability Goals**.

**Data Sources**

- Sustainability Goals

### N2O Realized (%)

**Formula**  

The **N2O Current Value** divided by the **N2O Emissions**.

[N2O Current Value](#n2o-current-value) / [N2O Target](#n2o-target)

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals

### Waste Current Value

**Formula**  

A sum of [Waste Intensity](#waste-intensity) based on the start and end date from the selected scorecards.

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals

### Waste Target

**Formula**  

A sum of **Target Value** for **Waste**.

**Data Sources**

- Sustainability Goals

### Waste Realized (%)

**Formula**  

The **Waste Current Value** divided by the **Waste Emissions**.

[Waste Current Value](#waste-current-value) / [Waste Target](#waste-target)

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals

### Water Current Value

**Formula**  

A sum of [Water Intensity](#water-intensity) based on the start and end date from the selected scorecards.

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals

### Water Target

**Formula**  

A sum of **Target Value** for **Water**.

**Data Sources**

- Sustainability Goals

### Water Realized (%)

**Formula**  

The **Water Current Value** divided by the **Water Emissions**.

[Water Current Value](#water-current-value) / [Water Target](#water-target)

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals

### CO2e Current Value

**Formula**  

A sum of [CO2e Emissions](#co2e-emissions) based on the start and end date from the selected scorecards.

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals

### CO2e Realized (%)

**Formula**  

The **CO2e Current Value** divided by the **CO2e Emissions**.

[CO2e Current Value](#co2e-current-value) / [CO2e Target](#co2e-target)

**Data Sources**

- Sustainability Ledger Entries
- Sustainability Goals

## Sustainability Ledger Entries Table

**Sustainability Ledger Entries Measures**

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
- [CO2e Baseline](#co2-baseline) 
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
- [Water Intensity Baseline](#water-intensity-balance)
- [Water Intensity Baseline at Date](#water-intensity-balance-at-date)
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

### CO2 Emissions

**Formula**  

A sum of **CO2** from the **Sustainability Ledger Entry**.

**Data Sources**

- Sustainability Ledger Entry

### CO2 Emissions Balance

**Formula**  

Calculates the total [CO2 Emissions](#co2-emissions) across all dates and ignores filters on the Date table. By removing date-based filtering, this measure provides the full value from the start to the end of the dataset.

**Data Sources**

- Sustainability Ledger Entry

### CO2 Emissions Balance at Date 

**Formula**  

Calculates the cumulative [CO2 Emissions](#co2-emissions) up to the latest date in the current filter. It removes all date filters, then re-applies a filter to include only dates up to and including the latest date in the selection, which gives a running balance up to the specified date.

**Data Sources**

- Sustainability Ledger Entry

### CO2 Baseline

**Formula**  

A sum of [CO2 Emissions](#co2-emissions) based on the **Baseline Start** and **End Date** from the selected scorecards to determine a **Baseline** value.

**Data Sources**

- Sustainability Ledger Entry
- Sustainability Goals

### CO2 vs Baseline (%)

**Formula**  

The **CO2 Current Value** divided by the **CO2 Baseline**.

[CO2 Current Value](#co2-current-value) / [CO2 Baseline](#co2-baseline)

**Data Sources**

- Sustainability Ledger Entry
- Sustainability Goals

### CH4 Emissions

**Formula**  

A sum of **CH4** from the **Sustainability Ledger Entry**.

**Data Sources**

- Sustainability Ledger Entry

### CH4 Emissions Balance at Date

**Formula**  

Calculates the cumulative [CH4 Emissions](#ch4-emissions) up to the latest date in the current filter. It removes all date filters, then re-applies a filter to include only dates up to and including the latest date in the selection, which gives a running balance up to the specified date.

**Data Sources**

- Sustainability Ledger Entry

### CH4 Emissions Balance 

**Formula**  

Calculates the total [CH4 Emissions](#ch4-emissions) across all dates, and ignore filters on the Date table. By removing date-based filtering, this measure provides the full value from the start to the end of the dataset.

**Data Sources**

- Sustainability Ledger Entry

### CH4 Baseline

**Formula**  

A sum of [CH4 Emissions](#ch4-emissions) based on the **Baseline Start** and **End Date** from the selected scorecards to determine a **Baseline** value.

**Data Sources**

- Sustainability Ledger Entry
- Sustainability Goals

### CH4 vs Baseline (%)

**Formula**  

The **CH4 Current Value** divided by the **CH4 Baseline**.

[CH4 Current Value](#ch4-current-value) / [CH4 Baseline](#ch4-baseline)

**Data Sources**

- Sustainability Ledger Entry
- Sustainability Goals

### N2O Emissions

**Formula**  

A sum of **N2O** from the **Sustainability Ledger Entry**.

**Data Sources**

- Sustainability Ledger Entry

### N2O Emissions Balance at Date

**Formula**  

Calculates the cumulative [N2O Emissions](#n2o-emissions) up to the latest date in the current filter. It removes all date filters, then re-applies a filter to include only dates up to and including the latest date in the selection, which gives a running balance up to the specified date.

**Data Sources**

- Sustainability Ledger Entry

### N2O Emissions Balance

**Formula**  

Calculates the total [N2O Emissions](#n2o-emissions) across all dates, and ignore filters on the Date table. By removing date-based filtering, this measure provides the full value from the start to the end of the dataset.

**Data Sources**

- Sustainability Ledger Entry

### N2O Baseline

**Formula**  

A sum of [N2O Emissions](#n2o-emissions) based on the **Baseline Start** and **End Date** from the selected scorecards to determine a **Baseline** value.

**Data Sources**

- Sustainability Ledger Entry
- Sustainability Goals

### N2O vs Baseline (%)

**Formula**  

The **N2O Current Value** divided by the **N2O Baseline**

[N2O Current Value](#n2o-current-value) / [N2O Baseline](#n2o-baseline)

**Data Sources**

- Sustainability Ledger Entry
- Sustainability Goals

### CO2e Emissions

**Formula**  

A sum of **CO2e** from the **Sustainability Ledger Entry**.

**Data Sources**

- Sustainability Ledger Entry

### CO2e Emissions (Excl Credits) 

**Formula**  

Uses the existing [CO2e Emissions](#co2e-emissions) and filters to where the document type isn't **GHG Credit**.

**Data Sources**

- Sustainability Ledger Entry

### CO2e Emissions Balance at Date

**Formula**  

Calculates the cumulative [CO2e Emissions](#co2e-emissions) up to the latest date in the current filter. It removes all date filters, then re-applies a filter to include only dates up to and including the latest date in the selection, which gives a running balance up to the specified date.

**Data Sources**

- Sustainability Ledger Entry

### CO2e Emissions Balance

**Formula**  

Calculates the total [CO2e Emissions](#co2e-emissions) across all dates, and ignores filters on the Date table. By removing date-based filtering, this measure provides the full value from the start to the end of the dataset.

**Data Sources**

- Sustainability Ledger Entry

### CO2e Baseline

**Formula**  

A sum of [CO2e Emissions](#co2e-emissions) based on the **Baseline Start** and **End Date** from the selected scorecards to determine a **Baseline** value.

**Data Sources**

- Sustainability Ledger Entry
- Sustainability Goals

### CO2e vs Baseline (%)

**Formula**  

The **CO2e Current Value** divided by the **CO2e Baseline**.

[CO2e Current Value](#co2e-current-value) / [CO2e Baseline](#co2e-baseline) 

**Data Sources**

- Sustainability Ledger Entry
- Sustainability Goals

### Discharged Into Water

**Formula**  

A sum of **Discharged Into Water** from the **Sustainability Ledger Entry**.

**Data Sources**

- Sustainability Ledger Entry

### Discharged Into Water Balance

**Formula**  

Calculates the total [Discharged Into Water](#discharged-into-water) value across all dates, and ignores filters on the Date table. By removing date-based filtering, this measure provides the full value from the start to the end of the dataset.

**Data Sources**

- Sustainability Ledger Entry

### Discharged Into Water Balance at Date 

**Formula**  

Calculates the cumulative [Discharged Into Water](#discharged-into-water) up to the latest date in the current filter. It removes all date filters, then re-applies a filter to include only dates up to and including the latest date in the selection, which gives a running balance up to the specified date.

**Data Sources**

- Sustainability Ledger Entry

### Discharged Into Water DOD

**Formula**  

Calculates the difference between the **Discharged Into Water** and the **Discharged Into Water PD**. It calculates the **Discharge Into Water** change directly in the measure as [Discharged Into Water PD](#discharged-into-water-pd) - [Discharged Into Water](#discharged-into-water)

Discharge Into Water Change / [Discharged Into Water PD](#discharged-into-water)

**Data Sources**

- Sustainability Ledger Entry

### Discharged Into Water PD

**Formula**  

Calculates the [Discharged Into Water](#discharged-into-water) for the prior day.

**Data Sources**

- Sustainability Ledger Entry

### Discharged Into Water PY

**Formula**  

Calculates the [Discharged Into Water](#discharged-into-water) for the prior year.

**Data Sources**

- Sustainability Ledger Entry

### Discharged Into Water YOY

**Formula**  

Calculates the difference between the **Discharged Into Water** and **Discharged Into Water PY**. It calculates the **Discharge Into Water** change directly in the measure as [Discharged Into Water PY](#discharged-into-water-py) - [Discharged Into Water](#discharged-into-water)

Discharge Into Water Change / [Discharged Into Water PY](#discharged-into-water)

**Data Sources**

- Sustainability Ledger Entry

### Discharged Into Water Baseline

**Formula**  

A sum of [Discharged Into Water](#discharged-into-water) based on the **Baseline Start** and **End Date** from the selected scorecards to determine a **Baseline** value.

**Data Sources**

- Sustainability Ledger Entry

### Discharged Into Water vs Baseline (%)

**Formula**  

The **Discharged Into Water** divided by the **Baseline**.

[Discharged Into Water](#discharged-into-water) / [Baseline](#discharged-into-water-balance) 

**Data Sources**

- Sustainability Ledger Entry

### Water Intensity

**Formula**  

Sum of **Water Intensity** from the **Sustainability Ledger Entry**.

**Data Sources**

- Sustainability Ledger Entry

### Water Intensity Balance at Date

**Formula**  

Calculates the cumulative [Water Intensity](#water-intensity) up to the latest date in the current filter. It removes all date filters, then re-applies a filter to include only dates up to and including the latest date within the selection, which gives a running balance up to the specified date.

**Data Sources**

- Sustainability Ledger Entry

### Water Intensity Balance

**Formula**  

Calculates the total [Water Intensity](#water-intensity) across all dates, and ignores filters on the Date table. By removing date-based filtering, this measure provides the full value from the start to the end of the dataset.

**Data Sources**

- Sustainability Ledger Entry

### Water Intensity DOD

**Formula**  

Calculates the difference between the **Water Intensity** and the **Water Intensity PD**. It calculates the **Water Intensity Change** directly in the measure as [Water Intensity PD](#water-intensity-pd) - [Water Intensity](#water-intensity)

Water Intensity Change / [Water Intensity PD](#water-intensity-pd)

**Data Sources**

- Sustainability Ledger Entry

### Water Intensity PD

**Formula**  

Calculates the [Water Intensity](#water-intensity) for the prior day.

**Data Sources**

- Sustainability Ledger Entry

### Water Intensity PY

**Formula**  

Calculates the [Water Intensity](#water-intensity) for the prior year.

**Data Sources**

- Sustainability Ledger Entry

### Water Intensity YOY

**Formula**  

Calculates the difference between the **Water Intensity** and the **Water Intensity PY**. It calculates the **Water Intensity Change** directly in the measure as [Water Intensity PY](#water-intensity-py) - [Water Intensity](#water-intensity)

Water Intensity Change / [Water Intensity PY](#water-intensity-py)

**Data Sources**

- Sustainability Ledger Entry

### Water Intensity Baseline

**Formula**  

A sum of [Water Intensity](#water-intensity) based on the **Baseline Start** and **End Date** from the selected scorecards to determine a **Baseline** value.

**Data Sources**

- Sustainability Ledger Entry

### Water Intensity vs Baseline (%)

**Formula**  

The **Water Intensity** divided by the **Baseline**.

[Water Intensity](#water-intensity) / [Baseline](#water-intensity-baseline)

**Data Sources**

- Sustainability Ledger Entry

### Water Available

**Formula**  

Calculated as **Facility Capacity** minus **Water Intensity**.

[Facility Capacity](#facility-capactity) - [Water Intensity](#water-intensity)

**Data Sources**

- Sustainability Ledger Entry

### Waste Intensity

**Formula**  

A sum of **Waste Intensity** from the **Sustainability Ledger Entry**.

**Data Sources**

- Sustainability Ledger Entry

### Waste Intensity Balance at Date 

**Formula**  

Calculates the cumulative [Water Intensity](#waste-intensity) up to the latest date in the current filter. It removes all date filters, then re-applies a filter to include only dates up to and including the latest date within the selection, which gives a running balance up to the specified date.

**Data Sources**

- Sustainability Ledger Entry

### Waste Intensity Balance

**Formula**  

Calculates the total [Waste Intensity](#waste-intensity) across all dates, and ignores filters on the Date table. By removing date-based filtering, this measure provides the full value from the start to the end of the dataset.

**Data Sources**

- Sustainability Ledger Entry

### Waste Intensity DOD

**Formula**  

Calculates the difference between the **Waste Intensity** and the **Waste Intensity PD**. It calculates the **Waste Intensity** change directly in the measure as [Waste Intensity PD](#waste-intensity-pd) - [Waste Intensity](#waste-intensity)

Waste Intensity Change / [Waste Intensity PD](#waste-intensity-pd)

**Data Sources**

- Sustainability Ledger Entry

### Waste Intensity PD

**Formula**  

Calculates the [Waste Intensity](#waste-intensity) for the prior day.

**Data Sources**

- Sustainability Ledger Entry

### Waste Intensity PY

**Formula**  

Calculates the [Waste Intensity](#waste-intensity) for the prior year.

**Data Sources**

- Sustainability Ledger Entry

### Waste Intensity YOY

**Formula**  

Calculates the difference between the **Waste Intensity** and the **Waste Intensity PY**. It calculates the **Waste Intensity** change directly in the measure as [Waste Intensity PY](#waste-intensity-py) - [Waste Intensity](#waste-intensity)

Waste Intensity Change / [Waste Intensity PY](#waste-intensity-py)

**Data Sources**

- Sustainability Ledger Entry

### Waste Intensity Baseline

**Formula**  

A sum of [Waste Intensity](#waste-intensity) based on the **Baseline Start** and **End Date** from the selected scorecards to determine a **Baseline** value.

**Data Sources**

- Sustainability Ledger Entry

### Waste Intensity vs Baseline (%)

**Formula**  

The **Waste Intensity** divided by the **Baseline**.

[Waste Intensity](#waste-intensity) / [Baseline](#waste-intensity-baseline) 

**Data Sources**

- Sustainability Ledger Entry

### Purchased Carbon Credits

**Formula**  

Uses the existing [CO2e Emissions](#co2e-emissions) and filters to where the document type is **GHG Credit**.

**Data Sources**

- Sustainability Ledger Entry

## Related information

[Sustainability Overview (Power BI Report)](sustainability-powerbi-sustainability-overview.md)  
[Sustainability management overview](finance-manage-sustainability.md)  
[Sustainability reports and analytics in Business Central](sustainability-reports.md)
