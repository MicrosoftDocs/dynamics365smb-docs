---
title: Use Business Central Power BI Semantic Models in Excel
description: Connect Excel to Business Central Power BI semantic models to create refreshable tables and PivotTables, and combine data with Power Pivot.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: how-to
ms.service: dynamics-365-business-central
ms.search.keywords: trial, Microsoft services
ms.date: 11/11/2026
ms.custom: bap-template
ai-usage: ai-assisted
---

# Use Power BI semantic models in Excel for Dynamics 365 Business Central reporting

In Excel Desktop or Excel for the web, you can connect your Power BI semantic models for Dynamics 365 Business Central as a data source to build powerful reports about the state of your business. Perform ad-hoc analysis across functional areas, create refreshable reports, and take advantage of the versatility of Excel to make data-driven business decisions.

This article describes how to create Pivot Tables and Tables connected to Power BI Semantic Models from the Power BI apps for Dynamics 365 Business Central.

## Connect Excel to your semantic models

Your Power BI administrator must enable **Users can work with Power BI semantic models in Excel using a live connection**. You need **Build** permission on the semantic model, or a workspace role of **Contributor** or higher, and a Power BI license. Free-license users can work with models in **My workspace** or in Premium capacity or Fabric F64 or larger capacity.

The connected-table and Power Pivot examples use Excel Desktop for Windows. **Insert Table** isn't available in Excel for the web. Learn more in [Connect Excel to Power BI semantic models](/power-bi/collaborate-share/service-connect-power-bi-datasets-excel).

The following table includes links to help you get started with connecting to Power BI semantic models and use the data.

