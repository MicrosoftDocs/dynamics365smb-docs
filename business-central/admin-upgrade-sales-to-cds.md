---
title: Upgrading an Integration with Dynamics 365 Sales
description: This topic tells you how to move your Dynamics 365 Business Central integration with Dynamics 365 Sales to the latest version.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: sales, crm, integration, integrating
ms.date: 06/14/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Upgrading an Integration with Dynamics 365 Sales
[!INCLUDE[prod_short](includes/prod_short.md)] integrates with [!INCLUDE[prod_short](includes/cds_long_md.md)], which makes it easy to connect and synchronize data with other Dynamics 365 applications, such as [!INCLUDE[crm_md](includes/crm_md.md)], or even apps that you build yourself. If you are integrating for the first time, we recommend that you do so through [!INCLUDE[prod_short](includes/cds_long_md.md)]. For more information, see [Integration with Dataverse](admin-common-data-service.md).

If you have already integrated [!INCLUDE[crm_md](includes/crm_md.md)] with [!INCLUDE[prod_short](includes/prod_short.md)], you can continue to synchronize data using your setup. However, if you upgrade [!INCLUDE[prod_short](includes/prod_short.md)], or turn off your [!INCLUDE[crm_md](includes/crm_md.md)] integration, to turn it on again you must connect through [!INCLUDE[prod_short](includes/cds_long_md.md)]. 

> [!NOTE]
> Reconnecting through [!INCLUDE[prod_short](includes/cds_long_md.md)] will apply default synchronization settings, and will overwrite any configurations you have. For example, the default table mappings will be applied.

## To upgrade your connection to use Dataverse
1. Open the **Microsoft Dynamics 365 Connection Setup** page, and then turn off the **Enabled** toggle. Then close the page to disconnect from [!INCLUDE[crm_md](includes/crm_md.md)].
2. Open the **Dataverse Connection Setup** page, and in the **Ownership Model** field, choose **Person**. Then choose the **Enabled** toggle to turn on the connection to [!INCLUDE[prod_short](includes/cds_long_md.md)].
  
   > [!NOTE]
   > After you enable the connection, the Business Central Integration Solution is deployed to Dataverse.
4. On the **Microsoft Dynamics 365 Connection Setup** page, choose **Redeploy Integration Solution** to reinstall the Business Central Integration Solution.
5. Turn on the **Enabled** toggle to reconnect to [!INCLUDE[crm_md](includes/crm_md.md)].
  
   > [!NOTE]
   > After you enable the connection, the Business Central Integration Solution is deployed to [!INCLUDE[prod_short](includes/prod_short.md)]. This enables integration with tables that are specific to [!INCLUDE[crm_md](includes/crm_md.md)], such as sales orders, quotes, and invoices.
6. On the **Sales Connection Setup** page, choose **Use Default Synchronization Setup** to initialize the integration table mappings for [!INCLUDE[crm_md](includes/crm_md.md)].

   > [!IMPORTANT]
   > Using the **Use Default Synchronization Setup** action will apply the default integration table mappings. All custom mappings will be overwritten. If you have custom mappings that you want to keep, we recommend that you export them to Excel or talk to your Microsoft partner about other ways to keep your custom mappings.    

## Related information
[Integrating with Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md)  
[Integrating with Microsoft Dataverse](admin-common-data-service.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
