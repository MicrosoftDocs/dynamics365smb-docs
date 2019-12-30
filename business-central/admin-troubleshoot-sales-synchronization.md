---
title: Troubleshooting Synchronization Errors | Microsoft Docs
description: Provides some guidance for identifying and resolving synchronization errors.
services: project-madeira
documentationcenter: ''
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 10/01/2019
ms.author: bholtorf

---
# Troubleshooting Synchronization Errors
There are lots of moving parts involved in integrating [!INCLUDE[d365fin](includes/d365fin_md.md)] with [!INCLUDE[crm_md](includes/crm_md.md)], and sometimes things go wrong. This topic points out some of the typical errors that occur and gives some pointers for how to fix them.

Errors often occur either because of something that a user has done to coupled records or something is wrong with how the integration is set up. For errors related to coupled records, users can resolve those themselves. These errors are caused by actions such as deleting a record in one, but not both, business apps and then synchronizing. For more information, see [View the Status of a Synchronization](admin-how-to-view-synchronization-status.md).

> [!VIDEO https://go.microsoft.com/fwlink/?linkid=2097304]

Errors that are related to how the integration is set up typically require an administrator's attention. You can view these errors on the **Integration Synchronization Errors** page. Examples of some typical issues include:  
  
* The permissions and roles assigned to users are not correct.  
* The administrator account was specified as the integration user.  
* The integration user’s password is set to require a change when the user signs in.  
* The exchange rates for currencies are not specified in one or the other app.  
  
You must manually resolve the errors, but there are a few ways in which the page helps you. For example:  

* The **Source** and **Destination** fields may contain links to the record where the error was found. Click the link to open the record and investigate the error.  
* The **Delete Entries Older than 7 Days** and the **Delete All Entries** actions will clean up the list. Typically, you use these actions after you have resolved the cause of an error that affects many records. Use caution, however. These actions might delete errors that are still relevant.

## See Also
[Integrating with [!INCLUDE[crm_md](includes/crm_md.md)]](admin-prepare-dynamics-365-for-sales-for-integration.md)  
[Setting Up User Accounts for Integrating with [!INCLUDE[crm_md](includes/crm_md.md)]](admin-setting-up-integration-with-dynamics-sales.md)  
[Set Up a Connection to [!INCLUDE[crm_md](includes/crm_md.md)]](admin-how-to-set-up-a-dynamics-crm-connection.md)  
[Couple and Synchronize Records Manually](admin-how-to-couple-and-synchronize-records-manually.md)  
[View the Status of a Synchronization](admin-how-to-view-synchronization-status.md)  