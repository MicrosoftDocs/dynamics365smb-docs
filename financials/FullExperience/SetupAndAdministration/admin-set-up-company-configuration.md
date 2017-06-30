---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Set Up Company Configuration
The implementation process begins with the [!INCLUDE[d365fin](includes/d365fin_md.md)] solution will require. You bundle all of this information into configuration packages.  
  
 ADD INCLUDE<!--[!INCLUDE[rimlong](../../includes/navnow_md.md)]-->. Examples of the types of data that you will migrate include information about existing customers and vendors.  
  
 We recommend that you create configuration packages with most of the setup tables already filled in, so that customers only have to change a few settings after the package is applied. For example, when you create a new company, table 308, **No. Series**, and table 309, **No. Series Line**, are filled in with a set of number series and starting numbers. The corresponding **No. Series** fields in the setup tables are also filled in automatically. You do not have to do the work of entering number series and other basic setup data. You can also manually change all default data that is used with ADD INCLUDE<!--[!INCLUDE[rim](../../includes/rim_md.md)]--> by using the configuration worksheet.  
  
 The configuration packages are built on a preconfigured company. After you have setup a company that meets your needs, you can create a configuration package that contains relevant data from this company. You can then use it when you create a new company that is to be configured in the same way.  
  
 To facilitate the import of master data, such as customer and vendor information, you can use configuration templates. Configuration templates contain a set of default settings, which are automatically assigned to the records imported into [!INCLUDE[d365fin](includes/d365fin_md.md)].  
  
 The following table describes the sequence of tasks with links to topics that describe them. These tasks are listed in the order in which you generally perform them.  
  
|**To**|**See**|  
|------------|-------------|  
|Plan a configuration.|[How to: Manage Company Configuration in a Worksheet](../how-to-manage-company-configuration-in-a-worksheet.md)|  
|Create configuration package.|[How to: Create a Configuration Package](../how-to-create-a-configuration-package.md)|  
|Gather and categorize the information that you want to use to configure a new company and arrange tables in a logical way in the **Configuration Worksheet** window.|[How to: Customize a Package or Worksheet](../how-to-customize-a-package-or-worksheet.md)|  
|Assign your defined tables to configuration packages in the **Configuration Worksheet** window.|[How to: Assign a Configuration Package](../how-to-assign-a-configuration-package.md)|  
|Modify configuration data.|[How to: Review and Customize Existing Database Data](../how-to-review-and-customize-existing-database-data.md)|  
|Modify permission sets with default permissions using RapidStart Services.|[How to: Work with the BASIC Permission Set](../how-to-work-with-the-basic-permission-set.md)|  
|Create a new company and copy data to a production environment.|[How to: Copy Data from Test Environment to Production Environment](../how-to-copy-data-from-test-environment-to-production-environment.md)|  
  
## See Also  
 [Setup and Administration](../setup-and-administration.md)   
 [Set Up Complex Application Areas Using Best Practices](../set-up-complex-application-areas-using-best-practices.md)