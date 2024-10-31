---
title: Gross Requirement (Power BI report)
description: The Gross Requirement report looks at all outbound transactions within the system to identify the quantity required per item. 
author: shaungibsonn
ms.author: 
ms.reviewer: 
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: 37027_Primary
ms.date: 10/28/2024
ms.service: dynamics-365-business-central
---

# Gross Requirement (Power BI Report)
[!INCLUDE[applies-to-2024w2](../includes/applies-to-2024w2.md)]


The *Gross Requirement* report looks at all outbound transactions within the system to identify the quantity required per item. 

The *Gross Requirement* reports shows a view of the Gross Requirement for an item along with the inventory across the different documents. This is coupled with the Project Available Balance which calculates the balance at any point in time. 

:::image type="content" source="../media/inventory/gross-requirement.png" alt-text="Screenshot of the Gross Requirement Power BI Report" lightbox="../media/inventory/gross-requirement.png":::

## How to use the report

The *Gross Requirement* is meant for management and procurement officers to be able to identify if the organization is keeping up with the demand.

As a manager, you can use the *Gross Requirement* report to ensure that you are keeping stock levels high enough to maintain the production schedule and sales demand for each item. The report can aid in identify impending bottle necks in production by highlighting items where the available balance will not meet the gross requirement. 

As a procurement officer, this report allows you to see Sales and Production volumes and ensure your available balance is enough to sustain the requirements for each item. With this, you can make informed decisions on what items need more inventory.

## Key Performance Indicators (KPIs)

The *Gross Requirement* report includes the following KPIs:

- [**Gross Requirement**](####)
- [**Project Available Balance**](####)
- [**Qty. on Sales Order**](####)
- [**Qty. on Purch. Return**](####)
- [**Qty. on Service Order**](####)
- [**Qty. on Projects**](####)
- [**Qty. on Prod. Order Comp Lines**](####)
- [**Trans. Order Shipment (Qty)**](####)
- [**Planning Issues (Qty)**](###)
- [**Qty. on Asm. Component**](###)

Click on the link for a KPI to learn more about what it means, how it is calculated, and what data was used in the calculations. 

[!INCLUDE[powerbi-tip-track-kpis](../includes/powerbi-tip-track-kpis.md)]

## Data used in the report

Data from the following tables are used on the *Gross Requirement* report
- Item
- Item Ledger Entries
- Assembly Lines
- Job Planning Lines
- Prod Order Component Line
- Production Order Lines
- Purchase Lines
- Sales Lines
- Service Lines
- Transfer Lines


## Try the report

Try the report here: [Gross Requirement](https://businesscentral.dynamics.com?page=37027)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## See also