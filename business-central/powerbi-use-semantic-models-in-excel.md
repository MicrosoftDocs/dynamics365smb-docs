---
title: Use Power BI Semantic Models in Excel for Dynamics 365 Business Central Reporting
description: Describes how to utilize connections Power BI semantic models in Excel for Business Central reporting.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: overview
ms.service: dynamics-365-business-central
ms.search.keywords: trial, Microsoft services
ms.date: 11/12/2025
ms.custom: bap-template
---

# Use Power BI semantic models in Excel for Dynamics 365 Business Central reporting

In Excel Desktop or Excel for the web, you can connect your Power BI semantic models for Dynamics 365 Business Central as a data source to build powerful reports about the state of your business. Perform ad-hoc analysis across functional areas, create refreshable reports, and take advantage of the versatility of Excel to make data-driven business decisions.

This article describes how to create Pivot Tables and Tables connected to Power BI Semantic Models from the Power BI apps for Dynamics 365 Business Central.

## Getting Started

The following table includes links to help you get started with connecting to Power BI semantic models and use the data.

| To | See |
| --- | ----------------|
| Access Power BI semantic models in Excel | [Connect Excel to Power BI semantic models](/power-bi/collaborate-share/service-connect-power-bi-datasets-excel)| 
| Create visuals in Excel using Power BI semantic models | [Discover Power BI semantic models in Excel](/power-bi/collaborate-share/service-connect-excel-power-bi-datasets#discover-power-bi-semantic-models-in-excel)| 

## Example: Create a Table

This example uses the [Inventory Power BI app for Business Central](./inventory-powerbi-app.md) semantic model to illustrate a Table that could be built to report on outbound Lots.

On the **Data** tab in Excel Desktop, select **Get Data** > **Power Platform** > **From Power BI**.

:::image type="content" source="media\powerbi\excel\excel-power-bi-semantic-model-connection.png" alt-text="Screenshot of Excel showing steps to connect to Power BI." lightbox="media\powerbi\excel\excel-power-bi-semantic-model-connection.png":::

After you select **From Power BI** using either of these options, a pane opens on the right of the screen that shows Power BI semantic models you have access to. Select **Insert Table** for the [Inventory app](./inventory-powerbi-app.md) semantic model.

:::image type="content" source="media\powerbi\excel\excel-power-bi-semantic-model-new-table.png" alt-text="Screenshot of Excel showing Power BI semantic models pane highlighting Create Table option." lightbox="media\powerbi\excel\excel-power-bi-semantic-model-new-table.png":::

When you select **Insert Table**, the **Create Table** dialog opens, where you can use the **Data**, **Build**, and **Filters** panes to design the table you'd like. The predefined relationships in the semantic model allow fields from different tables to be combined into one table.

For this example:

1. Add the following fields to values section of the **Build** pane:
    * Sales Line table - Shipment Date
    * Item table - Item No.
    * Item table - Item Description
    * Lot No. table - Lot No.
    * Customer table - Customer No.
    * Customer table - Customer Name
    * Measure - Quantity
2. In the **Filters** pane, filter for:
    * Item Ledger Entrt table Entry Type = Sale
    * Lot No. table Lot No. does not equal blank

To add the table to the Excel sheet, use the **Insert Table** action in the dialog.

:::image type="content" source="media\powerbi\excel\excel-power-bi-semantic-model-create-table-wizard.png" alt-text="Screenshot of Excel showing Power BI semantic model Create Table wizard." lightbox="media\powerbi\excel\excel-power-bi-semantic-model-create-table-wizard.png":::

The resulting table can be interacted with, for example, to filter for a specific customer to determine which lots recently shipped.

:::image type="content" source="media\powerbi\excel\excel-power-bi-semantic-model-inventory-table-example.png" alt-text="Screenshot of Excel showing table created from Power BI semantic model connection." lightbox="media\powerbi\excel\excel-power-bi-semantic-model-inventory-table-example.png":::

## Example: Create a Pivot Table

This example uses the [Inventory Valuation Power BI app for Business Central](./inventory-valuation-powerbi-app.md) semantic model to illustrate a Pivot Table that could be built to analyze inventory valuation by date.

On the **Data** tab in Excel Desktop, select **Get Data** > **Power Platform** > **From Power BI**.

:::image type="content" source="media\powerbi\excel\excel-power-bi-semantic-model-connection.png" alt-text="Screenshot of Excel showing steps to connect to Power BI." lightbox="media\powerbi\excel\excel-power-bi-semantic-model-connection.png":::

After you select From Power BI using either of these options, a pane opens on the right of the screen that shows Power BI semantic models you have access to. Select **Insert Pivot Table** for the [Inventory Valuation app](./inventory-valuation-powerbi-app.md) semantic model.

:::image type="content" source="media\powerbi\excel\excel-power-bi-semantic-model-new-pivot-table.png" alt-text="Screenshot of Excel showing Power BI semantic models pane highlighting Create Pivot Table option." lightbox="media\powerbi\excel\excel-power-bi-semantic-model-new-pivot-table.png":::

Alternatively, on the **Insert** tab in Excel, select **PivotTable** > **From Power BI**.

:::image type="content" source="media\powerbi\excel\excel-power-bi-semantic-model-insert-pivot-table.png" alt-text="Screenshot of Excel showing steps create Pivot Table using Power BI connection." lightbox="media\powerbi\excel\excel-power-bi-semantic-model-insert-pivot-table.png":::

When you select **Insert Pivot Table**, the **Pivot Table Field List** pane opens in a new sheet. Drag fields to the **Filters**, **Rows**, **Columns**, and **Values** sections to design the Pivot Table you'd like.

For this example, add the following fields to various sections of the **Fields** pane:

1. Add the following fields to the **Filters** section:
    * Date table - Fiscal Year
    * Date table - Fiscal Month
2. Add the following fields to the **Rows** section:
    * Measure - Valuation Date
    * Item table - Item No. & Description
3. Add the following field to the **Values** section:
    * Measure - Increases Qty.
    * Measure - Increases Value.
    * Measure - Decrease Qty.
    * Measure - Decrease Value.
    * Measure - Cost Amount (Expected)
    * Measure - Cost Amount (Actual).

:::image type="content" source="media\powerbi\excel\excel-power-bi-semantic-model-inv-val-pivot-table-example.png" alt-text="Screenshot of Excel showing Pivot Table created with connection to Power BI." lightbox="media\powerbi\excel\excel-power-bi-semantic-model-inv-val-pivot-table-example.png":::

The resulting Pivot Table could be used to review activity on a date where a discrepancy has been identified between the standard [Inventory Valuation Report](./reports/report-1001.md) and the inventory control accounts in the general ledger.

## Example: Combining models with Power Pivot Excel add-in

This example uses the [Inventory Power BI app for Business Central](./inventory-powerbi-app.md) and the [Sales Power BI app for Business Central](./sales-powerbi-app.md) semantic models to illustrate how to use the [Power Pivot for Excel add-in](https://support.microsoft.com/office/power-pivot-overview-and-learning-f9001958-7901-4caa-ad80-028a6d2432ed) to combine tables from multiple models into one Pivot Table.

Follow the steps from [Example: Create a Table](#example-create-a-table) with the Inventory app model, including the following fields:

* Item table - Item No.
* Item table - Item Description
* Item Table - Item Replenishment System

Follow the steps from [Example: Create a Table](#example-create-a-table) with the Sales app model, including the following fields:

* Item table - Item No.
* Salesperson Table - Salesperson Name
* Sales table - Document Type

Go to **Data** > **Data Tools** > **Data Model** > **Relationships**.

:::image type="content" source="media\powerbi\excel\excel-data-model-relationships.png" alt-text="Screenshot of Excel showing steps to create a Power Pivot relationship between Tables." lightbox="media\powerbi\excel\excel-data-model-relationships.png":::

Define a relationship between the Sales & Inventory tables created in previous steps, based on the **Item No.** field.

:::image type="content" source="media\powerbi\excel\excel-manage-relationships-power-pivot.png" alt-text="Screenshot of Excel showing wizard to create relationship between Tables for Power Pivot." lightbox="media\powerbi\excel\excel-manage-relationships-power-pivot.png":::

To open the Power Pivot model, choose to **Data** > **Data Tools** > **Data Model** > **Manage Data Model**.

:::image type="content" source="media\powerbi\excel\excel-manage-data-model.png" alt-text="Screenshot of Excel showing steps to Manage Data Model in Power Pivot. " lightbox="media\powerbi\excel\excel-manage-data-model.png":::

Review the created relationship in the Modelling view of Power Pivot. Create a Pivot Table to utilise the connection between the two tables.

:::image type="content" source="media\powerbi\excel\excel-create-pivot-from-power-pivot.png" alt-text="Screenshot of Excel showing steps to create Pivot Table from Power Pivot." lightbox="media\powerbi\excel\excel-create-pivot-from-power-pivot.png":::

For this example counting Item Sales for a Salesperson by Item Replenishment System:

1. Add the following fields to the **Rows** section of the **Fields** pane:
    * Salesperson table - Salesperson Name
    * Item table - Item Replenishment System
2. Add the following field to the **Values** section of the **Fields** pane:
    * Item table - Item No.

:::image type="content" source="media\powerbi\excel\excel-power-bi-semantic-model-combined-model-pivot-table-example.png" alt-text="Screenshot of Excel showing Pivot Table created from Power Pivot." lightbox="media\powerbi\excel\excel-power-bi-semantic-model-combined-model-pivot-table-example.png":::

The resulting Pivot Table shows how we can connect Power BI semantic models within Excel to perform cross-functional reporting.

## Related information

[Install [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps for [!INCLUDE [prod_short](includes/prod_short.md)]](across-powerbi-install-business-central-apps.md)  
[Power BI apps/reports for functional areas](across-powerbi-apps-by-functional-area.md)  
[Frequently asked questions about the Power BI apps in Business Central](across-powerbi-apps-faq.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
