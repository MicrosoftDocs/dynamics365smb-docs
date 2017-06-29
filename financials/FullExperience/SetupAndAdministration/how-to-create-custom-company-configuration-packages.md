---
title: "How to: Create Custom Company Configuration Packages"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "customers, creating new accounts"
  - "templates, customers"
  - "RapidStart Services, company templates"
  - "customers, setting up"
ms.assetid: 6ad66c7f-7ae3-475b-b282-8a381843d3f7
caps.latest.revision: 14
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
  
 To see a complete list of setup tables, in the **Search** box, enter **Setup**, and then choose the related link.  
  
### To create a company package  
  
1.  Create a new FIX INCLUDE HERE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] --> database. For more information, see [How to: Create Databases](../Topic/How%20to:%20Create%20Databases.md).  
  
2.  Create a new company for the industry or solution template. For more information, see [How to: Create a New Company](../SetupAndAdministration/how-to-create-a-new-company.md).  
  
3.  Setup the new company in the way you need. Fill in all required setup tables.  
  
4.  Switch to the FIX INCLUDE HERE<!--[!INCLUDE[nav_windows](../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_windows_md.md)] --> and open the new company. Open the configuration worksheet.  
  
5.  Add the tables that you want to transfer to another company to the worksheet. Assign the worksheet lines to the package.  
  
6.  Create a questionnaire for the most frequently used setup tables.  
  
7.  Create configuration templates to make it easier to create master data, such as customers or items.  
  
8.  Export your package as a .rapidstart file.  
  
## See Also  
 [How to: Create Configuration Questionnaires](../SetupAndAdministration/how-to-create-configuration-questionnaires.md)