---
title: Troubleshooting Synchronization Errors
description: This article provides guidance for identifying, troubleshooting, and resolving synchronization errors.
author: brentholtorf
ms.topic: troubleshooting-general
ms.devlang: al
ms.search.keywords:
ms.date: 04/04/2024
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Troubleshoot synchronization errors

There are lots of moving parts involved in integrating [!INCLUDE[prod_short](includes/prod_short.md)] with [!INCLUDE[prod_short](includes/cds_long_md.md)], and sometimes things go wrong. This article points out some of the typical errors that occur and gives some pointers for how to fix them.

Errors often occur either because of something that a user did to coupled records, or something is wrong with how the integration is set up. For errors related to coupled records, users can resolve them themselves. Causes for these errors are often actions, such as deleting data in one, but not both, business apps and then synchronizing. For more information, see [View the Status of a Synchronization](admin-how-to-view-synchronization-status.md).

Errors that are related to how the integration is set up typically require an administrator's attention. You can view these errors on the **Integration Synchronization Errors** page. 

The following table provides examples of typical issues:  

|Issue  |Resolution  |
|---------|---------|
|The permissions and roles assigned to the integration user aren't correct. | This error comes from [!INCLUDE[prod_short](includes/cds_long_md.md)] and it often includes the following text, **Principal user (Id=\<user id>, type=8) is missing \<privilegeName> privilege**. This error happens because the integration user is missing a privilege that allows it to access an entity. Typically, this error happens if you're synchronizing custom entities, or if you have an app installed in [!INCLUDE[prod_short](includes/cds_long_md.md)] that requires permission to access other [!INCLUDE[prod_short](includes/cds_long_md.md)] entities. To resolve this error, assign the permission to the integration user in [!INCLUDE[prod_short](includes/cds_long_md.md)].<br><br> You can find the integration user name on the **Dataverse Connection Setup** page. The error message provides the name of the permission, which can help you identify the entity for which you need permission. To add the missing privilege, sign in to [!INCLUDE[prod_short](includes/cds_long_md.md)] with an administrator account and edit the security role assigned to the integration user. For more information, see [Create or edit a security role to manage access](/power-platform/admin/create-edit-security-role). |
|You're coupling a record that uses another record that isn't coupled. For example, a customer whose currency isn't coupled or an item for which the unit of measure isn't coupled. | You must first couple the dependent record, for example, a currency or unit of measure, and then retry the coupling. |
|Your connection to Dataverse paused during synchronization. For example, because your session timed out. When that happens, the following error displays when you resume your session: _Table connection for table type CRM must be registered using RegisterTableConnection or cmdlet New-NAVTableConnection before it can be used._|* For session timeouts, refresh the page to reconnect to Dataverse. The error message disappears.<br><br>* For an issue in the code, for example, if you're using a custom page to show data from a Dataverse entity, contact your Microsoft partner or support. When you do, use the **Copy details** action to share details about the error. |
|User does not have required privileges (or role membership) to access the org when it is in Admin Only mode.|You can set a sandbox, production, or trial (subscription-based) environment in administration mode so that only users with System Administrator or System Customizer security roles will be able to sign in to that environment. Administration mode is useful when you want to make operational changes and not have regular users affect your work, and not have your work affect end users (non-admins). 
Data synchronization doesn't work on Dataverse environments in Administration mode. Learn how to disable Administration mode in [Administration mode](/power-platform/admin/admin-mode#set-administration-mode).|

The following are some tools on the Integration Synchronization Errors page that can help you manually resolve these issues.  

* The **Source** and **Destination** fields can contain links to the row where the error was found. Choose the link to investigate the error.  
* The **Delete Entries Older than 7 Days** and the **Delete All Entries** actions clean up the list. Typically, you use these actions after you resolve the cause of an error that affects many records. Use caution, however. These actions might delete errors that are still relevant.
* The **Show Error Call Stack** action shows information that can help identify the cause of the error. If you can't resolve the error yourself and you decide to submit a support request, include the information in the support request.

## Related information

[Integrating with Microsoft Dataverse](admin-prepare-dynamics-365-for-sales-for-integration.md)  
[Setting Up User Accounts for Integrating with Microsoft Dataverse](admin-setting-up-integration-with-dynamics-sales.md)  
[Set Up a Connection to Microsoft Dataverse](admin-how-to-set-up-a-dynamics-crm-connection.md)  
[Couple and Synchronize Records Manually](admin-how-to-couple-and-synchronize-records-manually.md)  
[View the Status of a Synchronization](admin-how-to-view-synchronization-status.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
