---
title: Upgrading an Integration with Dynamics 365 Sales| Microsoft Docs
description: Learn how to get Dynamics 365 Business Central ready to integrate with Dynamics 365 Sales.
services: project-madeira
documentationcenter: ''
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: sales, crm, integration, integrating
ms.date: 10/01/2019
ms.author: bholtorf

---
# Upgrading an Integration with Dynamics 365 Sales
[!INCLUDE[d365fin](includes/d365fin_md.md)] also integrates with [!INCLUDE[d365fin](includes/cds_long_md.md)], which makes it easy to connect and synchronize data with other Dynamics 365 applications, such as [!INCLUDE[crm_md](includes/crm_md.md)], or even apps that you build yourself. If you are integrating for the first time, we recommend that you do so through [!INCLUDE[d365fin](includes/cds_long_md.md)]. For more information, see [Integration with Common Data Service](admin-common-data-service.md).

If you have already integrated [!INCLUDE[crm_md](includes/crm_md.md)] with [!INCLUDE[d365fin](includes/d365fin_md.md)], you can continue to synchronize data using your setup. However, if you upgrade [!INCLUDE[d365fin](includes/d365fin_md.md)], or turn off your [!INCLUDE[crm_md](includes/crm_md.md)] integration, to turn it on again you must connect through [!INCLUDE[d365fin](includes/cds_long_md.md)]. 

> [!NOTE]
> Reconnecting through [!INCLUDE[d365fin](includes/cds_long_md.md)] will apply default synchronization settings, and will overwrite any configurations you have. For example, the default table mappings will be applied.

## To upgrade your connection to use Common Data Service
1. Open the **Microsoft Dynamics 365 Connection Setup** page, choose the **Enable** toggle to turn off your existing connection to [!INCLUDE[crm_md](includes/crm_md.md)].
2. Open the **Common Data Service Connection Setup** page, and choose the **Enable** toggle to turn on the connection.
3. After you enable the CDS connection, the Business Central CDS Base Integration Solution is deployed to Common Data Service.
4. On the Microsoft Dynamics 365 Connection Setup page, choose the Enable toggle to turn on the connection to [!INCLUDE[crm_md](includes/crm_md.md)].
5. After you enable the Sales connection, the Business Central Integration Solution is deployed to Sales. This enables integration with entities that are specific to [!INCLUDE[crm_md](includes/crm_md.md)], such as sales orders, quotes, and invoices.
6. On the **Sales Connection Setup** page, choose **Use Default Synchronization Setup** to initialize the integration table mappings for [!INCLUDE[crm_md](includes/crm_md.md)].
7. Now choose **Redeploy Integration Solution** to install and configure the upgraded Business Central Integration Solution.

## See Also
[Integrating with Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md)  
[Integrating with Common Data Service](admin-common-data-service.md)