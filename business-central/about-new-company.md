---
title: Create new companies using an assisted setup guide
description: It's easy to create a new, blank company in Business Central. An assisted setup guide helps you through the steps, and you can import your business data.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.date: 04/14/2023
ms.custom: bap-template
ms.search.keywords: company, setup wizard
ms.search.form: 1803, 9020, 9022, 9026, 9027, 9030, 9000, 9009, 9004, 9005, 9024, 9006, 9007, 9010, 9016, 9017
---
# Create New Companies in [!INCLUDE[prod_short](includes/prod_short.md)]

In [!INCLUDE[prod_short](includes/prod_short.md)], the container for business data that belongs to a business unit or legal entity is referred to as a *company*. When you sign up for [!INCLUDE[prod_short](includes/prod_short.md)], you're given a demonstration company and an empty company, *My Company*. Switching between the companies is easy: just go to **My Settings** and move to the other company. But you can also create new companies in [!INCLUDE[prod_short](includes/prod_short.md)] depending on your business needs.  

> [!NOTE]
> To create a new company, you must be assigned to the **Super** permission set.

When you create a new company, an assisted setup guide helps you get the basics in place. Then, you can import relevant data from your legacy system or another company in [!INCLUDE[prod_short](includes/prod_short.md)].  

[!INCLUDE [about-ui-learn](includes/about-ui-learn.md)]

## Choose the right template

If you decide to add a company to your [!INCLUDE[prod_short](includes/prod_short.md)], you can use the **Create New Company** assisted setup guide to get started. The setup guide is available from the **Companies** page and from the lookup in the **Company** field on the **My Settings** page.  

The setup guide offers two templates and a blank option:

- **Evaluation - Sample Data**  
    This creates a company that is similar to the demonstration company with sample data and setup data. This type of company is available to you without switching to a 30-day trial period, which the other types do.  
- **Production - Setup Data Only**  
    This creates a company that is similar to **My Company** with setup data but without sample data. You'll be able to use this company for a 30-day trial period.  
- **Create New - No Data**  
    This creates a blank company without setup data. You'll be able to use this company for a 30-day trial period.  

If you want to get started easily with a new company, choose **Production - Setup Data Only** and then import your own business data, such as customers, items, and vendors. Choose the **New** template if you want to set up everything from scratch. In that case, you can use the **Company Setup** assisted setup guide to help you get started with essential setup data.  

> [!NOTE]  
> When you create a new company, it takes a few minutes before you can access it in [!INCLUDE[prod_short](includes/prod_short.md)]. The setup status on the **Companies** page shows when the new company is ready for you. Then, you can switch to the new company by using **My Settings**.  

During your 30 day trial, you can create any number of new companies, but they'll only be available during your trial. For more information, contact your [!INCLUDE[prod_short](includes/prod_short.md)] partner. See also the [Dynamics 365 Business Central trial FAQ](trial-faq.md) article.  

Your administrator can learn more about trials and subscriptions [here](/dynamics365/business-central/dev-itpro/administration/trials-subscriptions).  

## Copy a company

On the **Companies** page, you can use the **Copy** action to create a second company based on the contents of an existing company. That's useful, for example, when you want to test a company without disrupting production data.

> [!Important]
> Don't use the Copy action to take a backup of a company. To take a backup, start by exporting the database as a .bacpac file. For more information, see [Exporting Databases](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-database-export) in the development and administration help.

[!INCLUDE [email-copy-company](includes/email-copy-company.md)]

## Set up the company

When you sign in to a new company, the **Company Setup** wizard runs automatically and helps you get started. You'll be asked for information about your business, such as the address, bank details, and inventory costing method. We ask for this information because it's used as a basis for many areas in [!INCLUDE[prod_short](includes/prod_short.md)] that you'll then not have to set up manually later.  

For example, [!INCLUDE [prod_short](includes/prod_short.md)] includes your company address in invoices and other documents and your bank information in payments. The costing method is used to calculate prices and inventory valuation.  

Once you have the basics in place, you can set up remaining core areas. Then, you're ready to add business data, such as customers and vendors. For more information, see [Set Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md).  

## Companies and environments

[!INCLUDE [company_environment](includes/company_environment.md)]

For more information, see [Switching to Another Company or Environment](ui-organization-switch.md). For more information about environments, see [Understanding the Infrastructure of Business Central Online](/dynamics365/business-central/dev-itpro/administration/tenant-environment-topology) (in English only).  

## Changing a company's name

Once a company has been created, you can't change its name. But you can change its **Display Name**, which is text that will be shown for the company throughout the application.  

> [!TIP]
> You can rename a company if you're using [!INCLUDE[prod_short](includes/prod_short.md)] on-premises.

## Add Contoso Coffee

The Contoso Coffee app provides demonstration data to help you explore the advanced capabilities of [!INCLUDE [prod_short](includes/prod_short.md)]. Find the app in AppSource, and install it in an empty company, for example a company in a sandbox environment. For more information, see [Introduction to Contoso Coffee Demo Data](contoso-coffee/contoso-coffee-intro.md).  

## See also

[Customizing Business Central](ui-customizing-overview.md)  
[Setting Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Understanding the Infrastructure of Business Central Online (English only)](/dynamics365/business-central/dev-itpro/administration/tenant-environment-topology)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
