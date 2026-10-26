---
title: IRS 1099 Tax Forms Overview in Business Central
description: Explore IRS 1099 tax forms in Business Central, including reporting setup, vendor payment calculations, electronic filing, and vendor copies.
author: altotovi
ms.topic: overview
ms.search.keywords: local, 1099, IRS, tax
ms.search.form: 10030, 10031, 10036, 10037
ms.date: 10/19/2026
ai-usage: ai-assisted
ms.author: altotovi
ms.reviewer: jswymer
ms.service: dynamics-365-business-central
---

# Introduction to the IRS 1099 tax forms

In this article, you learn how to set up IRS 1099 reporting, generate tax forms, submit them to the IRS, and send copies to vendors by using [!INCLUDE[prod_short](../../includes/prod_short.md)]. The built-in Information Returns Intake System (IRIS) integration supports electronic filing in online environments. Each user who sends transmissions must first configure their own IRIS User ID.

## IRS 1099 tax form introduction

The IRS 1099 form is used in the United States to report various types of income other than salaries, wages, or tips.

## Who needs to file an IRS 1099 tax form

IRS 1099 Tax Forms are used by businesses and individuals to report income such as payments made to nonemployees or independent contractors, miscellaneous income, dividends, interest, and similar.

## Types of IRS forms

There are several types of 1099 Tax Forms, each corresponding to a specific type of income. You can find a complete list of 1099 Tax Forms and instructions on the IRS website. [!INCLUDE[prod_short](../../includes/prod_short.md)] supports the following 1099 Tax Form types:

- **1099-MISC**: This form reports miscellaneous income, such as rents, royalties, prizes, and awards. Payments for services performed by nonemployees are described under **1099-NEC**.
- **1099-NEC**: This form reports payment made to nonemployees or independent contractors. These payments are typically for services performed for a trade or business. Common uses of form type include reporting payments to freelancers, consultants, vendors, subcontractors, and other self-employed individuals who provide services to a business but aren't considered employees.
- **1099-INT**: This form reports interest income, such as interest paid by banks, savings accounts, bonds, notes, and other sources.  
- **1099-DIV**: This form reports dividend income, such as dividends paid by corporations, mutual funds, and other entities.

> [!NOTE]
> This guidance isn't intended as comprehensive instruction for tax reporting. Before making your final calculations, it's advisable to seek advice from your tax consultant, accountant, and representatives from the IRS.

> [!IMPORTANT]
> The functionality described here was introduced in version 24.0 as a feature update. In versions where activation is required, enable it on **Feature Management** to replace the [legacy 1099 functionality](set-up-use-irs1099-form.md). For setup in the current app, go to [Set up IRS 1099 forms](set-up-use-irs1099-form-v24.md).

This feature doesn't print on preprinted original IRS 1099 tax forms. It provides *substitute copies* that you can print on plain paper or email to vendors who consented to electronic delivery. You can print **Copy B**, **Copy C**, or **Copy 2**, and email **Copy B** or **Copy 2**.

## Explore IRS 1099 workflows

To get started managing IRS 1099 functionality, see the following articles.  

|  Article  |  Description  |  
|--------|--------------|  
| [IRS 1099 Setup](set-up-use-irs1099-form-v24.md) | Learn how to set up all IRS 1099 related areas. |
| [Using IRS 1099](how-to-1099-use.md) | Learn how to prepare your document and how to create 1099 forms based on your entries. |
| [Reporting IRS 1099](how-to-1099-report.md) | Learn how to submit your 1099 forms to the IRS and to send them to your vendors. |

## Related information

- [United States Local Functionality](united-states-local-functionality.md)
- [Set up IRS 1099 forms](set-up-use-irs1099-form-v24.md)
- [How to use the IRS 1099 forms](how-to-1099-use.md)
- [Submit and report the IRS 1099 forms](how-to-1099-report.md)
- [Previous version of 1099 functionality](set-up-use-irs1099-form.md)
- [Register New Vendors](../../purchasing-how-register-new-vendors.md)
- [Record Purchase](../../purchasing-how-record-purchases.md)
- [Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
