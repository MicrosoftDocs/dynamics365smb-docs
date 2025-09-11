---
title: Sustainability reports and analytics
description: Explore the sustainability reports and analytics in the standard version of Business Central.
author: brentholtorf
ms.topic: article
ms.search.keywords: reporting
ms.search.form: Report_6210, Report_6211, Report_6212
ms.date: 08/27/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Sustainability reports and analytics in Business Central

Sustainability reporting gives finance professionals insights and statistics about current and past sustainability investments and emissions.  

## Reports

[!INCLUDE [sustainability_reports](includes/sustainability-reports-include.md)]

## Tasks

The following articles describe some of the key tasks for analyzing the state of your sustainability efforts:

* [Calculate Emission based on General Ledger](finance-sustainability-journal.md)
* [Track items that you know have high emission levels](#track-items-that-you-know-have-high-emission-levels)

## Explore sustainability reports with Report Explorer

To get an overview of the reports that are available for sustainability, choose **All Reports** on your Home page. This action opens the Role Explorer, which is filtered to the features in the **Report & Analysis** option. Under the **TODO** heading, choose **Explore**.

<!--There isn't an image file for this.

:::image type="content" source="media/report-explorer-sustainability.png" alt-text="Example of sustainability reports on the finance role center." lightbox="media/report-explorer-sustainability.png":::-->

To learn more, go to [Finding Reports with the Role Explorer](ui-role-explorer.md).

## Track items that you know have high emission levels

You can efficiently track items with high emissions to comply with environmental regulations and support your sustainability efforts. When you monitor inbound and outbound transactions and their pollution, you can make informed decisions that reduce your carbon footprint.

On the **Item Card** page, you can track items of concern by using the **Item of Concern** field on the **Sustainability** FastTab. This field tracks items by their emissions level and lets you specifically target significant polluters. When you select this field, you must enter a value in at least one of the following fields:

* **Default CO2 Emission**
* **Default CH4 Emission**
* **Default N2O Emission**

To track all inbound transactions, such as purchases and production output, and outbound transactions, such as sales and consumption for these items, use the **Track Item of Concern** report. The report provides detailed information grouped by inbound and outbound transactions, and it shows total emissions for CO2e, CO2, CH4, and N2O. To run the report, [!INCLUDE [open-search-lowercase](includes/open-search-lowercase.md)], enter **Track Item of Concern**, and then fill in the fields as necessary.

## Related information

[Ad-hoc analysis of sustainability data](ad-hoc-analysis-sustainability.md)  
[Sustainability management overview](finance-manage-sustainability.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
