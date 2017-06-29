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
# How to: Assign a Configuration Package
After you have defined the tables that you want to treat as part of your configuration, you can easily assign the tables to configuration packages. You can assign a table to one package only. In the following procedure, you assign the package from within the context of the configuration worksheet.  
  
> [!NOTE]  
>  You can also create a package directly, and add tables to it. For more information, see [How to: Create a Configuration Package](../how-to-create-a-configuration-package.md).  
  
### To assign a table to a configuration package  
  
1.  In the configuration worksheet, select a line or group of lines that you want to assign to a configuration package.  
  
2.  On the **Actions** tab, in the **Functions** group, choose **Assign Package**.  
  
3.  Select a package from the list, or on the **Home** tab, choose **New** to create a new package. Choose the **OK** button.  
  
     If a table is not already included in the package, it will be added to it. The package code field on the worksheet line will be filled in with the code of the package that the table is assigned to.  
  
     For more information about how to create a package, see [How to: Create a Configuration Package](../how-to-create-a-configuration-package.md).  
  
4.  If you choose an existing package, you can see how many tables are already in the package by reviewing the information in the **No. of Tables** field.  
  
## See Also  
 [How to: Manage Company Configuration in a Worksheet](../how-to-manage-company-configuration-in-a-worksheet.md)