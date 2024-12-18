---
title: Aged Accounts Payables (Excel report)
description: Analyze vendor balances at the end of each period. Helps ensure the reliability of what you owe your vendors.
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

The **Aged Accounts Payables Excel** report shows aggregated aging data based on vendor ledger entries.

The data is aggregated and bucketed according to the **Aged as of** and **Period length** parameters in the report's request page.

The aggregated data is summarized for the two global dimensions.

The report Excel workbook contains four worksheets that you can use to analyze your aged accounts payable:

- By period (LCY)
- By Period (FCY)
- Due by Currencies
- CustomerAgingData

Each worksheet represents a different dimension for your analysis.

[!INCLUDE [onedrive-excel-online](../includes/onedrive-excel-online.md)] 


> [!NOTE]
> This report does the calculations when you view it in Excel online or download and open it on your computer. If a banner displays text about external data connections, you might need to choose the **Enable content** button to load data. The report doesn't connect to any external data sources. All calculations are done in Excel with Power Query. In some cases (depending on the security configurations for your organization), you might also need to right-click on a pivot table in one of the worksheets and choose **Refresh** to update data in the reports.

## By period (LCY) worksheet

This worksheet shows amounts in local currency (LCY) by vendor, and you can group data by a Year-Quarter-Month-Day hierarchy on the due date.

The filters and slicers let you zoom in on a single vendor or a group of vendors.

:::image type="content" source="../media/excel-aged-accounts-payable-by-period-LCY.png" alt-text="Screenshot of the By period (LCY) worksheet":::

## By Period (FCY) worksheet

This worksheet shows amounts in foreign currency (FCY) by vendor, and you can group data by a Year-Quarter-Month-Day hierarchy on the due date.

The filters and slicers let you zoom in on a vendor or a group of vendors. You can also filter by one or more currency codes, if needed.

:::image type="content" source="../media/excel-aged-accounts-payable-by-period-FCY.png" alt-text="Screenshot of the By period (FCY) worksheet":::

## Due by Currencies worksheet

This worksheet shows amounts by currency code, and you can group data by a Year-Quarter-Month-Day hierarchy on the due date.

The filters and slicers let you zoom in on a vendor or a group of vendors. You can also filter by one or more currency codes, if needed.

:::image type="content" source="../media/excel-aged-accounts-payable-due-by-currencies.png" alt-text="Screenshot of the Due by Currencies worksheet":::

## VendorAgingData worksheet

This worksheet shows the raw data used in the report.

You can use this worksheet for data analysis assisted by built-in tools in Excel, such as [!INCLUDE [excel-copilot-name](../includes/excel-copilot-name.md)] or the What-if-analysis or Forecast Sheet tools.

:::image type="content" source="../media/excel-aged-accounts-payable-vendor-aging-data.png" alt-text="Screenshot of the VendorAgingData worksheet":::


To learn more, go to [Get started with Copilot in Excel](https://support.microsoft.com/en-us/office/get-started-with-copilot-in-excel-d7110502-0334-4b4f-a175-a73abdfc118a).

## Use cases

[!INCLUDE [report-4403-scenario](../includes/report-4403-scenario-include.md)]

## Try the report

Try the report here: [Aged Accounts Payables Excel](https://businesscentral.dynamics.com?report=4403)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Alternative reports

There are several other ways to analyze aged accounts payable. To learn more, go to:

- [Aged Payables (Back Dating) in Power BI](../finance-powerbi-aged-payables-back-dating.md)
- [Using data analysis to analyze accounts payable](../ad-hoc-analysis-finance.md#example-finance-accounts-payable)

## Related information

[Accounts payable analytics](../receivables-reports.md)  
[Key finance report overview](../finance-reports.md)  
[Ad hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]