---
title: Setup and generate DIOT reports | Microsoft Docs
description: Use this extension to setup and generate DIOT declarations in Business Central for the Mexican authorities.
services: project-madeira
documentationcenter: ''
author: sorenfriisalexandersen

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: extension, diot, authorities, export, compliance
ms.date: 10/29/2019
ms.author: soalex

---

# DIOT report - ((Declaración Informativa de Operaciones con Terceros).)

As a company in Mexico you must report VAT from vendor purchases to the Mexican government, to SAT - Servicio de Administración Tributaria. This can be done in [!INCLUDE[d365fin](../../includes/d365fin_md.md)] by generating a file that can be uploaded to SAT. This page describes how to set up this feature and generate the report. The DIOT report functionality is created as an extension (app) for [!INCLUDE[d365fin](../../includes/d365fin_md.md)] and is preinstalled in the cloud version but must be installed manually in the on-premises version of [!INCLUDE[d365fin](../../includes/d365fin_md.md)].

## What does this extensions handle?
This extension provides the following capabilities:
* Setup of the DIOT related information
* Vendor settings
* Export the DIOT report ready to upload to authorities 

## Setup of the Mexican DIOT extension
Set up the DIOT extension through Assisted Setup, which provides an easy, step-by-step guide for getting started with DIOT in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. If needed, you can run the guide several times until you finish the setup.

1. In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], choose the ![Lightbulb that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Assisted Setup**, and then choose **Assisted Setup**.  
2. Choose **Set up DIOT**.
3. The first page in the setup guide explains what you are about to set up. Choose **Next**.
4. In the in **Default Vendor DIOT Type of Operation** field, choose the default type of operation you want to be set on vendors in the system. It is required to have a **Type of Operation** assigned to every entry in the report. There are 3 valid types: **Prof. Services**, **Lease and Rent** and **Others**. You are not allowed to report the  **Lease and Rent** type of operation for a vendor which is not local. All vendors will be updated with the setting chosen here. Choose a **Type of Operation** and then choose **Next**
5. Now you select **Open Vendor List** to select another **Type of Operation** individually for vendors if you want the setting to be different form what you chose on the previous step. When finished, choose **Next**. If you choose **Open Vendor List** to edit the **Type of Operation** for the individual vendors you will see a special page designed for this, which includes the field **DIOT Type of Operation**. 
6. On this step you must set up DIOT Concepts, which is a sort of setup of how VAT Entries are collected for the report. Choose **Open DIOT Concepts**.
7. You will see a list of predefined DIOT concepts that looks like VAT setup. These DIOT Concepts must be linked to VAT Product Posting Groups and VAT Business Posting Groups. It is possible that you do not need to link all of the DIOT Concepts. Investigate each DIOT Concept and decide how these map to your VAT Posting Setup.
8. Adding a link to a DIOT Concept is done by clicking the number in the **VAT Link Count** field. Note, that not all DIOT Concepts must be linked. DIOT Concepts with **Column Type** "None" exist for legacy reasons and cannot be linked. For records where the **VAT Link Count** you should investigate if you have VAT entries that fall under this DIOT Concept and add the corresponding link. DIOT records where the **VAT Link Count** indicates that links are already created or does not have to be created. When done, chosse **Next**.
9. The setup of DIOT is now finished. Choose **Finish**.

## Optional setup for reporting Witholding Tax with the DIOT extension
The DIOT report exports data including witholding tax amounts for vendor transactions. Calculation of Witholding Tax is currently not supported in the Mexican version of [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. To work around this some users create workarounds such as posting extra lines to a predefined General Ledger Account. The DIOT extension supports reporting Witholding Tax data in the following way:
The **VAT Posting Setup** table has a new field, **DIOT WHT %**d. By setting this field to a value other than zero you indicate that all entries posted with this setup are to be considered as if they were posted with that amount of VAT withheld.

For example, if you have transactions that are supposed to be 10% VAT and 5% Witholding Tax, use a posting setup where VAT % is 10 and **DIOT WHT %** is 5.
This field will only affect the DIOT report calculations and not the actual posting of the lines/entries/documents, so you will need to continue the existing workaround you may have for calculating Witholding Tax, regardless of setting up the DIOT Report extension.

### To create an export of DIOT report files  
1. In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], choose the ![Lightbulb that opens the Tell Me feature](../../media/ui-search/search_small.png) "Tell me what you want to do") icon, enter **Create DIOT Report**, and then choose **Create DIOT Report**.  
2. On the **Create DIOT report** request page, set the **Starting Date** and **Ending Date** fields representing the period for which you wish to report.
3. Choose **OK**. You may get an error regarding **RFC No.** which needs to be set up on local vendors. To set this up fill the **RFC No.** field found on the **Payments** tab on the **Vendor** card.
4. ONce the report runs without errors you will be prompted to save the file **Diot.txt**, which you can then send to authorities.

## See Also
[Customizing [!INCLUDE[d365fin](../../includes/d365fin_md.md)] Using Extensions](../../ui-extensions.md)  
[Getting Started](../../product-get-started.md)
