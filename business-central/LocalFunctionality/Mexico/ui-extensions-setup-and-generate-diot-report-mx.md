---
title: Set up and generate DIOT reports | Microsoft Docs
description: Use this extension to set up and generate DIOT declarations in Business Central for the Mexican authorities.
author: sorenfriisalexandersen
ms.topic: how-to
ms.devlang: al
ms.search.keywords: extension, DIOT, authorities, export, compliance, DIOT declarations
ms.search.form: 27030, 27031, 27032, 27033, 27034
ms.date: 02/26/2025
ms.author: soalex
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up and generate DIOT reports

As a company in Mexico, you must report VAT from vendor purchases to the Mexican government, to SAT - Servicio de Administración Tributaria. This can be done in [!INCLUDE[prod_short](../../includes/prod_short.md)] by generating a file that can be uploaded to SAT. This article describes how to set up the functionality and generate the report. The DIOT (Declaración Informativa de Operaciones con Terceros) report functionality is created as an extension (app) for [!INCLUDE[prod_short](../../includes/prod_short.md)] and is preinstalled in the online version. However, it must be installed manually in the on-premises version of [!INCLUDE[prod_short](../../includes/prod_short.md)].

> [!NOTE]
> Starting with version 26.3, the exported DIOT file complies with the new SAT regulations effective in 2025, featuring a TXT file format that includes 54 fields.   

## What does this extension handle?

The extension provides the following capabilities:

* Setup of the DIOT-related information
* Vendor settings
* Export the DIOT report so it can be uploaded to the authorities

## Setup of the Mexican DIOT extension

You set up the DIOT extension through Assisted Setup, which provides an easy, step-by-step guide for getting started with DIOT in [!INCLUDE[prod_short](../../includes/prod_short.md)]. If needed, you can run the guide several times until the setup is completed.

1. In [!INCLUDE[prod_short](../../includes/prod_short.md)], choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Assisted Setup**, and then choose the related link.  
1. Choose the **Set Up DIOT** action.
1. The first page in the setup guide explains what you are about to set up. Choose the **Next** button.
1. In the in **Default Vendor DIOT Type of Operation** field, choose the default type of operation that you want to be set on vendors in the system.

    Every entry in the report must be assigned a **Type of Operation** value. There are three valid types: **Prof. Services**, **Lease and Rent**, and **Others**. You aren't allowed to report the **Lease and Rent** type of operation for a vendor that isn't local. All vendors are updated with the chosen setting.

1. Choose a value in the **Type of Operation** field, and then choose the **Next** button.
1. Choose the **Open Vendor List** action to select another **Type of Operation** value individually for vendors if you want the setting to be different from what you chose in the previous step.

    A special page opens, which includes the **DIOT Type of Operation** field. Here you must set up DIOT concepts, which is a sort of setup of how VAT entries are collected for the report.
1. Choose the **Open DIOT Concepts** action.

    You'll see a list of predefined DIOT concepts that look like VAT setup. These DIOT concepts must be linked to VAT product posting groups and VAT business posting groups. You may not have to link all of the DIOT concepts. Investigate each DIOT concept and decide how these map to your VAT posting setup.

    Adding a link to a DIOT concept is done by clicking the number in the **VAT Link Count** field. Note, that not all DIOT concepts must be linked. DIOT concepts with **None** in the **Column Type** field exist for legacy reasons and can't be linked. For records where the **VAT Link Count** field isn't filled in, you should investigate if you have VAT entries that fall under this DIOT concept and add the corresponding link. DIOT records where the **VAT Link Count** field is filled in indicate that links are already created or don't have to be created.

1. Choose the **Next** button.
   The setup of DIOT is now finished.
1. Choose the **Finish** button.

## Vendor Setup 

> [!NOTE]
> For the DIOT report, the vendor's operation type is used for all operations with that vendor unless you specifically change the value of the **DIOT Type Of Operation** in the document before you post it. The DIOT operation type for the vendor isn't passed on to purchase documents automatically. If you want to use a type other than the one that is specified for the vendor, change the field on the purchase document manually. 

To update necessary fields on the **Vendor** card, follow next steps:   

1. In [!INCLUDE[prod_short](../../includes/prod_short.md)], choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendor Card**, and then choose the related link.   
2. Select the **Tax Effects Applied** field to show if the tax effects are applied to the invoices related to transactions with the vendor. This value will be exported at the 54th field as ‘01’ when **Tax Effects Applied** = TRUE and ‘02’ otherwise. 
3. Fill in the **Tax Jurisdiction Location** in case **Country/Region Code** of the vendor is not in the list of **DIOT Country/Region**. This field will be enabled for usage only when the **Country/Region Code** has "ZZZ" (Other) value. 

## Optional setup for reporting withholding tax with the DIOT extension

The DIOT report exports data including withholding tax amounts for vendor transactions. Calculation of withholding tax is currently not supported in the Mexican version of [!INCLUDE[prod_short](../../includes/prod_short.md)]. To work around this, you can post extra lines to a predefined general ledger account. The DIOT extension supports reporting withholding tax data in the following way:

The **VAT Posting Setup** table has a new field, **DIOT WHT %**. By setting this field to a value other than zero, you indicate that all entries posted with this setup are to be considered as if they were posted with that amount of VAT withheld.

For example, if you have transactions that are supposed to be 10% VAT and 5% withholding tax, use a posting setup where the **VAT %** field contains *10* and the **DIOT WHT %** field contains *5*.  

This field will only affect the DIOT report calculations and not the actual posting of the lines/entries/documents, so you must continue the existing workaround that you may have for calculating withholding tax, regardless of setting up the DIOT Report extension.

### Create an export of DIOT report files

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Create DIOT Report**, and then choose the related link.  
1. On the **Create DIOT report** request page, set the **Starting Date** and **Ending Date** fields to represent the period for which you wish to report.
1. Choose the **OK** button.

    You may get an error regarding the **RFC No.** field, which needs to be set up on local vendors. To set this up, fill in the **RFC No.** field on the **Payments** tab on the **Vendor Card** page.

When the report runs without errors, you are prompted to save the file **Diot.txt**, which you can then send to authorities.

## Related information

- [Customizing [!INCLUDE[prod_short](../../includes/prod_short.md)] Using Extensions](../../ui-extensions.md)  
- [Getting Ready for Doing Business](../../ui-get-ready-business.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
