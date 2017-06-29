---
title: "Set Up Company Configuration"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "RapidStart Services, creating companies"
  - "companies, creating"
  - "companies, RapidStart Services"
ms.assetid: 033f9ffe-94e5-4656-b3d7-6f7488008781
caps.latest.revision: 24
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# Set Up Company Configuration
The implementation process begins with the ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> partner. It’s the partner who is responsible for thinking through the configuration details and creating a package that a customer can easily apply. Before you create a new company, you should plan how it will be configured. You need to consider basic setup data and the types of data that your ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> solution will require. You bundle all of this information into configuration packages.  
  
 ADD INCLUDE<!--[!INCLUDE[rimlong](../SetupAndAdministration/includes/rimlong_md.md)]--> also provides you with the tools that you will use to migrate your legacy data for tables in ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]-->. Examples of the types of data that you will migrate include information about existing customers and vendors.  
  
 We recommend that you create configuration packages with most of the setup tables already filled in, so that customers only have to change a few settings after the package is applied. For example, when you create a new company, table 308, **No. Series**, and table 309, **No. Series Line**, are filled in with a set of number series and starting numbers. The corresponding **No. Series** fields in the setup tables are also filled in automatically. You do not have to do the work of entering number series and other basic setup data. You can also manually change all default data that is used with ADD INCLUDE<!--[!INCLUDE[rim](../Roles/includes/rim_md.md)]--> by using the configuration worksheet.  
  
 The configuration packages are built on a preconfigured company. After you have setup a company that meets your needs, you can create a configuration package that contains relevant data from this company. You can then use it when you create a new company that is to be configured in the same way.  
  
 To facilitate the import of master data, such as customer and vendor information, you can use configuration templates. Configuration templates contain a set of default settings, which are automatically assigned to the records imported into ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]-->.  
  
 The following table describes the sequence of tasks with links to topics that describe them. These tasks are listed in the order in which you generally perform them.  
  
|**To**|**See**|  
|------------|-------------|  
|Plan a configuration.|[How to: Manage Company Configuration in a Worksheet](../SetupAndAdministration/how-to-manage-company-configuration-in-a-worksheet.md)|  
|Create configuration package.|[How to: Create a Configuration Package](../SetupAndAdministration/how-to-create-a-configuration-package.md)|  
|Gather and categorize the information that you want to use to configure a new company and arrange tables in a logical way in the **Configuration Worksheet** window.|[How to: Customize a Package or Worksheet](../SetupAndAdministration/how-to-customize-a-package-or-worksheet.md)|  
|Assign your defined tables to configuration packages in the **Configuration Worksheet** window.|[How to: Assign a Configuration Package](../SetupAndAdministration/how-to-assign-a-configuration-package.md)|  
|Modify configuration data.|[How to: Review and Customize Existing Database Data](../SetupAndAdministration/how-to-review-and-customize-existing-database-data.md)|  
|Modify permission sets with default permissions using RapidStart Services.|[How to: Work with the BASIC Permission Set](../SetupAndAdministration/how-to-work-with-the-basic-permission-set.md)|  
|Create a new company and copy data to a production environment.|[How to: Copy Data from Test Environment to Production Environment](../SetupAndAdministration/how-to-copy-data-from-test-environment-to-production-environment.md)|  
  
## See Also  
 [Setup and Administration](../SetupAndAdministration/setup-and-administration.md)   
 [Set Up Complex Application Areas Using Best Practices](../SetupAndAdministration/set-up-complex-application-areas-using-best-practices.md)