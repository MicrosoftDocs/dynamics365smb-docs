---
title: Aged Accounts Payables (Excel report)
description: Analyze vendor balances at the end of each period. Used as a gauge to measure the reliability of what your owe your vendors.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: Report_4403_Primary
ms.date: 12/14/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 12/14/2024
ai.usage: ai-assisted
---

# Aged Accounts Payables Excel (report)

The **Aged Accounts Payables Excel** report shows aggregated ageing data based on vendor ledger entries. 

The data is aggregated and bucketed according to the ‘Aged as of' and ‘Period length' parameters in the reports request page. 

The aggregated data is summarised per the 2 global dimensions.

The report Excel workbook contains four worksheets that you can use to analyze your aged accounts payables:
- By period (LCY)
- By Period (FCY)
- Due by Currencies
- CustomerAgingData

Each worksheet represents a different dimension to your analysis.

[!INCLUDE [onedrive-excel-online](../includes/onedrive-excel-online.md)]

> [!NOTE]
> This report performs calculations when viewed in Excel online or when downloaded and opened on your computer. If you see a banner with a text about external data connections, you might need to choose the botton **Enable content** to load data. The report does not connect to any external data sources, all calculations are done in Excel with Power Query. In some cases (depending on the security configurations for your organization), you might also need to right-click on a pivot table in one of the worksheets and choose **Refresh** to see data in the reports.


## By period (LCY) worksheet

This worksheet shows amounts in local currency by vendor and with the ability to see data grouped by a Year-Quarter-Month-Day hierachy on Due Date.

With filters and slicers, you can zoom into a single vendor or a group of vendors.

:::image type="content" source="../media/excel-aged-accounts-payable-by-period-LCY.png" alt-text="Screenshot of the By period (LCY) worksheet":::


## By Period (FCY) worksheet

This worksheet shows amounts in foreign currency by vendor and with the ability to see data grouped by a Year-Quarter-Month-Day hierachy on Due Date.

With filters and slicers, you can zoom into a single vendor or a group of vendors. You can also filter by one or more Currency Codes, should you need this. 

:::image type="content" source="../media/excel-aged-accounts-payable-by-period-FCY.png" alt-text="Screenshot of the By period (FCY) worksheet":::


## Due by Currencies worksheet

This worksheet shows amounts by currency code and with the ability to see data grouped by a Year-Quarter-Month-Day hierachy on Due Date.

With filters and slicers, you can zoom into a single vendor or a group of vendors. You can also filter by one or more Currency Codes, should you need this. 

:::image type="content" source="../media/excel-aged-accounts-payable-due-by-currencies.png" alt-text="Screenshot of the Due by Currencies worksheet":::


## VendorAgingData worksheet

This worksheet shows the raw data used in the report. 

You can use this worksheet for data analysis assisted by built-in tools in Excel, such as [!INCLUDE [excel-copilot-name](../includes/excel-copilot-name.md)] or the What-if-analysis or Forecast Sheet tools.

:::image type="content" source="../media/finance/excel-aged-accounts-payable-vendor-aging-data.png" alt-text="Screenshot of the VendorAgingData worksheet":::

To learn more, go to [Get started with Copilot in Excel](https://support.microsoft.com/en-us/office/get-started-with-copilot-in-excel-d7110502-0334-4b4f-a175-a73abdfc118a)


## Use cases

[!INCLUDE [report-4403-scenario](../includes/report-4402-scenario-include.md)]


## Try the report

Try the report here: [Aged Accounts Payables Excel](https://businesscentral.dynamics.com?report=4403)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Alternative reports

There are multiple other options for analyzing your aged accounts payables. To learn more, go to

- [Aged Payables (Back Dating) in Power BI](../finance-powerbi-aged-payables-back-dating.md)
- [Using data analysis to analyze accounts payable](../ad-hoc-analysis-finance.md#example-finance-accounts-payable)

## See also

[Accounts payable analytics](../receivables-reports.md)  
[Key finance report overview](../finance-reports.md)  
[Ad hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]