---
title: Administrative tasks in Business Central
description: Some tasks in Business Central requires central administration and setup. See what they are and learn what to do.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: article
ms.date: 01/11/2023
ms.custom: bap-template
---
# Administration Tasks

Central administration tasks are usually performed by one role in the company. The scope of these tasks can depend on the company's size and the administrator's job responsibilities. These tasks can include managing database synchronization of job and email queues, setting up users, and customizing the user interface.  

Entering the correct setup values from the start is important to the success of any new business software. [!INCLUDE[prod_short](includes/prod_short.md)] includes a number of setup guides that help you set up core data. For more information, see [Setting Up Business Central](setup.md).

> [!NOTE]
> You can use the data migration tools to migrate existing data to [!INCLUDE [prod_short](includes/prod_short.md)] online. Alternatively, you can set up a new company in [!INCLUDE[prod_short](includes/prod_short.md)] with configuration packages to shorten deployment times, improve quality of implementation, introduce a repeatable approach to implementations, and enhance productivity by automating and simplifying recurring tasks. For more information, see [Migrate On-Premises Data to Business Central Online](/dynamics365/business-central/dev-itpro/administration/migrate-data).

You can support your setup decisions with some general recommendations for selected setup fields that are known to potentially cause the solution to be inefficient if defined incorrectly.  

A super user or an administrator can set up the Data Exchange Framework to enable users to export and import data in bank and payroll files, for example for various cash management processes. For more information, see [Exchanging Data Electronically](across-data-exchange.md).

The following table describes a sequence of tasks, with links to the articles that describe them.  

|**To**|**See**|  
|------------|-------------|
|Define who can sign in to [!INCLUDE[prod_short](includes/prod_short.md)] by creating users on the Microsoft 365 Admin Center according to the product licenses.|[Create Users According to Licenses](ui-how-users-permissions.md)|
|Assign permissions to users, modify permission sets, and group users for easy permission management.|[Assign Permissions to Users and Groups](ui-how-users-permissions.md)|
|Add users, manage permissions and access to data, assign roles.|[Manage Profiles](admin-users-profiles-roles.md)|
|Manage user settings, such as company, role, language, region and time zone.|[User Settings](admin-manage-user-settings-preferences.md)|
|Set up printers and specify which reports to print on which printers.|[Set Up Printers](ui-specify-printer-selection-reports.md)|
|Classify data sensitivities for fields so that you can respond to requests from data subjects related to their personal data.|[Classify Data Sensitivity](admin-classifying-data-sensitivity.md)|
|Respond to requests from data subjects related to their personal data.|[Respond to Requests About Personal Data](admin-responding-to-requests-about-personal-data.md)|
|Set up a new business unit using templates|[Create New Companies](about-new-company.md)|
|Track all direct modifications that users make to data in the database to identify the origin of errors and data changes.|[Logging Changes](across-log-changes.md)|  
|Enter single or recurring requests to run reports or codeunits.|[Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md)|  
|Manage, delete, or compress documents|[Delete Documents](admin-manage-documents.md)|  
|Expose pages, codeunits, and queries as web services.|[Publish a Web Service](across-how-publish-web-service.md)|
|As a part of creating Connect apps between [!INCLUDE[prod_short](includes/prod_short.md)] and 3rd-party solutions through REST APIs, define templates that are used to populate empty properties on an entity when you create a POST action through an API.|[Configure API Templates](admin-configuring-api-template.md)|
|Encrypt data on the [!INCLUDE[prod_short](includes/prod_short.md)] server by generating new or importing existing encryption keys that you enable on the server.|[Manage Data Encryption](admin-manage-data-encryption.md)|
|Connect Dynamics 365 Sales with [!INCLUDE[prod_short](includes/prod_short.md)] to obtain seamless integration between customer relations and order processing in the lead-to-cash process.|[Integrate with Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md)|
|Change which fields and actions are shown in the user interface to fit your company's business processes and extend the solution with apps.|[Customize [!INCLUDE[prod_short](includes/prod_short.md)]](ui-customizing-overview.md)|

## Administration in the admin center

Internal and delegated admins have access to the [!INCLUDE [prod_short](includes/prod_short.md)] admin center where they can configure, monitor, and troubleshoot [!INCLUDE [prod_short](includes/prod_short.md)] environments. The following table describes some of the key tasks, with links to the articles that describe them.  

|**To**|**See**|  
|------------|-------------|
|Learn about the tools that are available to you to help you troubleshoot.|[Technical Support](/dynamics365/business-central/dev-itpro/technical-support)|
|Monitor usage and troubleshoot sessions|[Environment Telemetry in the Business Central administration center](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-telemetry)|
|Manage user sessions, including canceling a session if the user is blocked.|[Manage Sessions](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-manage-sessions)|
|Configure the tenant to send telemetry data to Azure Application Insights for better analysis and troubleshooting.|[Enable Sending Telemetry to Application Insights](/dynamics365/business-central/dev-itpro/administration/telemetry-enable-application-insights)|

## Related information

[Business Functionality](across-business-functionality.md)  
[General Business Functionality](ui-across-business-areas.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]
