---
title: Troubleshooting Synchronization Errors | Microsoft Docs
description: Provides some guidance for identifying and resolving synchronization errors.
services: project-madeira
documentationcenter: ''
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 04/01/2021
ms.author: bholtorf

---
# Troubleshooting Synchronization Errors
[!INCLUDE[prod_short](includes/cc_data_platform_banner.md)]

There are lots of moving parts involved in integrating [!INCLUDE[prod_short](includes/prod_short.md)] with [!INCLUDE[prod_short](includes/cds_long_md.md)], and sometimes things go wrong. This topic points out some of the typical errors that occur and gives some pointers for how to fix them.

Errors often occur either because of something that a user has done to coupled records, or something is wrong with how the integration is set up. For errors related to coupled records, users can resolve those themselves. These errors are caused by actions such as deleting data in one, but not both, business apps and then synchronizing. For more information, see [View the Status of a Synchronization](admin-how-to-view-synchronization-status.md).

## Example
This video shows an example of how to troubleshoot errors that happened while synchronizing with [!INCLUDE[prod_short](includes/cds_long_md.md)]. The process will be the same for all integrations. 

> [!VIDEO https://go.microsoft.com/fwlink/?linkid=2097304]

Errors that are related to how the integration is set up typically require an administrator's attention. You can view these errors on the **Integration Synchronization Errors** page. Examples of some typical issues include:  
  
* The permissions and roles assigned to users are not correct.  
* The administrator account was specified as the integration user.  
* The integration user's password is set to require a change when the user signs in.  
* The exchange rates for currencies are not specified in one or the other app.  
  
You must manually resolve the errors, but there are a few ways in which the page helps you. For example:  

* The **Source** and **Destination** fields may contain links to the row where the error was found. Click the link to investigate the error.  
* The **Delete Entries Older than 7 Days** and the **Delete All Entries** actions will clean up the list. Typically, you use these actions after you have resolved the cause of an error that affects many records. Use caution, however. These actions might delete errors that are still relevant.

Sometimes the timestamps on records can cause conflicts. The "CDS Integration Record" table keeps the timestamps "Last Synch. Modified On" and "Last Synch. CDS Modified On" for the last integration done in both directions for a row. These timestamps are compared to timestamps on Business Central and Sales records. In Business Central, the timestamp is in the Integration Record table.

You can filter on records that are to be synchronized by comparing row timestamps in the table "Integration Table Mapping" fields "Synch. Modified On Filter" and "Synch. Int. Tbl. Mod. On Fltr.".

The conflict error message "Cannot update the Customer record because it has a later modified date than the Account record" or "Cannot update the Account record because it has a later modified date than the Customer record" can happen if a row has a timestamp that is bigger than IntegrationTableMapping."Synch. Modified On Filter" but it is not more recent than the timestamp on Sales Integration Record. It means that the source row was synchronized manually, and not by the job queue entry. 

The conflict happens because the destination row was also changed  - the row timestamp is more recent than Sales Integration Record's timestamp. The destination check happens only for bidirectional tables. 

These records are now moved to the "Skipped Synch. Records" page, which you open from the Microsoft Dynamics Connection Setup page in Business Central. There you can specify the changes to keep, and then synchronize the records again.

## Remove Couplings Between Records
When something goes wrong in your integration and you need to uncouple records to stop synchronizing them, you can do so for one or more records at a time. You can uncouple one or more records from list pages or the **Coupled Data Synchronization Errors** page by choosing one or more lines and choosing **Delete Coupling**. You can also remove all couplings for one or more table mappings on the **Integration Table Mappings** page. 

If an entity with a unidirectional coupling is deleted in [!INCLUDE[prod_short](includes/prod_short.md)], you must manually delete the broken coupling. To do that, on the **Coupled Data Synchronization Errors** page, choose the **Find for Deleted** action, and then delete the couplings.

## See Also
[Integrating with Microsoft Dataverse](admin-prepare-dynamics-365-for-sales-for-integration.md)  
[Setting Up User Accounts for Integrating with Microsoft Dataverse](admin-setting-up-integration-with-dynamics-sales.md)  
[Set Up a Connection to Microsoft Dataverse](admin-how-to-set-up-a-dynamics-crm-connection.md)  
[Couple and Synchronize Records Manually](admin-how-to-couple-and-synchronize-records-manually.md)  
[View the Status of a Synchronization](admin-how-to-view-synchronization-status.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]