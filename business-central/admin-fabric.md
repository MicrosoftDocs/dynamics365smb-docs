---
title: Data Mirroring to Microsoft Fabric from Business Central
description: Learn how Business Central mirrors selected company data to Microsoft Fabric for analytics, engineering, and business intelligence scenarios.
author: kennienp
ms.topic: overview
ms.search.keywords: analytics, reporting, business intelligence, Fabric, OneLake, open mirroring, data mirroring, replication, synchronization
ms.search.form: Primary_48511, 48519
ms.reviewer: bholtorf
ms.date: 10/08/2026
ms.author: kepontop
ms.custom: bap-template
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---
# Data mirroring to Microsoft Fabric from Business Central

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Data mirroring connects [!INCLUDE[prod_short](includes/prod_short.md)] online to an open mirrored database in [!INCLUDE[microsoft_fabric](includes/microsoft_fabric.md)]. You select the companies and tables to synchronize. Business Central then replicates an initial snapshot and ongoing changes into OneLake.

<!--[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]-->

> [!IMPORTANT]
> - This feature is planned to become available as a production-ready preview in October 2026. Delivery timing and functionality might change.
> - Production-ready previews are subject to [supplemental terms of use](https://go.microsoft.com/fwlink/?linkid=2189520).

In Fabric, Business Central data is stored in OneLake in Delta Parquet format. Fabric IQ, Power BI, Data Factory, and other analytics experiences can use the synchronized data without repeatedly reading it from Business Central APIs.

## Choose when to use data mirroring

Use data mirroring when your organization wants a managed way to make Business Central data available in Fabric for analytics and data engineering. The integration supports:

- Multiple Business Central companies.
- Up to 1,000 selected tables. Learn more in [Limitations in Microsoft Fabric mirrored databases from Azure SQL Database](/fabric/mirroring/azure-sql-database-limitations).
- Initial snapshot and incremental synchronization.
- A Microsoft configuration package with a curated set of standard tables.
- Synchronization monitoring in Business Central, through APIs, and from Fabric.

Learn more about choosing an extraction method in [Extract data from Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-extract-data).

## Understand the mirroring flow

An administrator completes the following high-level tasks:

1. Creates an open mirrored database in a Fabric workspace.
1. Connects Business Central to the workspace and database.
1. Grants the service principal access to the mirroring database.
1. Selects the Business Central companies and tables to synchronize.
1. Starts synchronization and monitors each run.

The setup and synchronization operations run asynchronously. Business Central records an overview for each run and details for each company and table.

## Get started

| Task | Learn more |
| --- | --- |
| Prepare Fabric and connect Business Central | [Set up data mirroring from Business Central to Microsoft Fabric](admin-set-up-fabric-mirroring.md) |
| Select companies and tables, use configuration packages, and control synchronization | [Manage Business Central data synchronization with Fabric](admin-manage-fabric-export.md) |
| Check synchronization runs and resolve common problems | [Monitor and troubleshoot Fabric synchronization](admin-monitor-fabric-export.md) |
| Monitor or manage the integration through APIs | [Microsoft Fabric Export APIs](/dynamics365/business-central/dev-itpro/developer/devenv-fabric-export-apis) |

## Power BI apps and Fabric

Microsoft plans to provide versions of the standard Business Central Power BI apps that use data in Fabric. The planned apps include single-company and multicompany versions. Availability can change during the preview.

## Related information

- [Analyze data in business intelligence tools](reports-external-analysis.md)
- [Using Power BI with Business Central](admin-powerbi.md)
- [Extract data from Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-extract-data)
- [Microsoft Fabric documentation](/fabric/)

[!INCLUDE[footer-include](includes/footer-banner.md)]