| To | See |
| --- | ----------------|
| Access Power BI semantic models in Excel | [Connect Excel to Power BI semantic models](/power-bi/collaborate-share/service-connect-power-bi-datasets-excel)| 
| Create visuals in Excel using Power BI semantic models | [Discover Power BI semantic models in Excel](/power-bi/collaborate-share/service-connect-excel-power-bi-datasets#discover-power-bi-semantic-models-in-excel)| 

## Example: Create a connected table

This example uses the [Inventory Power BI app for Business Central](./inventory-powerbi-app.md) semantic model to illustrate a Table that could be built to report on outbound Lots.

On the **Data** tab in Excel Desktop, select **Get Data** > **Power Platform** > **From Power BI**.

:::image type="content" source="media/powerbi/excel/excel-power-bi-semantic-model-connection.png" alt-text="Screenshot of Excel showing steps to connect to Power BI." lightbox="media/powerbi/excel/excel-power-bi-semantic-model-connection.png":::

After you select **From Power BI**, a pane opens on the right of the screen that shows Power BI semantic models you have access to. Select **Insert Table** for the [Inventory app](./inventory-powerbi-app.md) semantic model.

:::image type="content" source="media/powerbi/excel/excel-power-bi-semantic-model-new-table.png" alt-text="Screenshot of Excel showing Power BI semantic models pane highlighting the Insert Table option." lightbox="media/powerbi/excel/excel-power-bi-semantic-model-new-table.png":::

When you select **Insert Table**, the **Create Table** dialog opens, where you can use the **Data**, **Build**, and **Filters** panes to design the table you'd like. The predefined relationships in the semantic model allow fields from different tables to be combined into one table.

For this example:

1. Add the following fields to values section of the **Build** pane:
    * Item Ledger Entries table - Posting Date
    * Item table - Item No.
    * Item table - Item Description
    * Lot No table - Lot No.
    * Customer table - Customer No.
    * Customer table - Customer Name
    * Measure - Quantity
1. In the **Filters** pane, set filters for:
    * Item Ledger Entries table - Entry Type = Sale
    * Lot No table - Lot No. does not equal blank

Use **Item Ledger Entries** > **Posting Date** for the posted quantities in this example. **Sales Lines** > **Shipment Date** describes sales lines, not the posting date of the item ledger entries. The following screenshots show an earlier field selection.

To add the table to the Excel sheet, use the **Insert Table** action in the dialog.

:::image type="content" source="media/powerbi/excel/excel-power-bi-semantic-model-create-table-wizard.png" alt-text="Screenshot of Excel showing Power BI semantic model Create Table wizard." lightbox="media/powerbi/excel/excel-power-bi-semantic-model-create-table-wizard.png":::

The resulting table can be interacted with, for example, to filter for a specific customer to determine which lots recently shipped.

:::image type="content" source="media/powerbi/excel/excel-power-bi-semantic-model-inventory-table-example.png" alt-text="Screenshot of Excel showing table created from Power BI semantic model connection." lightbox="media/powerbi/excel/excel-power-bi-semantic-model-inventory-table-example.png":::

## Example: Create a connected PivotTable

This example uses the [Inventory Valuation Power BI app for Business Central](./inventory-valuation-powerbi-app.md) semantic model to illustrate a Pivot Table that could be built to analyze inventory valuation by date.

On the **Data** tab in Excel Desktop, select **Get Data** > **Power Platform** > **From Power BI**.

:::image type="content" source="media/powerbi/excel/excel-power-bi-semantic-model-connection.png" alt-text="Screenshot of Excel showing steps to connect to Power BI." lightbox="media/powerbi/excel/excel-power-bi-semantic-model-connection.png":::

After you select **From Power BI**, a pane opens on the right of the screen that shows Power BI semantic models you can access. Select **Insert PivotTable** for the [Inventory Valuation app](./inventory-valuation-powerbi-app.md) semantic model.

:::image type="content" source="media/powerbi/excel/excel-power-bi-semantic-model-new-pivot-table.png" alt-text="Screenshot of Excel showing Power BI semantic models pane highlighting Insert PivotTable." lightbox="media/powerbi/excel/excel-power-bi-semantic-model-new-pivot-table.png":::

Alternatively, on the **Insert** tab in Excel, select **PivotTable** > **From Power BI**.

:::image type="content" source="media/powerbi/excel/excel-power-bi-semantic-model-insert-pivot-table.png" alt-text="Screenshot of Excel showing steps create Pivot Table using Power BI connection." lightbox="media/powerbi/excel/excel-power-bi-semantic-model-insert-pivot-table.png":::

When you select **Insert PivotTable**, a PivotTable opens in a new sheet. Use the **PivotTable Fields** pane to drag fields to the **Filters**, **Rows**, **Columns**, and **Values** sections to design the PivotTable you want.

For this example, add the following fields to various sections of the **Fields** pane:

1. Add the following fields to the **Filters** section:
    * Date table - Fiscal Year
    * Date table - Fiscal Month
1. Add the following fields to the **Rows** section:
    * Value Entries table - Valuation Date
    * Item table - Item No. & Description
1. Add the following fields to the **Values** section:
    * Measure - Increases Qty.
    * Measure - Increases Value
    * Measure - Decrease Qty.
    * Measure - Decrease Value
    * Measure - Cost Amount (Expected)
    * Measure - Cost Amount (Actual)

:::image type="content" source="media/powerbi/excel/excel-power-bi-semantic-model-inv-val-pivot-table-example.png" alt-text="Screenshot of Excel showing Pivot Table created with connection to Power BI." lightbox="media/powerbi/excel/excel-power-bi-semantic-model-inv-val-pivot-table-example.png":::

The resulting Pivot Table could be used to review activity on a date where a discrepancy has been identified between the standard [Inventory Valuation Report](./reports/report-1001.md) and the inventory control accounts in the general ledger.

## Example: Combine models with the Power Pivot Excel add-in

This example uses the [Inventory Power BI app for Business Central](./inventory-powerbi-app.md) and the [Sales Power BI app for Business Central](./sales-powerbi-app.md) semantic models to illustrate how to use the [Power Pivot for Excel add-in](https://support.microsoft.com/office/power-pivot-overview-and-learning-f9001958-7901-4caa-ad80-028a6d2432ed) to combine tables from multiple models into one Pivot Table.

Follow the steps from [Example: Create a connected table](#example-create-a-connected-table) with the Inventory app model, including the following fields:

* Item table - Item No.
* Item table - Item Description
* Item Table - Item Replenishment System

Follow the steps from [Example: Create a connected table](#example-create-a-connected-table) with the Sales app model, including the following fields:

* Item table - Item No.
* Salesperson Table - Salesperson Name
* Documents table - Document Type
* Measure - Sales (LCY), to return combinations with sales data

Add both extracted Excel tables to the workbook's Data Model. Select a cell in each table, and then select **Power Pivot** > **Add to Data Model**. Learn more in [Add worksheet data to a Data Model using a linked table](https://support.microsoft.com/office/add-worksheet-data-to-a-data-model-using-a-linked-table-d3665fc3-99b0-479d-ba09-a37640f5be42).

Go to **Data** > **Data Tools** > **Data Model** > **Relationships**.

:::image type="content" source="media/powerbi/excel/excel-data-model-relationships.png" alt-text="Screenshot of Excel showing steps to create a Power Pivot relationship between Tables." lightbox="media/powerbi/excel/excel-data-model-relationships.png":::

Define a relationship based on **Item No.**. Set **Table** to the extracted Sales table and **Column (Foreign)** to its item number column. Set **Related Table** to the extracted Inventory table and **Related Column (Primary)** to its item number column. The Inventory table must contain one row per item number. Repeated item numbers are allowed on the Sales side, but not on the primary side. Learn more in [Create a relationship between two tables in Excel](https://support.microsoft.com/office/create-a-relationship-between-two-tables-in-excel-fe1b6be7-1d85-4add-a629-8a3848820be3).

To open the Power Pivot model, choose to **Data** > **Data Tools** > **Data Model** > **Manage Data Model**.

:::image type="content" source="media/powerbi/excel/excel-manage-data-model.png" alt-text="Screenshot of Excel showing steps to manage the Data Model in Power Pivot." lightbox="media/powerbi/excel/excel-manage-data-model.png":::

Review the created relationship in the Modelling view of Power Pivot. Create a Pivot Table to utilize the connection between the two tables.

:::image type="content" source="media/powerbi/excel/excel-create-pivot-from-power-pivot.png" alt-text="Screenshot of Excel showing steps to create Pivot Table from Power Pivot." lightbox="media/powerbi/excel/excel-create-pivot-from-power-pivot.png":::

For this example, count rows in the extracted Sales table by salesperson and item replenishment system:

1. Add the following fields to the **Rows** section of the **Fields** pane:
    * Salesperson table - Salesperson Name
    * Item table - Item Replenishment System
1. Add the item number field from the extracted Sales table to the **Values** section of the **Fields** pane, and summarize it by **Count**.

This count represents rows in the extracted table, not sales quantities or the number of sales transactions. Include the relevant sales measure in the extraction if you need those figures. The following screenshot shows field names from an earlier version of the model.

:::image type="content" source="media/powerbi/excel/excel-power-bi-semantic-model-combined-model-pivot-table-example.png" alt-text="Screenshot of Excel showing Pivot Table created from Power Pivot." lightbox="media/powerbi/excel/excel-power-bi-semantic-model-combined-model-pivot-table-example.png":::

The resulting Pivot Table shows how we can connect Power BI semantic models within Excel to perform cross-functional reporting.

## Related information

[Install [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps for [!INCLUDE [prod_short](includes/prod_short.md)]](across-powerbi-install-business-central-apps.md)  
[Power BI apps/reports for functional areas](across-powerbi-apps-by-functional-area.md)  
[Frequently asked questions about the Power BI apps in Business Central](across-powerbi-apps-faq.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
