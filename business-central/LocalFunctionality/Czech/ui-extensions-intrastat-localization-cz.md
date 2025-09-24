---
title: Intrastat Localization for Czech (Extension)  
description: Companies in the European Union (EU) must report trade of goods with other EU countries or regions using Intrastat reporting or the VAT Information Exchange System (VIES).
author: v-pejano
ms.service: dynamics-365-business-central
ms.topic: article
ms.search.keywords: Czech, Intrastat, CZ
ms.date: 06/09/2025
ms.reviewer: v-soumramani
ms.author: v-pejano
---

# Czech Intrastat reporting

[!INCLUDE[intrastat-2022w2](../../includes/intrastat-2022w2.md)]

Dynamics 365 Business Central provides features that allow you to collect statistics on the trade in goods among EU member nations and to prepare Intrastat report file for submitting. With Intrastat CZ app you can complete periodic Intrastat reporting to report trade of goods according to Czech local legislation. To use this app, you first must have installed Intrastat Core app.

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
- **Item Charges** - the field **Include in Intrastat amount** has been added to allow the user to specify which charges should be included in the Intrastat amount. The application or non-application of the Intrastat charge amount can also be affected retrospectively for items already posted.
- For Intrastat purposes, the **Item Card** is extended with the **Specific Movement** and **Statistic Indication** fields.

## Intrastat reporting settings

The following fields are added to the Intrastat reporting settings:

- **Intrastat Rounding Type** - specifies the rounding type for calculating amounts when creating Intrastat reports and allows you to set the rounding to Up, Down or Nearest.
- **Def. Phys. Trans. - Returns** - Specifies the default value of the Physical Movement field for sales and service returns and purchase returns.  
- **Transaction Type Mandatory** - Controls the value to be filled in when posting documents.
- **Transaction Spec. Mandatory** - checks the value to be filled in when posting documents.
- **Transport Method Mandatory** - checks the value to be filled in when posting documents.
- **Shipment Method Mandatory** - checks the value to be filled in when posting documents.

## Using the Intrastat report

- The **Suggest lines** function fills the Intrastat report lines taking into account the application or non-application of the amount of Item Charges and the way the amounts are rounded.
- The **Checklist Report** performs standard checks on the Intrastat report including added checks on the mandatory fields Transaction Type, Transaction Spec, Transport Method, and Shipment Method.
- **Create File** exports the Intrastat report. The export of the report uses the **Data Exchange Definition** setting, which follows the current format of the CZ Intrastat report. The Data exchange definition allows user editing of the data export.

## Related information

- [Czech local Functionality](czech-local-functionality.md)  
- [Set up Intrastat reporting](../../finance-how-setup-report-intrastat.md)  
- [Work with Intrastat reporting](../../finance-how-report-intrastat.md)  
