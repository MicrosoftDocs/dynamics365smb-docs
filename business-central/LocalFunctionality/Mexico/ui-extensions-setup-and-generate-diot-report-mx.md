---
title: Set up and generate DIOT reports | Microsoft Docs
description: Use this extension to setup and generate DIOT declarations in Business Central for the Mexican authorities.
author: sorenfriisalexandersen

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: extension, diot, authorities, export, compliance
ms.date: 04/01/2020
ms.author: soalex

---

# Set Up and Generate DIOT Reports

As a company in Mexico, you must report VAT from vendor purchases to the Mexican government, to SAT - Servicio de Administración Tributaria. This can be done in [!INCLUDE[d365fin](../../includes/d365fin_md.md)] by generating a file that can be uploaded to SAT. This topic describes how to set up the functionality and generate the report. The DIOT (Declaración Informativa de Operaciones con Terceros) report functionality is created as an extension (app) for [!INCLUDE[d365fin](../../includes/d365fin_md.md)] and is preinstalled in the online version but must be installed manually in the on-premises version of [!INCLUDE[d365fin](../../includes/d365fin_md.md)].

## What Does this Extensions Handle?
The extension provides the following capabilities:
* Setup of the DIOT-related information
* Vendor settings
* Export the DIOT report so it can be uploaded to the authorities

## Setup of the Mexican DIOT Extension
You set up the DIOT extension through Assisted Setup, which provides an easy, step-by-step guide for getting started with DIOT in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. If needed, you can run the guide several times until the setup is completed.

1. In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], choose the ![Lightbulb that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Assisted Setup**, and then choose the related link.  
2. Choose the **Set Up DIOT** action.
3. The first page in the setup guide explains what you are about to set up. Choose the **Next** button.
4. In the in **Default Vendor DIOT Type of Operation** field, choose the default type of operation that you want to be set on vendors in the system.

    Every entry in the report must be assigned a **Type of Operation** value. There are three valid types: **Prof. Services**, **Lease and Rent**, and **Others**. You are not allowed to report the **Lease and Rent** type of operation for a vendor that is not local. All vendors will be updated with the setting chosen here.

5. Choose a value in the **Type of Operation** field, and then choose the **Next** button.
6. Choose the **Open Vendor List** action to select another **Type of Operation** value individually for vendors if you want the setting to be different from what you chose in the previous step.

    A special page opens, which includes the **DIOT Type of Operation** field. Here you must set up DIOT concepts, which is a sort of setup of how VAT entries are collected for the report.
7. Choose the **Open DIOT Concepts** action.

    You will see a list of predefined DIOT concepts that look like VAT setup. These DIOT concepts must be linked to VAT product posting groups and VAT business posting groups. You may not have to link all of the DIOT concepts. Investigate each DIOT concept and decide how these map to your VAT posting setup.

    Adding a link to a DIOT concept is done by clicking the number in the **VAT Link Count** field. Note, that not all DIOT concepts must be linked. DIOT concepts with **None** in the **Column Type** field exist for legacy reasons and cannot be linked. For records where the **VAT Link Count** field is not filled in, you should investigate if you have VAT entries that fall under this DIOT concept and add the corresponding link. DIOT records where the **VAT Link Count** field is filled in indicate that links are already created or do not have to be created.

8. Choose the **Next** button.

    The setup of DIOT is now finished.
9. Choose the **Finish** button.

## Optional Setup for Reporting Witholding Tax with the DIOT Extension
The DIOT report exports data including witholding tax amounts for vendor transactions. Calculation of witholding tax is currently not supported in the Mexican version of [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. To work around this, you can post extra lines to a predefined general ledger account. The DIOT extension supports reporting witholding tax data in the following way:

The **VAT Posting Setup** table has a new field, **DIOT WHT %**. By setting this field to a value other than zero, you indicate that all entries posted with this setup are to be considered as if they were posted with that amount of VAT withheld.

For example, if you have transactions that are supposed to be 10% VAT and 5% witholding tax, use a posting setup where the **VAT %** field contains *10* and the **DIOT WHT %** field contains *5*.  

This field will only affect the DIOT report calculations and not the actual posting of the lines/entries/documents, so you must continue the existing workaround that you may have for calculating witholding tax, regardless of setting up the DIOT Report extension.

### To create an export of DIOT report files  
1. Choose the ![Lightbulb that opens the Tell Me feature](../../media/ui-search/search_small.png) "Tell me what you want to do") icon, enter **Create DIOT Report**, and then choose the related link.  
2. On the **Create DIOT report** request page, set the **Starting Date** and **Ending Date** fields to represent the period for which you wish to report.
3. Choose the **OK** button.

    You may get an error regarding the **RFC No.** field, which needs to be set up on local vendors. To set this up, fill in the **RFC No.** field on the **Payments** tab on the **Vendor Card** page.

When the report runs without errors, you will be prompted to save the file **Diot.txt**, which you can then send to authorities.

## See Also
[Customizing [!INCLUDE[d365fin](../../includes/d365fin_md.md)] Using Extensions](../../ui-extensions.md)  
[Getting Started](../../product-get-started.md)
