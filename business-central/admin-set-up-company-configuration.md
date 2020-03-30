---
    title: Set Up Company Configuration | Microsoft Docs
    description: The implementation process begins with the Business Central solution will require. You bundle all of this information into configuration packages.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Set Up Company Configuration
The implementation process begins with the Microsoft partner. The partner is responsible for thinking through the configuration details and creating a package that a customer can easily apply. Before you create a new company, you should plan how it will be configured. You must consider basic setup data and the types of data that your [!INCLUDE[d365fin](includes/d365fin_md.md)] solution will require. You bundle all of this information in configuration packages.

RapidStart Services also provides you with the tools that you will use to migrate your legacy data, such as customers and vendors.  

We recommend that you create configuration packages with most of the setup tables already filled in, so that customers only have to change a few settings after the package is applied. For example, when you create a new company, the **No. Series** and the **No. Series Line** tables are filled in with a set of number series and starting numbers. The corresponding **No. Series** fields in the setup tables are also filled in automatically. You do not have to do the work of entering number series and other basic setup data. You can also manually change all default data that is used with RapidStart Services by using the configuration worksheet.  

The configuration packages are built on a preconfigured company. After you have set up a company that meets your needs, you can create a configuration package that contains relevant data from this company. You can then use it when you create a new company that is to be configured in the same way.  

To facilitate the import of master data, such as customer and vendor information, you can use configuration templates. Configuration templates contain a set of default settings that are automatically assigned to the records imported into [!INCLUDE[d365fin](includes/d365fin_md.md)].

The following table describes a sequence of tasks with links to topics that describe them.

|**To**|**See**|  
|------------|-------------|  
|Plan a company configuration by filling in the configuration worksheet.|[Manage Company Configuration in a Worksheet](admin-how-to-manage-company-configuration-in-a-worksheet.md)|  
|Create a configuration package, customize a package, assign tables to a package, review or edit existing customer data, create the new company and then move test data to the production environment.|[Prepare a Configuration Package](admin-how-to-prepare-a-configuration-package.md)| 

## See Also  
[Setting Up a Company With RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)
