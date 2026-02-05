---
title: Introduction to the IRS 1099 tax forms [US]
description: Discover the purposes and methods for using IRS 1099 Tax Forms in the US.
author: altotovi
ms.topic: concept-article
ms.search.keywords: local, 1099, IRS, tax
ms.search.form: 10030, 10031, 10036, 10037
ms.date: 02/04/2026
ms.author: altotovi
ms.reviewer: v-soumramani
ms.service: dynamics-365-business-central
---

# Introduction to the IRS 1099 tax forms

> [!IMPORTANT]
> The IRS has confirmed that Microsoft’s TCC transmitter for submitting 1099 forms is fully operational. All cloud users can use the complete A2A integration through the IRIS platform without any restrictions.

In this article, you learn how to set up 1099 reporting, generate 1099 Tax Forms, submit them to the IRS, and send copies to vendors using Business Central.

## IRS 1099 tax form introduction

The IRS 1099 form is used in the United States to report various types of income other than salaries, wages, or tips.

## Who needs to file an IRS 1099 tax form

IRS 1099 Tax Forms are used by businesses and individuals to report income such as payments made to nonemployees or independent contractors, miscellaneous income, dividends, interest, and similar.

## Types of IRS forms

There are several types of 1099 Tax Forms, each corresponding to a specific type of income. You can find a complete list of 1099 Tax Forms and instructions on the IRS website. [!INCLUDE[prod_short](../../includes/prod_short.md)] supports the following 1099 Tax Form types:

- **1099-MISC**: This form reports miscellaneous income, such as payments made to nonemployees or independent contractors, royalties, rents, prizes, awards, and other income not reported on other forms.  
- **1099-NEC**: This form reports payment made to nonemployees or independent contractors. These payments are typically for services performed for a trade or business. Common uses of form type include reporting payments to freelancers, consultants, vendors, subcontractors, and other self-employed individuals who provide services to a business but aren't considered employees.
- **1099-INT**: This form reports interest income, such as interest paid by banks, savings accounts, bonds, notes, and other sources.  
- **1099-DIV**: This form reports dividend income, such as dividends paid by corporations, mutual funds, and other entities.

> [!NOTE]
> This guidance isn't intended as comprehensive instruction for tax reporting. Before making your final calculations, it's advisable to seek advice from your tax consultant, accountant, and representatives from the IRS.
> [!IMPORTANT]
> The functionality described here is active from Business Central version 24.0 and it requires manual activation on the **Feature Management** page. After the user activates it, the old [1099 functionality](set-up-use-irs1099-form.md) is deactivated.

This feature integrates with the IRS and doesn't print 1099 Tax Forms on preprinted original IRS 1099 Tax Forms. Instead, [!INCLUDE[prod_short](../../includes/prod_short.md)] submits 1099 Tax Forms through integration with IRS and sends Copy B to vendors as *Copy Substitutions* printed on plain paper.  

## Features overview

To get started managing IRS 1099 functionality, see the following articles.  

|  Article  |  Description  |  
|--------|--------------|  
| [IRS 1099 Setup](set-up-use-irs1099-form-v24.md) | Learn how to set up all IRS 1099 related areas. |
| [Using IRS 1099](how-to-1099-use.md) | Learn how to prepare your document and how to create 1099 forms based on your entries. |
| [Reporting IRS 1099](how-to-1099-report.md) | Learn how to submit your 1099 forms to the IRS and to send them to your vendors. |

## Related information

- [United States Local Functionality](united-states-local-functionality.md)
- [How to setup the IRS 1099 forms](set-up-use-irs1099-form-v24.md)
- [How to use the IRS 1099 forms](how-to-1099-use.md)
- [How to submit and report the IRS 1099](set-up-use-irs1099-form-v24.md#print-report-configuration)
- [Previous version of 1099 functionality](set-up-use-irs1099-form.md)
- [Register New Vendors](../../purchasing-how-register-new-vendors.md)
- [Record Purchase](../../purchasing-how-record-purchases.md)
- [Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)
