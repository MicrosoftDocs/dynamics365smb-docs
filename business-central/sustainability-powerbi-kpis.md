---
title: Sustainability KPIs and measures (Power BI)
description: Get an overview of all the KPIs and measures in the semantic model for the Sustainability Power BI app.
author: 
ms.author: 
ms.reviewer: 
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: 
ms.date: 04/28/2025
ms.service: dynamics-365-business-central
---

# Power BI Sustainability app KPIs and measures

This page provides a list of all Key Performance Indicators (KPIs) included in the semantic model for the Power BI Sustainability report. 

Explore the list of KPIs below to learn more about how they can help you achieve your business goals. 

Each KPI is described, including how it is calculated and what data was used in the calculations.

## Emission Fees Table

**Emissions Fees Measures**
- [CH4 Carbon Equivalent](#ch4-carbon-equivalent)
- [CO2 Carbon Equivalent](#co2-carbon-equivalent)
- [N2O Carbon Equivalent](#N2o-carbon-equivalent)
- [CO2e Target](#co2e-target)


### CH4 Carbon Equivilent
**Formula**  
A sum of the Carbon Equivalent Factor where the Emission Type is CH4

**Data Sources**
- Emissions Fees

### C02 Carbon Equivilent
**Formula**  
A sum of the Carbon Equivalent Factor where the Emission Type is CO2.

**Data Sources**
- Emissions Fees

### N2O Carbon Equivilent
**Formula**  
A sum of the Carbon Equivalent Factor where the Emission Type is N2O.

**Data Sources**
- Emissions Fees

### CO2e Target
**Formula**  
A calculation of all Carbon Equivalent factors and there targets shown as one figure.

**Data Sources**
- Emissions Fees
- Sustainability Goals

## Employee Absences Table

**Employee Absences Measures**
- [Employee Absences](#employee-absences)
- [Employee Absences (%)](#employee-absences-)

### Employee Absences
**Formula**  
A sum of Employee Absences Quantity

**Data Sources**
- Employee Absence

### Employee Absences (%)
**Formula**  
A calculation of the [Employee Absences](#employee-absences) multipled by [Active Employees](#active-employees) and divided by Working Days to calculate the percentage of Absence Hours.

**Data Sources**
- Employees
- Employee Absence

## Employee Ledger Entries Table

**Employee Ledger Entries Measures**
- [Employee Amount](#employee-amount)

### Employee Amount
**Formula**  
Sum of the Amount field from the Employee Ledger Entries.

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
A filter on the  [No. of Employees](#no-of-employees) where the Status of the Employee is Active.

**Data Sources**
- Employee

### Age
**Formula**  
A calculated column against the Employee to determine the age of the Employee based on the Employee Date of Birth.

**Data Sources**
- Employee

### Age Distribution
**Formula**  
A calculated column to group Employees into one of three different age distributions.

[!NOTE]
> The age distrubition is defined directly in Power BI. The grouping is Under 30, between 30 and 50 and then Over 50. This is currently not adjustable.

**Data Sources**
- Employee

### Female Employees (%)
**Formula**  
A division of the No. of Female Employees by the No. of Employees.

[No. of Female Employees](#no-of-female-employees) / [No. of Employees](#no-of-employees)

**Data Sources**
- Employee

### Male Employees (%)
**Formula**  
A division of the No. of Male Employees by the No. of Employees.

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
A filter on the  [No. of Employees](#no-of-employees) where the Employee Gender is Female.

**Data Sources**
- Employee

### No. of Male Employees
**Formula**  
A filter on the  [No. of Employees](#no-of-employees) where the Employee Gender is Male.

**Data Sources**
- Employee

### No. of Other Employees
**Formula**  
A filter on the  [No. of Employees](#no-of-employees) where the Employee Gender is not Male or Female.

**Data Sources**
- Employee

### Other Employees (%)
**Formula**  
A division of the No. of Other Employees by the No. of Employees.

[No. of Other Employees](#no-of-other-employees) / [No. of Employees](#no-of-employees)

**Data Sources**
- Employee

## Responsibility Centre Table

**Responsibility Centre Measures**
- [Facility Capactity](#facility-capactity)

### Facility Capactity
**Formula**  
Measures the water capacity of the facility (Responsibilty Centre). This will be based on the Month in Period when filtering.

**Data Sources**
- Responsibility Centre

## Sustainability Goals Table

**Sustainability Goals Measures**
- [CO2 Current Value](#co2-target)
- [CO2 Target](#co2-target)
- [CO2 Realized (%)](#co2-target)
- [CH4 Current Value](#ch4-target)
- [CH4 Target](#ch4-target)
- [CH4 Realized (%)](#ch4-target)
- [N2O Current Value](#n2o-target)
- [N2O Target](#n2o-target)
- [N2O Realized (%)](#n2o-target)
- [Waste Current Value](#waste-target)
- [Waste Target](#waste-target)
- [Waste Realized (%)](#waste-target)
- [Water Current Value](#water-target)
- [Water Target](#water-target)
- [Water Realized (%)](#water-target)

### CH4 Current Value
**Formula**  
A Sum of [CO2 Emissions](#co2) based on the Start and End date from the selected scorecard(s)

**Data Sources**
- Sustainability Ledger Entries
- Sustainability Goals

### CO2 Target
**Formula**  
Sum of Target Value for CO2.

**Data Sources**
- Sustainability Goals

### CO2 Realized (%)
**Formula**  
A calculation of the CH4 Current Value divided by the CH4 Emissions

[CO2 Current Value](#co2-current-value) / [CO2 Target](#co2-target) 

**Data Sources**
- Sustainability Ledger Entries
- Sustainability Goals

### CH4 Current Value
**Formula**  
A Sum of [CH4 Emissions](#ch4) based on the Start and End date from the selected scorecard(s)

**Data Sources**
- Sustainability Ledger Entries
- Sustainability Goals

### CH4 Target
**Formula**  
Sum of Target Value for CH4.

**Data Sources**
- Sustainability Goals

### CH4 Realized (%)
**Formula**  
A calculation of the CH4 Current Value divided by the CH4 Emissions

[CH4 Current Value](#ch4-current-value) / [CH4 Target](#ch4-target) 

**Data Sources**
- Sustainability Ledger Entries
- Sustainability Goals

### N20 Current Value
**Formula**  
A Sum of [N2O Emissions](#n2o) based on the Start and End date from the selected scorecard(s)

**Data Sources**
- Sustainability Ledger Entries
- Sustainability Goals

### N2O Target
**Formula**  
Sum of Target Value for N2O from the Sustainabilty Goals.

**Data Sources**
- Sustainability Goals

### N2O Realized (%)
**Formula**  
A calculation of the N2O Current Value divided by the N2O Emissions

[N2O Current Value](#n2o-current-value) / [n2o Target](#n2o-target) 

**Data Sources**
- Sustainability Ledger Entries
- Sustainability Goals

### Waste Current Value
**Formula**  
A Sum of [Waste Intensity](#waste-intensity) based on the Start and End date from the selected scorecard(s)

**Data Sources**
- Sustainability Ledger Entries
- Sustainability Goals

### Waste Target
**Formula**  
Sum of Target Value for Waste.

**Data Sources**
- Sustainability Goals

### Waste Realized (%)
**Formula**  
A calculation of the Waste Current Value divided by the Waste Emissions

[Waste Current Value](#waste-current-value) / [Waste Target](#waste-target) 

**Data Sources**
- Sustainability Ledger Entries
- Sustainability Goals

### Water Current Value
**Formula**  
A Sum of [Water Intensity](#water-intensity) based on the Start and End date from the selected scorecard(s)

**Data Sources**
- Sustainability Ledger Entries
- Sustainability Goals

### Water Target
**Formula**  
Sum of Target Value for Water.

**Data Sources**
- Sustainability Goals

### Water Realized (%)
**Formula**  
A calculation of the Water Current Value divided by the Water Emissions

[Water Current Value](#water-current-value) / [Water Target](#water-target) 

**Data Sources**
- Sustainability Ledger Entries
- Sustainability Goals

## Sustainability Ledger Entries Table

**Sustainability Ledger Entries Measures**
- [CO2 Emissions](#co2-emissions)
- [CO2 Emissions Balance](#balance-co2-emissions)
- [CO2 Emissions Balance at Date ](#balance-at-date-co2-emissions)
- [CO2 Baseline](#co2-emissions) 
- [CO2 vs Baseline (%)](#co2-emissions)

- [CH4 Emissions](#ch4-emissions)
- [CH4 Emissions Balance at Date ](#balance-at-date-ch4-emissions)
- [CH4 Emissions Balance](#balance-ch4-emissions)
- [CH4 Baseline](#co2-emissions) 
- [CH4 vs Baseline (%)](#co2-emissions)


- [N2O Emissions](#n2o-emissions)
- [N2O Emissions Balance](#n2o-emissions)
- [N2O Emissions Balance at Date](#n2o-emissions)
- [N2O Baseline](#co2-emissions) 
- [N2O vs Baseline (%)](#co2-emissions)

- [CO2e](#co2e)
- [CO2e Emissions Balance](#n2o-emissions)
- [CO2e Emissions Balance at Date](#n2o-emissions)
- [CO2e Baseline](#co2-emissions) 
- [CO2e vs Baseline (%)](#co2-emissions)

- [Discharged Into Water](#discharged-into-water)
- [Water Intensity](#water-intensity)
- [Waste Intensity](#waste-intensity)

### CO2 Emissions
**Formula**  
Sum of CO2 from the Sustainability Ledger Entry.

**Data Sources**
- Sustainability Ledger Entry

### CO2 Emissions Balance
**Formula**  
The Balance measure calculates the total [CO2 Emissions](#co2-emissions) across all dates, ignoring any filters on the Date table. By removing date-based filtering, this measure provides the full  value from the start to the end of the dataset, regardless of any date selections applied in the report.

**Data Sources**
- Sustainability Ledger Entry

### CO2 Emissions Balance at Date 
**Formula**  
The Balance at Date CO2 Emissions measure calculates the cumulative [CO2 Emissions](#co2-emissions) up to the latest date in the current filter context. It removes all date filters, then re-applies a filter to include only dates up to and including the maximum date within the selection. This provides a running balance up to the specified date.

**Data Sources**
- Sustainability Ledger Entry

### CO2 Baseline
**Formula**  
A Sum of [CO2 Emissions](#co2-emissions) based on the Baseline Start and End Date from the selected scorecard(s) to determine a Baseline value.

**Data Sources**
- Sustainability Ledger Entry
- Sustainability Goals

### CO2 vs Baseline (%)
**Formula**  
A calculation of the CO2 Current Value divided by the CO2 Baseline

[CO2 Current Value](#co2-current-value) / [CO2 Baseline](#co2-baseline) 
**Data Sources**
- Sustainability Ledger Entry
- Sustainability Goals

### CH4 Emissions
**Formula**  
Sum of CH4 from the Sustainability Ledger Entry.

**Data Sources**
- Sustainability Ledger Entry

### Balance at Date CH4 Emissions
**Formula**  
The Balance at Date CH4 Emissions measure calculates the cumulative [CH4](#ch4) up to the latest date in the current filter context. It removes all date filters, then re-applies a filter to include only dates up to and including the maximum date within the selection. This provides a running balance up to the specified date.

**Data Sources**
- Sustainability Ledger Entry

### Balance CH4 Emissions
**Formula**  
The Balance measure calculates the total [ CH4](#ch4) across all dates, ignoring any filters on the Date table. By removing date-based filtering, this measure provides the full  value from the start to the end of the dataset, regardless of any date selections applied in the report.

**Data Sources**
- Sustainability Ledger Entry

### CH4 Baseline
**Formula**  
A Sum of [CH4 Emissions](#ch4-emissions) based on the Baseline Start and End Date from the selected scorecard(s) to determine a Baseline value.

**Data Sources**
- Sustainability Ledger Entry
- Sustainability Goals

### CO2 vs Baseline (%)
**Formula**  
A calculation of the CH4 Current Value divided by the CH4 Baseline

[CH4 Current Value](#ch4-current-value) / [CH4 Baseline](#ch4-baseline) 
**Data Sources**
- Sustainability Ledger Entry
- Sustainability Goals

### N2O Emissions
**Formula**  
Sum of N2O from the Sustainability Ledger Entry.

**Data Sources**
- Sustainability Ledger Entry

### Balance at Date N2O Emissions
**Formula**  
The Balance at Date N2O Emissions measure calculates the cumulative [N2O](#n20) up to the latest date in the current filter context. It removes all date filters, then re-applies a filter to include only dates up to and including the maximum date within the selection. This provides a running balance up to the specified date.

**Data Sources**
- Sustainability Ledger Entry

### Balance N2O Emissions
**Formula**  
The Balance measure calculates the total [N2O](#n20) across all dates, ignoring any filters on the Date table. By removing date-based filtering, this measure provides the full  value from the start to the end of the dataset, regardless of any date selections applied in the report.

**Data Sources**
- Sustainability Ledger Entry

### N2O Baseline
**Formula**  
A Sum of [N2O Emissions](#n2o-emissions) based on the Baseline Start and End Date from the selected scorecard(s) to determine a Baseline value.

**Data Sources**
- Sustainability Ledger Entry
- Sustainability Goals

### N2O vs Baseline (%)
**Formula**  
A calculation of the N2O Current Value divided by the N2O Baseline

[N2O Current Value](#n2o-current-value) / [N2O Baseline](#n2o-baseline) 
**Data Sources**
- Sustainability Ledger Entry
- Sustainability Goals

### CO2e Emissions
**Formula**  
Sum of CO2e from the Sustainability Ledger Entry.

**Data Sources**
- Sustainability Ledger Entry

### Balance at Date CO2e Emissions
**Formula**  
The Balance at Date CO2e Emissions measure calculates the cumulative [CO2e](#co2e) up to the latest date in the current filter context. It removes all date filters, then re-applies a filter to include only dates up to and including the maximum date within the selection. This provides a running balance up to the specified date.

**Data Sources**
- Sustainability Ledger Entry

### Balance CO2e Emissions
**Formula**  
The Balance measure calculates the total [CO2e](#co2e) across all dates, ignoring any filters on the Date table. By removing date-based filtering, this measure provides the full  value from the start to the end of the dataset, regardless of any date selections applied in the report.

**Data Sources**
- Sustainability Ledger Entry

### CO2e Baseline
**Formula**  
A Sum of [CO2e Emissions](#co2e-emissions) based on the Baseline Start and End Date from the selected scorecard(s) to determine a Baseline value.

**Data Sources**
- Sustainability Ledger Entry
- Sustainability Goals

### CO2e vs Baseline (%)
**Formula**  
A calculation of the CO2e Current Value divided by the CO2e Baseline

[CO2e Current Value](#co2e-current-value) / [CO2e Baseline](#co2e-baseline) 
**Data Sources**
- Sustainability Ledger Entry
- Sustainability Goals

### Discharged Into Water
**Formula**  
Sum of Discharged into Water from the Sustainability Ledger Entry.

**Data Sources**
- Sustainability Ledger Entry

### Balance at Date Discharged Into Water
**Formula**  
The Balance at Date Discharged Into Water measure calculates the cumulative [Discharged Into Water](#discharged-into-water) up to the latest date in the current filter context. It removes all date filters, then re-applies a filter to include only dates up to and including the maximum date within the selection. This provides a running balance up to the specified date.

**Data Sources**
- Sustainability Ledger Entry

### Balance Discharged Into Water
**Formula**  
The Balance measure calculates the total [Discharged Into Water](#discharged-into-water) across all dates, ignoring any filters on the Date table. By removing date-based filtering, this measure provides the full  value from the start to the end of the dataset, regardless of any date selections applied in the report.

**Data Sources**
- Sustainability Ledger Entry

### Water Intensity
**Formula**  
Sum of Water Intensity from the Sustainability Ledger Entry.

**Data Sources**
- Sustainability Ledger Entry

### Balance at Date Water Intensity
**Formula**  
The Balance at Date Water Intensity measure calculates the cumulative [Water Intensity](#water-intensity) up to the latest date in the current filter context. It removes all date filters, then re-applies a filter to include only dates up to and including the maximum date within the selection. This provides a running balance up to the specified date.

**Data Sources**
- Sustainability Ledger Entry

### Balance Water Intensity
**Formula**  
The Balance Water Intensity measure calculates the total [Water Intensity](#water-intensity) across all dates, ignoring any filters on the Date table. By removing date-based filtering, this measure provides the full  value from the start to the end of the dataset, regardless of any date selections applied in the report.

**Data Sources**
- Sustainability Ledger Entry

### Waste Intensity
**Formula**  
Sum of Waste Intensity from the Sustainability Ledger Entry.

**Data Sources**
- Sustainability Ledger Entry

### Balance at Date Waste Intensity
**Formula**  
The Balance at Date Discharged Into Water measure calculates the cumulative [Water Intensity](#waste-intensity) up to the latest date in the current filter context. It removes all date filters, then re-applies a filter to include only dates up to and including the maximum date within the selection. This provides a running balance up to the specified date.

**Data Sources**
- Sustainability Ledger Entry

### Balance Waste Intensity
**Formula**  
The Balance measure calculates the total [Waste Intensity](#waste-intensity) across all dates, ignoring any filters on the Date table. By removing date-based filtering, this measure provides the full  value from the start to the end of the dataset, regardless of any date selections applied in the report.

**Data Sources**
- Sustainability Ledger Entry

**Baseline Calculation Measures**

