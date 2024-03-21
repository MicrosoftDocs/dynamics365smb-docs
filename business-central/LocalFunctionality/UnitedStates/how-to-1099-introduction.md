---
title: Introduction in IRS 1099 Forms [US]
description: Learn about reasons why and how to use IRS 1099 Tax Formes in the US..
author: altotovi

ms.topic: conceptual
ms.search.keywords: local, 1099, IRS, tax
ms.search.form: 10030, 10031, 10036, 10037
ms.date: 03/21/2024
ms.author: altotovi
ms.reviewer: 

ms.service: dynamics-365-business-central
---

# Introduction to the 1099 Functionality   

Let first understand what IRS 1099 forms are, who needs to file them, and how to fill them out correctly.   

What is the IRS 1099 form? The IRS 1099 form is used in the United States to report various types of income other than salaries, wages, or tips. It is used by businesses and individuals to report income such as payments made to non-employees or independent contractors, miscellaneous income, dividends, interest, and similar. There are different types of 1099 forms, each corresponding to a specific type of income. [!INCLUDE[prod_short](../../includes/prod_short.md)] supports the following 1099 form types: 

- **1099-MISC**: This form reports miscellaneous income, such as payments made to non-employees or independent contractors, royalties, rents, prizes, awards, and other income not reported on other forms.  
- **1099-NEC**: This form reports payments made to non-employees or independent contractors. These payments are typically for services performed for a trade or business. Common uses of form type include reporting payments to freelancers, consultants, vendors, subcontractors, and other self-employed individuals who provide services to a business but are not considered employees. 
- **1099-INT**: This form reports interest income, such as interest paid by banks, savings accounts, bonds, notes, and other sources.  
- **1099-DIV**: This form reports dividend income, such as dividends paid by corporations, mutual funds, and other entities.   

There are many other types of 1099 forms, each with its own rules and requirements. You can find a complete list of 1099 forms and instructions on the IRS website.  

> [!NOTE]
> This guidance is not intended as comprehensive instruction for tax reporting. Before making your final calculations, it's advisable to seek advice from your tax consultant, accountant, and representatives from the IRS. 

> [!IMPORTANT]
> This functionality described here is active from [!INCLUDE[prod_short](../../includes/prod_short.md)] version 24.0 and it requires manually activation in the **Feature Management** page. Once, user activates it, the old [1099 functionality](set-up-use-irs1099-form.md) will be deactivated. This is the one direction process.  

This feature is built having a mind to have integration with IRS and it will not print 1099 forms on preprinted original IRS 1099 forms. Instead of that, [!INCLUDE[prod_short](../../includes/prod_short.md)] will submit 1099 forms through integration with IRS and send Copy Bs to vendors as printed Copy Substitutions printed on a plain paper.  

In this guide, we will show you how to set up 1099 reporting, generate 1099 forms, submit them to the IRS, and send copies to vendors using [!INCLUDE[prod_short](../../includes/prod_short.md)].  

## Features Overview   

To get started managing IRS 1099 functionality, see the following topics.  

|  Article  |  Description  |  
|--------|--------------|  
| [IRS 1099 Setup](how-to-1099-setup.md) | Learn how to setup all IRS 1099 related areas. |
| [Using IRS 1099](how-to-1099-use.md) | Learn how to prepare your document and how to create 1099 forms based on your entries. |
| [Reporting IRS 1099](how-to-1099-report.md) | Learn how to submit your 1099 forms to the IRS and to send them tou your vendors. |


## See also 

[United States Local Functionality](united-states-local-functionality.md)  
[How to setup the IRS 1099 forms](how-to-1099-setup.md)
[How to use the IRS 1099 forms](how-to-1099-use.md)
[How to submit and report the IRS 1099](how-to-1099-report.md)
[Previous version of 1099 functionality](set-up-use-irs1099-form.md)
[Register New Vendors](../../purchasing-how-register-new-vendors.md)  
[Record Purchase](../../purchasing-how-record-purchases.md)  
[Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

