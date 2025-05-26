---
title: Regulatory 1099 format changes and details
description: Learn about the changes applied to the IRS 1099 tax form regarding the required codes for payments to vendors.
author: brentholtorf
ms.topic: article
ms.search.keywords: local, 1099
ms.search.form: 10015, 10016, 10018, 10900, 315, 466, 467, 468, 469
ms.date: 02/04/2025
ms.reviewer: v-soumramani
ms.author: bholtorf
ms.service: dynamics-365-business-central
---

# Regulatory 1099 format changes and details

> [!IMPORTANT]
> From version 24.0, you can start using the 1099 functionality for better transparency, integration, and automation. To do this, you must enable this feature using the **Feature Management** page. You can find more details [here](introduction-to-the-irs-forms.md). If you don't enable it, [!INCLUDE[prod_short](../../includes/prod_short.md)] automatically enables it with version 27.0. Therefore, we recommend you use this version.

The Internal Revenue Service (IRS) periodically issues updates to the format used in the 1099 Form Box. This article lists changes to the codes and requirements in the IRS 1099 forms.

> [!IMPORTANT]
> Running the [**Update Form Boxes**](set-up-use-irs1099-form.md#setup) action prevents you from reporting for previous years because some boxes change their meaning. Make sure you've done all your reporting for the previous year before you update the form boxes to prepare for reporting for the new year.

## Regulatory 1099 format changes November 2023

There are no changes associated with the 1099 report layouts for the year 2023. To continue printing the text of the new year on reports, such as 2024, you should upgrade your [!INCLUDE[prod_short](../../includes/prod_short.md)]. To get this update, you must [run the **Update Form Boxes** action on the **1099 Form Boxes** page](set-up-use-irs1099-form.md#setup).   

## Regulatory 1099 format changes November 2022

1099 changes for 2022 provide an upgrade for the MISC and DIV boxes.

* Some of the boxes will be shifted in all 1099 reports.
* A calendar year is added in the top right corner in printouts.
* For the MISC report, the position of the FATCA mark is different. There are no changes in the sequence of text elements for the Magnetic Media.

The additions are relevant for the reporting year 2022. Before you prepare your reporting for 2021, you must first upgrade your [!INCLUDE[prod_short](../../includes/prod_short.md)] to handle the new requirements.

## Regulatory 1099 format changes December 2021

The following table lists the 1099 Form Box codes that are added to 1099 forms.

|Form  |Amount Type  | Code  |
|---------|---------|---------|
|Form 1099-DIV     |Section 897 Ordinary Dividends         |     DIV-02-E     |
|Form 1099-DIV     |Section 897 Capital Gains         |    DIV-02-F     |
|Form 1099-MISC     |Fish Purchased for resale         |    MISC-11     |
|Form 1099-NEC     |Payer made direct sales totaling $5,000 or more of consumer products to recipient for resale         |    NEC-02     |

The additions are relevant for the reporting year 2021. Before you prepare your reporting for 2021, you must first upgrade your [!INCLUDE[prod_short](../../includes/prod_short.md)] to handle the new requirements. To get this update, you must [run the **Update Form Boxes** action on the **1099 Form Boxes** page](set-up-use-irs1099-form.md#setup). Alternatively, you can open the **1099 Form Boxes** page, and use the **Schedule an update of the form boxes** link in the notification to specify when you want the update to run.

## Regulatory 1099 format changes December 2020

In [!INCLUDE[prod_short](../../includes/prod_short.md)], the new 1099 Form Box codes *NEC-01* and *MISC-14*, and a new form, *Vendor 1099 Nec*, have been added. The additions are relevant for the reporting year 2020. Before you submit your reporting for 2020, you must first upgrade your [!INCLUDE[prod_short](../../includes/prod_short.md)] to handle the new requirements. To get this update, you must [run the action **Update Form Boxes** on the **1099 Form-Boxes** page](set-up-use-irs1099-form.md#setup).  

## Regulatory 1099 format changes December 2018

In [!INCLUDE[prod_short](../../includes/prod_short.md)], a new 1099 Form Box code *DIV-05* has been added, and all the 1099 codes from DIV-05 to DIV-11 were upgraded to codes from DIV-06 to DIV-12. When you open the **IRS 1099 Form Box** page, a notification pops up to upgrade the form boxes. If you change the 1099 code on the **Vendor Card** page, a notification displays asking if you want to update the 1099 codes for all the associated entries (like purchase documents, journal lines, posted invoices, credit memos, and vendor ledger entries).  

## Related information

- [Set Up and Use the IRS 1099 Form](set-up-use-irs1099-form-v24.md)  
- [United States Local Functionality](united-states-local-functionality.md)  
- [Register New Vendors](../../purchasing-how-register-new-vendors.md)  
- [Record Purchase](../../purchasing-how-record-purchases.md)  
- [Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
