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

The **Aged Accounts Payables Excel** report uses vendor ledger entries to aggregate and bucket data according to the Aged as of and Period length parameters in the report's request page. Data is summarized by the two global dimensions.

The report Excel workbook contains four worksheets that you can use to analyze your aged accounts payable:

- By period (LCY)
- By Period (FCY)
- Due by Currencies
- CustomerAgingData

[!INCLUDE [excel-reports-use-the-worksheets](../includes/excel-reports-use-the-worksheets.md)]

[!INCLUDE [onedrive-excel-online](../includes/onedrive-excel-online.md)]

[!INCLUDE [excel-reports-enable-content-note](../includes/excel-reports-enable-content-note.md)]

## By period (LCY) worksheet

This worksheet shows amounts in local currency (LCY) by vendor, and you can group data by a Year-Quarter-Month-Day hierarchy on the due date.

The filters and slicers let you zoom in on a single vendor or a group of vendors.

:::image type="content" source="../media/excel-aged-accounts-payable-by-period-LCY.png" alt-text="Screenshot of the By period (LCY) worksheet":::

[!INCLUDE [excel-pivottable-tip](../includes/excel-pivottable-tip.md)]

## By Period (FCY) worksheet

This worksheet shows amounts in foreign currency (FCY) by vendor, and you can group data by a Year-Quarter-Month-Day hierarchy on the due date.

The filters and slicers let you zoom in on a vendor or a group of vendors. You can also filter by one or more currency codes, if needed.

:::image type="content" source="../media/excel-aged-accounts-payable-by-period-FCY.png" alt-text="Screenshot of the By period (FCY) worksheet":::

[!INCLUDE [excel-pivottable-tip](../includes/excel-pivottable-tip.md)]

## Due by Currencies worksheet

This worksheet shows amounts by currency code, and you can group data by a Year-Quarter-Month-Day hierarchy on the due date.

The filters and slicers let you zoom in on a vendor or a group of vendors. You can also filter by one or more currency codes, if needed.

:::image type="content" source="../media/excel-aged-accounts-payable-due-by-currencies.png" alt-text="Screenshot of the Due by Currencies worksheet":::

[!INCLUDE [excel-pivottable-tip](../includes/excel-pivottable-tip.md)]

## VendorAgingData worksheet

[!INCLUDE [excel-reports-data-worksheet](../includes/excel-reports-data-worksheet.md)]

:::image type="content" source="../media/excel-aged-accounts-payable-vendor-aging-data.png" alt-text="Screenshot of the VendorAgingData worksheet":::

[!INCLUDE [excel-reports-get-started-with-copilot-excel](../includes/excel-reports-get-started-with-copilot-excel.md)]

## Other worksheets

[!INCLUDE [excel-reports-other-worksheets](../includes/excel-reports-other-worksheets.md)]

## Use cases

[!INCLUDE [report-4403-scenario](../includes/report-4403-scenario-include.md)]

## Try the report

Try the report here: [Aged Accounts Payables Excel](https://businesscentral.dynamics.com?report=4403)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Make the report your own

[!INCLUDE [excel-reports-make-it-your-own](../includes/excel-reports-make-it-your-own.md)]

## Alternative reports

There are several other ways to analyze aged accounts payable. To learn more, go to:

- [Aged Payables (Back Dating) in Power BI](../finance-powerbi-aged-payables-back-dating.md)
- [Using data analysis to analyze accounts payable](../ad-hoc-analysis-finance.md#example-finance-accounts-payable)

## Contributors

[!INCLUDE [contributor_credit](../includes/contributor_credit.md)]

- [Kim Dallefeld](https://www.linkedin.com/in/kim-dallefeld/) | Microsoft MVP

## Related information

[Accounts payable analytics](../receivables-reports.md)  
[Key finance report overview](../finance-reports.md)  
[Ad hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]