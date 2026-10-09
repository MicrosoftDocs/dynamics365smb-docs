---
title: Requirements for Reporting Declaration of Trade in Goods [FR]
description: Learn about the required fields and steps for reporting the Declaration of Trade in Goods (DEB) in the French version of Business Central.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: declaration of trade, DEB report, trade in goods, declaration reporting requirements, validate intrastat lines, intrastat, French version
ms.date: 10/08/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Requirements for reporting declaration of trade in goods in the French version

[!INCLUDE[intrastat-2022w2](../../includes/intrastat-2022w2.md)]

In this article, we describe how you can set up [!INCLUDE [prod_short](../../includes/prod_short.md)] for reporting the Declaration of Trade in Goods (DEB) report in France.

The following fields are required for reporting DEB:

- **CISD** from the **Company Information** table.
- **Registration No.** from the **Company Information** table.
- **VAT Registration No.** from the **Company Information** table.
- **Name** from the **Company Information** table.
- **Statistics Period** from the **Intrastat Report** header.
- **Transaction Specification** from the **Intrastat Report Line** table.
- **Quantity** from the **Intrastat Report Line** table must be greater than 0.
- **Statistical Value** from the **Intrastat Report Line** table must be greater than 0.

> [!NOTE]
> The **Create File** action on the **Intrastat Report** page exports shipments and receipts in one batch, unless you've set up separate files for receipts and shipments on the **Intrastat Report Setup** page. If you want to report only shipments or receipts, filter the lines that you don't want to export before you run **Create File**.

## Intrastat requirements for DEB

For France, Intrastat management requires that you separate the declaration data for statistical reporting and fiscal reporting (the VAT recapitulative statement). You must export separate files based on the configured obligation level.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Report List**, and then select the related link.
1. Choose **New** to create a new Intrastat report, or select an existing report, and then open it.
1. Choose the **Suggest Lines** action to create lines for the selected period.
1. On the **Intrastat Report** page, in the **Obligation Level** field, select the obligation level that you want to report.

   Setting the **Obligation Level** field automatically sets the **Transaction Specification Filter** field with a predefined value. This value is a filter that's applied to the **Transaction Specification** field on the Intrastat report lines, so that only lines with a matching value are processed when you create the file.

The **Transaction Specification Filter** field is editable, so you can change its value if needed. The following table outlines the currently supported values:

| Level | Filter |
|--|--|
| **Obligation Level 1** | `11\|19\|21\|29` |
| **Obligation Level 2** | *(blank, so that all Intrastat report lines are processed)* |
| **Obligation Level 3** | *(blank)* |
| **Obligation Level 4** | `<>29&<>11&<>19` (lines with transaction specification 29, 11, or 19 aren't processed) |
| **Obligation Level 5** | `<>11&<>19` |

On the report lines, fill in the necessary fields, and then choose the **Create File** action to generate the XML file for the selected obligation level.

## Validate Intrastat lines

Run the **Checklist Report** action on the **Intrastat Report** page to check the Intrastat report lines before you export them to XML. For France, the checklist always validates the **Tariff No.**, **Country/Region Code**, and **Transaction Type** fields, and conditionally validates the **Quantity**, **Total Weight**, **Country/Region of Origin Code**, and **Partner VAT ID** fields depending on whether supplementary units are used and whether the line is a shipment.

### Set up the checklist

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Report Setup**, and then choose the related link.
1. Select the **Intrastat Report Checklist** action.
1. Add the necessary lines. Set the **Field No.** field to a field that must be checked for a non-empty value, and fill in the **Filter Expression** field if needed.

## Related information

[Set up Intrastat reporting](../../finance-how-setup-report-intrastat.md)
[France local functionality](france-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
