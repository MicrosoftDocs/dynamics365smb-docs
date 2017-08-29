---
    title: How to Create Custom Company Configuration Packages | Microsoft Docs
    description: As you grow your business, you will likely come to rely on a set of company types that you use with most of your customers. You can streamline your implementation process by turning these types into company configuration packages that are available for reuse.
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
# How to: Create Custom Company Configuration Packages
As you grow your business, you will likely come to rely on a set of company types that you use with most of your customers. You can streamline your implementation process by turning these types into company configuration packages that are available for reuse.  
  
 In general, create a configuration package per functional area, for example, create a package for your manufacturing functionality. That lets you apply and set up new areas in a company as you need them  
  
 Another approach would be to create a package that includes the tables that define setup, such as the following:  
  
-   Fixed Asset Setup  
  
-   General Ledger Setup  
  
-   Inventory Setup  
  
-   Manufacturing Setup  
  
-   Purchases and Payables Setup  
  
-   Marketing Setup  
  
-   Service Setup  
  
-   Sales and Receivables Setup  
  
-   Warehouse Setup  
  
-   General Posting Setup  
  
-   VAT Posting Setup  
  
-   Inventory Posting Setup  
  
 To see a complete list of setup tables, Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Setup**, and then choose the related link.  
  
### To create a company package  
  
1.  Create a new ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/How%20to:%20Create%20Databases.md).  
  
2.  Create a new company for the industry or solution template. For more information, see [How to: Create a New Company](../how-to-create-a-new-company.md).  
  
3.  Setup the new company in the way you need. Fill in all required setup tables.  
  
4.  Switch to the ADD INCLUDE<!--[!INCLUDE[nav_windows](../../includes/nav_windows_md.md)]--> and open the new company. Open the configuration worksheet.  
  
5.  Add the tables that you want to transfer to another company to the worksheet. Assign the worksheet lines to the package.  
  
6.  Create a questionnaire for the most frequently used setup tables.  
  
7.  Create configuration templates to make it easier to create master data, such as customers or items.  
  
8.  Export your package as a .rapidstart file.  
  
## See Also  
 [How to: Create Configuration Questionnaires](../how-to-create-configuration-questionnaires.md)