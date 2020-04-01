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
ms.date: 04/01/2020
ms.author: bholtorf

---
# Troubleshooting Synchronization Errors
There are lots of moving parts involved in integrating [!INCLUDE[d365fin](includes/d365fin_md.md)] with Common Data Service, and sometimes things go wrong. This topic points out some of the typical errors that occur and gives some pointers for how to fix them.

Errors often occur either because of something that a user has done to coupled records or something is wrong with how the integration is set up. For errors related to coupled records, users can resolve those themselves. These errors are caused by actions such as deleting a record in one, but not both, business apps and then synchronizing. For more information, see [View the Status of a Synchronization](admin-how-to-view-synchronization-status.md).

## Example
This video shows an example of how to troubleshoot errors that happened while synchronizating with Sales. The process will be the same for all integrations. 

> [!VIDEO https://go.microsoft.com/fwlink/?linkid=2097304]

Errors that are related to how the integration is set up typically require an administrator's attention. You can view these errors on the **Integration Synchronization Errors** page. Examples of some typical issues include:  
  
* The permissions and roles assigned to users are not correct.  
* The administrator account was specified as the integration user.  
* The integration user's password is set to require a change when the user signs in.  
* The exchange rates for currencies are not specified in one or the other app.  
  
You must manually resolve the errors, but there are a few ways in which the page helps you. For example:  

* The **Source** and **Destination** fields may contain links to the record where the error was found. Click the link to open the record and investigate the error.  
* The **Delete Entries Older than 7 Days** and the **Delete All Entries** actions will clean up the list. Typically, you use these actions after you have resolved the cause of an error that affects many records. Use caution, however. These actions might delete errors that are still relevant.

Sometimes the timestamps on records can cause conflicts. The "CDS Integration Record" table keeps the timestamps "Last Synch. Modified On" and "Last Synch. CDS Modified On" for the last integration done in both directions for a record. These timestamps are compared to timestamps on Business Central and Sales records. In Business Central, the timestamp is in the Integration Record table.

You can filter on records that are to be synched by comparing record timestamps in the table "Integration Table Mapping" fields "Synch. Modified On Filter" and "Synch. Int. Tbl. Mod. On Fltr.".

The conflict error message "Cannot update the Customer record because it has a later modified date than the Account record" or "Cannot update the Account record because it has a later modified date than the Customer record" can happen if a record has a timestamp that is bigger than IntegrationTableMapping."Synch. Modified On Filter" but it is not more recent than the timestamp on Sales Integration Record. It means that the source record was synced manually, not by the job queue entry. 

The conflict happens because the destination record was also changed  - the record timestamp is more recent than Sales Integration Record's timestamp. The destination check happens only for bi-directional tables. 

These records are now moved to the "Skipped Synch. Records" page, which you open from the Microsoft Dynamics Connection Setup page in Business Central. There you can specify the changes to keep, and then synchronize the records again.

## See Also
[Integrating with Common Data Service](admin-prepare-dynamics-365-for-sales-for-integration.md)  
[Setting Up User Accounts for Integrating with Common Data Service](admin-setting-up-integration-with-dynamics-sales.md)  
[Set Up a Connection to Common Data Service](admin-how-to-set-up-a-dynamics-crm-connection.md)  
[Couple and Synchronize Records Manually](admin-how-to-couple-and-synchronize-records-manually.md)  
[View the Status of a Synchronization](admin-how-to-view-synchronization-status.md)  
