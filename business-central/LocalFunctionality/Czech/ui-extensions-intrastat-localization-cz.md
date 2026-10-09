---
title: Intrastat Localization for Czech (Extension)  
description: Companies in the European Union (EU) must report trade of goods with other EU countries or regions using Intrastat reporting or the VAT Information Exchange System (VIES).
author: bholtorf
ms.service: dynamics-365-business-central
ms.topic: article
ms.search.keywords: Czech, Intrastat, CZ
ms.date: 10/08/2026
ms.reviewer: bholtorf
ms.author: bholtorf
ai-usage: ai-assisted
---

# Czech Intrastat reporting

[!INCLUDE[intrastat-2022w2](../../includes/intrastat-2022w2.md)]

Dynamics 365 Business Central provides features that let you collect statistics on the trade in goods among EU member nations and prepare an Intrastat report file for submission. With the Intrastat CZ app, you can complete periodic Intrastat reporting to report trade of goods according to Czech local legislation. To use this app, you must first install the Intrastat Core app.

## Main features

- Setting up Intrastat reporting
- Setting up Items and Fixed Assets for Intrastat reporting
- Setting up Intrastat Checklist for validation Intrastat rules
- Setting up Data Exchange Definition to create Intrastat file exports
- Creating and Submitting Intrastat report file
- Submit Intrastat Report in accordance with Czech requirements

## Extension of settings for Intrastat CZ

- **Statistic Indication** - the code list is added to the Intrastat report lines and to the report export.
- **Intrastat Delivery Groups** - the code list is added to Delivery Methods, Intrastat report lines, and report export.
- **Item Charges** - the field **Incl. in Intrastat Amount** has been added to allow you to specify which charges should be included in the Intrastat amount. The application or non-application of the Intrastat charge amount can also be affected retrospectively for items already posted.
- For Intrastat purposes, the **Item Card** is extended with the **Specific Movement** and **Statistic Indication** fields.

## Intrastat reporting settings

The following fields are added to the Intrastat reporting settings:

- **No Item Charges in Intrastat** - specifies that no item charges are included in Intrastat amounts. You can't turn off this field while any item charge has **Incl. in Intrastat Amount** turned on.
- **Intrastat Rounding Type** - specifies the rounding type for calculating amounts when creating Intrastat reports and allows you to set the rounding to Up, Down, or Nearest.
- **Default Phys. Trans. - Returns** - specifies the default value of the Physical Movement field for sales returns, service returns, and purchase returns.
- **Minimum Tolerance from Fair Market Value (%)** - specifies the minimum percentage tolerance at which Business Central replaces the sales or purchase price from the item ledger entries with the fair market value entered on the item card when it generates Intrastat line suggestions.

> [!NOTE]
> Earlier versions of this app added Czech-specific fields for **Transaction Type Mandatory**, **Transaction Spec. Mandatory**, **Transport Method Mandatory**, and **Shipment Method Mandatory**. These settings are now part of the standard Intrastat core extension, so they're no longer Czech-specific fields.

## Using the Intrastat report

- The **Suggest Lines** action fills the Intrastat report lines, taking into account the application or non-application of the amount of item charges and the way the amounts are rounded.
- The **Checklist Report** performs standard checks on the Intrastat report, including added checks on the mandatory fields Transaction Type, Transaction Spec, Transport Method, and Shipment Method.
- **Create File** exports the Intrastat report. The export uses the **Data Exchange Definition** setting, which follows the current format of the CZ Intrastat report. You can edit the data exchange definition to change the data export.

## Related information

- [Czech local functionality](czech-local-functionality.md)
- [Set up Intrastat reporting](../../finance-how-setup-report-intrastat.md)
- [Work with Intrastat reporting](../../finance-how-report-intrastat.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
