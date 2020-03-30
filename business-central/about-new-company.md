---
title: Create new companies using an assisted setup guide | Microsoft Docs
description: It's easy to create a new, blank company in Business Central. An assisted setup guide helps you through the steps, and you can import your existing business data.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: company, setup wizard
ms.date: 04/01/2020
ms.author: edupont

---
# Creating New Companies in [!INCLUDE[d365fin](includes/d365fin_md.md)]
In [!INCLUDE[d365fin](includes/d365fin_md.md)], the containers for business data that belongs to a business unit or legal entity is referred to as a *company*. When you sign up for [!INCLUDE[d365fin](includes/d365fin_md.md)], you are given a demonstration company and an empty company, *My Company*. Switching between the companies is easy: just go to **My Settings** and move to the other company. But you can also create new companies in [!INCLUDE[d365fin](includes/d365fin_md.md)] depending on your business needs. When you create a new company, an assisted setup guide helps you get the basics in place. Then, you can import relevant data from your legacy system or another company in [!INCLUDE[d365fin](includes/d365fin_md.md)].  

## Creating a New Company
If you decide to add a company to your [!INCLUDE[d365fin](includes/d365fin_md.md)], you can use the **Create New Company** assisted setup guide to get you started. The setup wizard is available from the **Companies** page and from the lookup in the **Company** field on the **My Settings** page.  

The setup wizard offers three templates:

-   **Evaluation - Sample Data**  
    This creates a company that is similar to the demonstration company with sample data and setup data.  
-   **Production - Setup Data Only**  
    This creates a company that is similar to **My Company** with setup data but without sample data.
-   **Advanced Evaluation - Complete Sample Data**
    This creates a company with setup data and complete sample data for all features, including Manufacturing and Service Management.
-   **Create New - No Data**  
    This creates a blank company without setup data.  

If you want to get started easily with a new company, choose **Production - Setup Data Only** and then import your own business data, such as customers, items, and vendors. Choose the **New** template if you want to set everything up from scratch. In that case, you can use the **Company Setup** assisted setup guide to help you get started with essential setup data.  

> [!NOTE]  
>   When you create a new company, it takes a few minutes before you can access it in [!INCLUDE[d365fin](includes/d365fin_md.md)]. The setup status on the **Companies** page shows when the new company is ready for you. Then, you can switch to the new company by using **My Settings**.  

During your 30 day trial, you can create any number of new companies, but they will only be available during your trial. For more information, contact your [!INCLUDE[d365fin](includes/d365fin_md.md)] partner.  

## Copying a company
On the **Companies** page, you can use the **Copy** action to create a second company based on the contents of an existing company. This is useful, for example, when you want to test a company without disrupting production data.

> [!Important]
> This function cannot be used to take a backup of a company. Taking a company backup begins by exporting the database as a .bacpac file. For more information, see [Exporting Databases](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-database-export) in the Developer and ITPro help.

## Company Setup
When you sign in to a new company, the **Company Setup** wizard runs automatically and helps you get started. You will be asked for information about your business, such as the address, bank details, and inventory costing method. We ask for this information because it is used as a basis for many areas in [!INCLUDE[d365fin](includes/d365fin_md.md)] that you will then not have to set up manually later.  

For example, your company address is included in invoices and other documents, your bank information is used in payments, and the costing method is used to calculate prices as well as inventory valuation.  

Once you have the basics in place, you can set up remaining core areas. Then, you are ready to add business data, such as customers and vendors. For more information, see [Setting Up [!INCLUDE[d365fin](includes/d365fin_md.md)]](setup.md).  

## See Also
[Customizing Business Central](ui-customizing-overview.md)  
[Setting Up [!INCLUDE[d365fin](includes/d365fin_md.md)]](setup.md)  
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Getting Started](product-get-started.md)  
