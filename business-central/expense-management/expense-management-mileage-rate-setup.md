---
title: Set Up Mileage Rates for Expense Management
description: Configure mileage reimbursement rates by vehicle type, currency, and date range so Business Central applies the correct rate automatically.
author: jswymer
ms.topic: how-to
ms.date: 09/26/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ms.search.form: Primary_7128, 7130, 6988
ai-usage: ai-assisted
---

# Set up mileage rates for expense management

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Use the **Mileage Rate Setup** page to define effective-dated mileage reimbursement rates by vehicle type and currency. Business Central uses these rates to calculate mileage expenses and expense report lines.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Before you start

- You need the **Expense Management - Admin** permission set or equivalent permissions.
- On the **Expense Agent Setup** page, set **Default Mileage UOM** and **Standard Rate of Mileage**. In assisted setup, these fields are named **Default unit of distance** and **Rate per unit**. Business Central uses **Standard Rate of Mileage** when no mileage rate setup record matches an expense. Learn more in [Set up Expense Agent](expense-agent-configuration-page.md).

## Set up vehicle types

Your organization defines the vehicle types that expense users can select. If you use vehicle-specific mileage rates, create the vehicle types before you set up the rates.

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Vehicle Types**, and then choose the related link.
1. On the **Vehicle Types** page, choose **New**.
1. Enter a **Code** and **Description** for the vehicle type, such as a car or motorcycle.
1. Create more vehicle types as needed.

## Configure a mileage rate

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Mileage Rate Setup**, and then choose the related link.
1. Select **New** to add a rate.
1. Fill in the fields:
   - **Code**: Enter a unique code for the rate.
   - **Vehicle Type**: Optionally, select the vehicle type that the rate applies to. A blank value applies only to expenses that also have a blank **Vehicle Type**.
   - **Starting Date**: Enter the first date that the rate applies. This field is required.
   - **Ending Date**: Optionally, enter the last date that the rate applies. Leave this field blank to keep the period open-ended.
   - **Rate**: Enter a nonnegative reimbursement amount per unit of distance.
   - **Currency Code**: Optionally, select the currency that the rate is expressed in. Leave this field blank to define the rate in the local currency.
1. Create more rates for different vehicle types, currencies, or date ranges as needed.

The starting and ending dates are both included in the effective period. Date ranges can't overlap for the same **Vehicle Type** and **Currency Code** combination. Start a following period on the day after the previous period ends.

## Understand how Business Central selects a rate

Business Central uses the **Expense Date** to find a rate whose effective period includes that date. The **Vehicle Type** must match exactly. A blank **Vehicle Type** isn't a wildcard and matches only an expense with a blank **Vehicle Type**.

For the matching vehicle type and date, Business Central selects rates in this order:

1. A rate with a **Currency Code** that matches the expense currency.
1. A rate with a blank **Currency Code**, which is a local-currency rate. Business Central converts this rate to the expense currency using the exchange rate for the expense date.
1. **Standard Rate of Mileage** from the **Expense Agent Setup** page if no mileage rate setup record matches. Business Central treats the fallback as a local-currency rate and converts it when needed.

Business Central calculates the reimbursement as effective distance multiplied by the applicable rate. For a round trip, Business Central doubles the distance first. Business Central rounds a converted rate and the final reimbursement by using the rounding precision configured for the expense currency.

## Understand when rate changes apply

Editing mileage rate setup doesn't automatically recalculate existing expenses or expense reports. Business Central applies the current setup when it creates or recalculates an open mileage expense or expense report line. For example, changing the expense date, currency, vehicle type, distance, or round-trip setting on an open record can cause recalculation.

Posted expenses aren't recalculated. Review open mileage expenses and reports that must use a changed rate.

## Related information

[Set up per diem and mileage allowances](expense-management-per-diem-mileage.md)
[Create and manage expenses](expense-management-create-expenses.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
