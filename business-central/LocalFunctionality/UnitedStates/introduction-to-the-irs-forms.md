---
title: Introduction to the IRS 1099 forms [US]
description: Learn about the reasons why and how to use IRS 1099 tax forms in the US.
author: altotovi
ms.topic: conceptual
ms.search.keywords: local, 1099, IRS, tax
ms.search.form: 10030, 10031, 10036, 10037
ms.date: 04/03/2024
ms.author: altotovi
ms.reviewer: solsen 
ms.service: dynamics-365-business-central
---

# Introduction to the IRS 1099 forms and its functionality   

In this article, you'll understand:

- What is the IRS 1099 form?
- Who needs to file an IRS 1099 form?
- Types of IRS forms

## IRS 1099 form introduction
The IRS 1099 form is used in the United States to report various types of income other than salaries, wages, or tips. 

## Who needs to file an IRS 1099 form
It's used by businesses and individuals to report income such as payments made to non-employees or independent contractors, miscellaneous income, dividends, interest, and similar. 

## Types of IRS forms
There are different types of 1099 forms, each corresponding to a specific type of income. [!INCLUDE[prod_short](../../includes/prod_short.md)] supports the following 1099 form types: 

- **1099-MISC**: This form reports miscellaneous income, such as payments made to non-employees or independent contractors, royalties, rents, prizes, awards, and other income not reported on other forms.  
- **1099-NEC**: This form reports payment made to non-employees or independent contractors. These payments are typically for services performed for a trade or business. Common uses of form type include reporting payments to freelancers, consultants, vendors, subcontractors, and other self-employed individuals who provide services to a business but aren't considered employees. 
- **1099-INT**: This form reports interest income, such as interest paid by banks, savings accounts, bonds, notes, and other sources.  
- **1099-DIV**: This form reports dividend income, such as dividends paid by corporations, mutual funds, and other entities.   

There are many other types of 1099 forms, each with its own rules and requirements. You can find a complete list of 1099 forms and instructions on the IRS website.  

> [!NOTE]
> This guidance isn't intended as comprehensive instruction for tax reporting. Before making your final calculations, it's advisable to seek advice from your tax consultant, accountant, and representatives from the IRS. 

> [!IMPORTANT]
> The functionality described here is active from [!INCLUDE[prod_short](../../includes/prod_short.md)] version 24.0 and it requires manual activation on the **Feature Management** page. Once, the user activates it, the old [1099 functionality](set-up-use-irs1099-form.md) will be deactivated. This is the one direction process.  

This feature is integrated with IRS and it will not print 1099 forms on preprinted original IRS 1099 forms. Instead, [!INCLUDE[prod_short](../../includes/prod_short.md)] will submit 1099 forms through integration with IRS and send Copy Bs to vendors as printed **Copy Substitutions** printed on plain paper.  

In this guide, we'll show you how to set up 1099 reporting, generate 1099 forms, submit them to the IRS, and then send copies to vendors using [!INCLUDE[prod_short](../../includes/prod_short.md)].  

## Features Overview   

To get started managing IRS 1099 functionality, see the following articles.  

|  Article  |  Description  |  
|--------|--------------|  
| [IRS 1099 Setup](../../UnitedStates/set-up-use-irs1099-form-v24.md) | Learn how to set up all IRS 1099 related areas. |
| [Using IRS 1099](how-to-1099-use.md) | Learn how to prepare your document and how to create 1099 forms based on your entries. |
| [Reporting IRS 1099](how-to-1099-report.md) | Learn how to submit your 1099 forms to the IRS and to send them to your vendors. |


## See also 

[United States Local Functionality](united-states-local-functionality.md)    
[How to setup the IRS 1099 forms](../../UnitedStates/set-up-use-irs1099-form-v24.md)    
[How to use the IRS 1099 forms](how-to-1099-use.md)    
[How to submit and report the IRS 1099](../../UnitedStates/set-up-use-irs1099-form-v24.md#to-print-report-configuration)    
[Previous version of 1099 functionality](../../UnitedStates/set-up-use-irs1099-form.md)    
[Register New Vendors](../../purchasing-how-register-new-vendors.md)    
[Record Purchase](../../purchasing-how-record-purchases.md)    
[Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

