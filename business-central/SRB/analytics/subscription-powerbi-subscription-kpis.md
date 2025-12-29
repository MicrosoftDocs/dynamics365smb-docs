---
title: Subscription Billing KPIs and measures (Power BI)
description: Get an overview of all the KPIs and measures in the semantic model for the Power BI Subscription Billing app.
author: vanessa-mi
ms.author: bholtorf
ms.reviewer: 
ms.topic: article
ms.search.keywords: reporting
ms.search.form: 
ms.date: 12/15/2025
ms.service: dynamics-365-business-central
ms.custom: 
---

# KPIs and measures in the Power BI Subscription Billing app

This article lists and describes the key performance indicators (KPIs) included in the semantic model for the Power BI Subscription app. The descriptions include how the app calculates KPIs and the data it uses for its calculations.

Explore the KPIs to learn more about how they can help you achieve your business goals.

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Subscription Billing KPIs table

You can find all subscription billing KPIs in a dedicated table for calculated measures.

- **Recurring Revenue**
  - [Mon. Recurring Revenue](#mon-recurring-revenue)
  - [Mon. Recurring Revenue PY](#mon-recurring-revenue-py)
  - [Mon. Recurring Revenue delta vs. PY](#mon-recurring-revenue-delta-vs-py)
  - [Annual Recurring Revenue](#annual-recurring-revenue)
- **Recurring Cost**
  - [Mon. Recurring Cost](#mon-recurring-cost)
  - [Mon. Recurring Cost PY](#mon-recurring-cost-py)
  - [Mon. Recurring Cost delta vs. PY](#mon-recurring-cost-delta-vs-py)
- **Recurring Profit**
  - [Mon. Net Profit Amount](#mon-net-profit-amount)
  - [Mon. Net Profit Percentage](#mon-net-profit-percentage)
  - [Mon. Net Profit PY](#mon-net-profit-py)
  - [Mon. Net Profit delta vs. PY](#mon-net-profit-delta-vs-py)
- **Active Customers**
  - [Active Customers](#active-customers)
  - [Active Customers PY](#active-customers-py)
  - [Active Customers delta vs. PY](#active-customers-delta-vs-py)
- **Churn & New**
  - [Change in Mon. Recurring Revenue](#change-in-mon-recurring-revenue)
  - [Mon. Recurring Revenue Churn](#mon-recurring-revenue-churn)
  - [Mon. Recurring Revenue Downgrade](#mon-recurring-revenue-downgrade)
  - [Mon. Recurring Revenue Downgrade & Churn](#mon-recurring-revenue-downgrade--churn)
  - [Mon. Recurring Revenue New](#mon-recurring-revenue-new)
  - [Mon. Recurring Revenue Upgrade](#mon-recurring-revenue-upgrade)
  - [Mon. Recurring Revenue Change UBB](#mon-recurring-revenue-change-ubb)
  - [Avg. Mon. Churn Rate](#avg-mon-churn-rate)
  - [Avg. Mon. Downgrade Rate](#avg-mon-downgrade-rate)
- **Total Contract Value**
  - [Total Contract Value](#total-contract-value)
  - [Total Contract Value PY](#total-contract-value-py)
  - [Total Contract Value delta vs. PY](#total-contract-value-delta-vs-py)
- **Deferrals**
  - [Customer Deferrals](#customer-deferrals)
  - [Vendor Deferrals](#vendor-deferrals)
- **Forecast**
  - [Customer Billing Forecast](#customer-billing-forecast)
  - [Forecast Sales](#forecast-sales)
  - [Vendor Billing Forecast](#vendor-billing-forecast)
  - [Forecast Cost](#forecast-cost)

### Mon. Recurring Revenue

**Formula**  

This measure calculates the sum of monthly recurring revenue LCY over all active customer contract lines, evaluated by analysis date. If the report is filtered on a specific period, this measure will return the monthly recurring revenue for the latest month in that period. A customer contract line counts as active in the given period, if the subscription start date is on or before the analysis date and the subscription end date is empty, on or after the analysis date.

**Data Sources**

- Customer Contract Line

### Mon. Recurring Revenue PY

**Formula**  

This measure calculates [Mon. Recurring Revenue](#mon-recurring-revenue) in the same period of the previous year.

**Data Sources**

- Customer Contract Line

### Mon. Recurring Revenue delta vs. PY

**Formula**  

Difference between [Mon. Recurring Revenue](#mon-recurring-revenue) and [Mon. Recurring Revenue PY](#mon-recurring-revenue-py).

**Data Sources**

- Customer Contract Line

### Annual Recurring Revenue

**Formula**  

The annual recurring revenue is calculated as follows:

1. The Power BI report determines the remaining period for the contract line based on the subscription end date.
1. If the remaining period is larger than 1 year, annual recurring revenue LCY for this contract line is calculated as *monthly recurring revenue LCY x 12 months*.
1. If the remaining period is less than 1 year, the annual recurring revenue LCY for this contract line is calculated as *monthly recurring revenue LCY x remaining months*.
1. The measure then calculates the sum of annual recurring revenue LCY over all active customer contract lines, evaluated by analysis date. If the report is filtered on a specific period, this measure will return the annual recurring revenue based on the latest month in that period.

The calculation makes an exception for contract lines with usage based billing. Usage based subscriptions can fluctuate, so we cannot expect monthly recurring revenue to stay the same for the next 12 months. There is a possibility, that usage even drops to zero. In order to account for this uncertainty, the report viewer can choose between two possible calculations for usage based subscriptions. The calculation can be toggled with the filter value for **Treat Usage Based Billing as constant**:

1. If **Treat Usage Based Billing as constant** = **True**, the above calculation also applies to usage based contract lines. In this case, we assume that monthly recurring revenue for usage based subscriptions stays more or less constant.
1. If **Treat Usage Based Billing as constant** = **False**, the annual recurring revenue is the [Mon. Recurring Revenue](#mon-recurring-revenue). In this case, only the current monthly recurring revenue of a usage based subscription is added to the calculation of annual recurring revenue. This offers a conservative calculation of annual recurring revenue.

**Data Sources**

- Customer Contract Line

### Mon. Recurring Cost

**Formula**  

This measure calculates the sum of monthly recurring cost LCY over all active vendor contract lines, evaluated by analysis date. If the report is filtered on a specific period, this measure will return the monthly recurring cost for the latest month in that period. A vendor contract line counts as active in the given period, if the subscription start date is on or before the analysis date and the subscription end date is empty, on or after the analysis date.

**Data Sources**

- Vendor Contract Line

### Mon. Recurring Cost PY

**Formula**  

This measure calculates [Mon. Recurring Cost](#mon-recurring-cost) in the same period of the previous year.

**Data Sources**

- Vendor Contract Line

### Mon. Recurring Cost delta vs. PY

**Formula**  

Difference between [Mon. Recurring Cost](#mon-recurring-cost) and [Mon. Recurring Cost PY](#mon-recurring-cost-py).

**Data Sources**

- Vendor Contract Line

### Mon. Net Profit Amount

**Formula**  

*Mon. Net Profit Amount = [Mon. Recurring Revenue](#mon-recurring-revenue) - [Mon. Recurring Cost](#mon-recurring-cost)*

**Data Sources**

- Customer Contract Line
- Vendor Contract Line

### Mon. Net Profit Percentage

**Formula**  

*Mon. Net Profit Percentage = [Mon. Net Profit Amount](#mon-net-profit-amount) / [Mon. Recurring Revenue](#mon-recurring-revenue)*

**Data Sources**

- Customer Contract Line
- Vendor Contract Line

### Mon. Net Profit PY

**Formula**  

This measure calculates [Mon. Net Profit Amount](#mon-net-profit-amount) in the same period of the previous year.

**Data Sources**

- Customer Contract Line
- Vendor Contract Line

### Mon. Net Profit delta vs. PY

**Formula**  

Difference between [Mon. Net Profit Amount](#mon-net-profit-amount) and [Mon. Net Profit PY](#mon-net-profit-py).

**Data Sources**

- Customer Contract Line
- Vendor Contract Line

### Active Customers

**Formula**  

This measure counts the number of customers that have a positive [Mon. Recurring Revenue](#mon-recurring-revenue) in the selected period.

**Data Sources**

- Customers
- Customer Contract Line

### Active Customers PY

**Formula**  

This measure counts the number of customers with [Mon. Recurring Revenue](#mon-recurring-revenue) greater than zero in the same period of the previous year.

**Data Sources**

- Customers
- Customer Contract Line

### Active Customers delta vs. PY

**Formula**  

Difference between [Active Customers](#active-customers) and [Active Customers PY](#active-customers-py).

**Data Sources**

- Customers
- Customer Contract Line

### Change in Mon. Recurring Revenue

**Formula**

This measure sums up the change in [Mon. Recurring Revenue](#mon-recurring-revenue) between the current and the previous month. All possible **Change Type** values are included.

**Data Sources**

- Customer Contract Changes

### Mon. Recurring Revenue Churn

**Formula**

This measure calculates the sum of [Change in Mon. Recurring Revenue](#change-in-mon-recurring-revenue) where **Change Type** = **Churn**. If a customer contract line has zero [Mon. Recurring Revenue](#mon-recurring-revenue) in the next month compared to the current month, it is identified as churn for that current month. **Mon. Recurring Revenue Churn** returns the churn amount as a positive value. **Mon. Recurring Revenue Churn (-)** returns the same absolute value with a negative sign.

**Data Sources**

- Customer Contract Changes

### Mon. Recurring Revenue Downgrade

**Formula**

This measure calculates the sum of [Change in Mon. Recurring Revenue](#change-in-mon-recurring-revenue) where **Change Type** = **Downgrade**. If the [Mon. Recurring Revenue](#mon-recurring-revenue) of a customer contract line is lower in the current month compared to the previous month, it is identified as downgrade for that current month. **Mon. Recurring Revenue Downgrade** returns the downgrade amount as a positive value. **Mon. Recurring Revenue Downgrade (-)** returns the same absolute value with a negative sign.

**Data Sources**

- Customer Contract Changes

### Mon. Recurring Revenue Downgrade & Churn

**Formula**

This measure calculates the sum of [Change in Mon. Recurring Revenue](#change-in-mon-recurring-revenue) where **Change Type** = **Churn** or **Downgrade**. It returns the churn & downgrade amount as a positive value.

**Data Sources**

- Customer Contract Changes

### Mon. Recurring Revenue New

**Formula**

This measure calculates the sum of [Change in Mon. Recurring Revenue](#change-in-mon-recurring-revenue) where **Change Type** = **New**. If the subscription start date of a customer contract line lies in the current month, or the customer contract line appears for the first time in the current month and did not exist in the previous month, the [Mon. Recurring Revenue](#mon-recurring-revenue) of that customer contract line is considered new monthly recurring revenue.

**Data Sources**

- Customer Contract Changes

### Mon. Recurring Revenue Upgrade

**Formula**

This measure calculates the sum of [Change in Mon. Recurring Revenue](#change-in-mon-recurring-revenue) where **Change Type** = **Upgrade**. If the [Mon. Recurring Revenue](#mon-recurring-revenue) of a customer contract line is higher in the current month compared to the previous month, it is identified as upgrade for that current month.

**Data Sources**

- Customer Contract Changes

### Mon. Recurring Revenue Change UBB

**Formula**

This measure calculates the sum of [Change in Mon. Recurring Revenue](#change-in-mon-recurring-revenue) for usage based customer contract lines.

**Data Sources**

- Customer Contract Changes

### Avg. Mon. Churn Rate

**Formula**

This measure calculates the churn rate for each month in the filtered period: *[Mon. Recurring Revenue Churn](#mon-recurring-revenue-churn) / [Mon. Recurring Revenue](#mon-recurring-revenue) of previous month*. It then calculates the average of those monthly rates by dividing the sum of monthly churn rates by the number of months in the filtered period.

**Data Sources**

- Customer Contract Changes
- Customer Contract Line

### Avg. Mon. Downgrade Rate

**Formula**

This measure calculates the downgrade rate for each month in the filtered period: *[Mon. Recurring Revenue Downgrade](#mon-recurring-revenue-downgrade) / [Mon. Recurring Revenue](#mon-recurring-revenue) of previous month*. It then calculates the average of those monthly rates by dividing the sum of monthly downgrade rates by the number of months in the filtered period.

**Data Sources**

- Customer Contract Changes
- Customer Contract Line

### Total Contract Value

**Formula**

The total contract value is calculated as follows:

1. The Power BI report determines the remaining contractual period in months for the contract line:
   - If the subscription end date is not empty, the remaining period is calculated from the current period to the subscription end date.
   - Else, if the term until date is not empty, the remaining period is calculated from the current period to the term until date.
   - Else, parameter **Default Contract Term** is used as remaining period.
1. Total contract value LCY is then calculated as *monthly recurring revenue LCY x months in remaining period*.
1. The measure then calculates the sum of total contract value LCY over all customer contract lines, evaluated by analysis date. If the report is filtered on a specific period, this measure will return the total contract value based on the latest month in that period.

The calculation makes an exception for contract lines with usage based billing. Usage based subscriptions can fluctuate, so we cannot expect monthly recurring revenue to stay the same within the remaining term. There is a possibility, that usage even drops to zero. In order to account for this uncertainty, the report viewer can choose between two possible calculations for usage based subscriptions. The calculation can be toggled with the filter value for **Treat Usage Based Billing as constant**:

1. If **Treat Usage Based Billing as constant** = **True**, the above calculation also applies to usage based contract lines. In this case, we assume that monthly recurring revenue for usage based subscriptions stays more or less constant.
1. If **Treat Usage Based Billing as constant** = **False**, the total contract value is the [Mon. Recurring Revenue](#mon-recurring-revenue). In this case, only the current monthly recurring revenue of a usage based subscription is added to the calculation of total contract revenue. This offers a conservative calculation of the total contract value.

**Data Sources**

- Customer Contract Line

### Total Contract Value PY

**Formula**  

This measure calculates [Total Contract Value](#total-contract-value) in the same period of the previous year.

**Data Sources**

- Customer Contract Line

### Total Contract Value delta vs. PY

**Formula**  

Difference between [Total Contract Value](#total-contract-value) and [Total Contract Value PY](#total-contract-value-py).

**Data Sources**

- Customer Contract Line

### Customer Deferrals

**Formula**

Sum of **Amount** in **Customer Contract Deferrals**.

**Data Sources**

- Customer Contract Deferrals

### Vendor Deferrals

**Formula**

Sum of **Amount** in **Vendor Contract Deferrals**.

**Data Sources**

- Vendor Contract Deferrals

### Customer Billing Forecast

**Formula**

This forecast projects future billing amounts based on the **Next Billing Date** and **Billing Rhythm** of each customer contract line. It allocates the expected revenue to the month in which it is scheduled to be billed and runs up to the end date defined in the **Power BI Reports Setup** in Business Central. The measure considers all currently active customer contract lines up to their subscription end date.

The calculation makes an exception for contract lines with usage based billing. Usage based subscriptions can fluctuate, so we cannot expect monthly recurring revenue to stay the same within the remaining term. There is a possibility, that usage even drops to zero. In order to account for this uncertainty, the report viewer can choose between two possible calculations for usage based subscriptions. The calculation can be toggled with the filter value for **Treat Usage Based Billing as constant**:

1. If **Treat Usage Based Billing as constant** = **True**, the above calculation also applies to usage based contract lines. In this case, we assume that monthly recurring revenue for usage based subscriptions stays more or less constant.
1. If **Treat Usage Based Billing as constant** = **False**, the **Customer Billing Forecast** returns the future billing amount for the next billing date only.

**Data Sources**

- Customer Billing Forecast
- Customer Contract Line

### Forecast Sales

**Formula**

This forecast projects the [Mon. Recurring Revenue](#mon-recurring-revenue) for all future months up to the end date defined in the **Power BI Reports Setup** in Business Central. The measure considers all currently active customer contract lines up to their subscription end date.

The calculation makes an exception for contract lines with usage based billing. The calculation can be toggled with the filter value for **Treat Usage Based Billing as constant**:

1. If **Treat Usage Based Billing as constant** = **True**, the above calculation also applies to usage based contract lines. In this case, we assume that monthly recurring revenue for usage based subscriptions stays more or less constant.
1. If **Treat Usage Based Billing as constant** = **False**, the **Forecast Sales** includes the monthly recurring revenue of usage based subscriptions only for one month.

**Data Sources**

- Customer Contract Line

### Vendor Billing Forecast

**Formula**

This forecast projects future billing amounts based on the **Next Billing Date** and **Billing Rhythm** of each vendor contract line. It allocates the expected cost to the month in which it is scheduled to be billed and runs up to the end date defined in the **Power BI Reports Setup** in Business Central. The measure considers all currently active vendor contract lines up to their subscription end date.

The calculation makes an exception for contract lines with usage based billing. Usage based subscriptions can fluctuate, so we cannot expect monthly recurring cost to stay the same within the remaining term. There is a possibility, that usage even drops to zero. In order to account for this uncertainty, the report viewer can choose between two possible calculations for usage based subscriptions. The calculation can be toggled with the filter value for **Treat Usage Based Billing as constant**:

1. If **Treat Usage Based Billing as constant** = **True**, the above calculation also applies to usage based contract lines. In this case, we assume that monthly recurring cost for usage based subscriptions stays more or less constant.
1. If **Treat Usage Based Billing as constant** = **False**, the **Vendor Billing Forecast** returns the future billing amount for the next billing date only.

**Data Sources**

- Vendor Billing Forecast
- Vendor Contract Line

### Forecast Cost

**Formula**

This forecast projects the [Mon. Recurring Cost](#mon-recurring-cost) for all future months up to the end date defined in the **Power BI Reports Setup** in Business Central. The measure considers all currently active vendor contract lines up to their subscription end date.

The calculation makes an exception for contract lines with usage based billing. The calculation can be toggled with the filter value for **Treat Usage Based Billing as constant**:

1. If **Treat Usage Based Billing as constant** = **True**, the above calculation also applies to usage based contract lines. In this case, we assume that monthly recurring cost for usage based subscriptions stays more or less constant.
1. If **Treat Usage Based Billing as constant** = **False**, the **Forecast Cost** includes the monthly recurring cost of usage based subscriptions only for one month.

**Data Sources**

- Vendor Contract Line

## Related information

[Track your business KPIs with Power BI metrics](../../track-kpis-with-power-bi-metrics.md)  
[Setting up the Subscription Billing Power BI app](subscription-powerbi-app-setup.md)
[Subscription Billing controlling](../controlling.md)
[Subscription Billing overview](../welcome.md)