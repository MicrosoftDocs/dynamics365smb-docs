---
    title: How to Create Custom Company Configuration Packages | Microsoft Docs
    description: As you grow your business, you will likely come to rely on a set of company types that you use with most of your customers. You can streamline your implementation process by turning these types into company configuration packages that are available for reuse.
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
# Create Custom Company Configuration Packages
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

To see a complete list of setup tables, Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Manual Setup**, and then choose the related link.  

## To create a custom company configuration package  
1.  Create a new company. For more information, see [Creating New Companies in Business Central](about-new-company.md).  
3.  Set up the new company in the way you need. Fill in all required setup tables.  
4.  Open the new company.
5. Open the **Configuration Worksheet** page.  
6.  Add the tables that you want to transfer to another company to the worksheet. Assign the worksheet lines to the package.  
7.  Create a questionnaire for the most frequently used setup tables.  
8.  Create configuration templates to make it easier to create master data, such as customers or items.  
9.  Export your package as a .rapidstart file.  

## See Also  
[Setting Up a Company With RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)
