---
title: Setup and generate SAF-T files | Microsoft Docs
description: Use this extension to setup and generate SAF-T files for the Norwegian authorities in Business Central.
services: project-madeira
documentationcenter: ''
author: sorenfriisalexandersen

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: extension, saf-t, authorities, export, compliance
ms.date: 04/01/2020
ms.author: soalex

---

# Standard Audit Files - Tax

Starting in January, 2020, companies in Norway must report financial data and provide a set of Standard Audit Files - Tax (SAF-T) to the Norwegian authorities upon request. This extension makes it easy to set up, generate, and export Standard Audit Files - Tax in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. The exported SAF-T files will automatically be compressed as a .zip file ready to be uploaded by the user on the website of Skatteetaten, the Norwegian tax authorities.  

## What does this extensions handle?
This extension provides the following capabilities:
* Setup and mapping of chart of accounts to SAF-T standard accounts
* Mapping VAT setup to SAF-T VAT codes
* Control to which extent dimensions are exported in SAF-T files
* Export SAF-T files, either directly or by using the Job Queue. Using Job Queue lets you schedule the export to occur during quiet hours, which is useful for potentially large datasets.

## Setup of the Norwegian SAF-T extension
Set up the SAF-T extension through Assisted Setup, which provides an easy, step-by-step guide for get started with SAF-T in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. If needed, you can run the guide several times until you finish the setup.

1. In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], choose the ![Lightbulb that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Assisted Setup**, and then choose **Assisted Setup**.  
2. Choose **Set up SAF-T**.
3. The first page in the setup guide explains what you are about to set up. Choose **Next**.
4. In the in **Mapping Type** field, choose the type of Chart of Accounts you want to SAF-T accounts, and then choose **Next**. 

   > [!Note]
   > If you are using the on-premises version of [!INCLUDE[d365fin](../../includes/d365fin_md.md)], there are some additional steps. 
   > 1. Download and import source files with SAF-T accounts. Download the SAF-T mapping files from [Skatteetaten's repo on Github](https://github.com/Skatteetaten/saf-t).
   > 2. Choose **Import The Source Files For Mapping**.
   > 3. Import all required files. If you are setting up the mapping for income statement import files, make sure to import mapping codes for all records with **Income Statement** in the **Source Type** column.
   > 4. For each imported file, choose **Update mapping codes from file**.

5. To define the period for the first SAF-T reporting, choose **Accounting Period**, confirm the data range, and then choose **Next**.

   Typically, this is done for a specific accounting period, but you can also define a date range without specifying an accounting period.
6. To map your chart of accounts to the SAF-T accounts, choose **Open setup to define G/L account mappings**. Lines where the G/L Account No. is marked with green indicates that here are transactions on the account within the date range specified in the previous step, in which case it must be mapped. Other G/L accounts can be skipped. When finished, close the **SAF-T Mapping Setup Card**, and then choose **Next** in the setup guide.
7. To map the VAT Posting Setup to standard sales and purchase SAF-T tax codes, choose **Open setup to define VAT Posting Setup Mapping**.  When finished close the **SAF-T VAT Posting Setup card**, and then choose **Next** in the setup guide.
8. Norwegian authorities recommend that you export dimensions for financial transactions. However, in some situations you may not want to export dimensions - for example if you have internal dimensions that do provide value to auditors. This step lets you open the Dimensions list and choose which dimensions to export. Choose the value in the **Export to SAF-T** field, and then choose **Close**.
9. To specify the employee who is the SAF-T contact in your company, choose the employee in the **Employee No.** field. This is useful when Norwegian authorities have questions about the SAF-T files. When finished, choose **Next**.
10. The setup of SAF-T is now finished. Choose **Finish**.

> [!Note] 
> The mappings are tied to the date range you specified. You can create additional mappings for other periods without changing the mapping you already created. You can also copy mappings from previously made setups. This is to ensure that you can report SAF-T for different periods while managing changes in your chart of accounts.

## Exporting SAF-T files
To export SAF-T files from [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you must first create and set up a **SAF-T Export** to define the mapping range. For example, you can define a mapping and export the entire year of 2019, and another mapping for just the month of April 2019 if the authorities ask you to provide this data specifically.

### To create an export of SAF-T files  
1. In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], choose the ![Lightbulb that opens the Tell Me feature](../../media/ui-search/search_small.png) "Tell me what you want to do") icon, enter **SAF-T Exports**, and then choose **SAF-T Exports**.  
2. On the **SAF-T Exports** page, choose **Create**.
3. On the **SAF-T Export** page, in the **Mapping Range Code** field, choose the mapping range for which to define an export.
5. To start the SAF-T export, do one of the following: 
   * To export immediately, choose **Start**.
   * To schedule the export to be handled by the jobs in the Job Queue, choose **Parallel Processing**. Exporting G/L entries can take time. To speed up the process, consider specifying how many jobs to run in parallel. 
6. To check the status of the SAF-T file generation, look at the **Lines** section in the lower part of this page. 
7. When all files are generated, choose **Download file** to download a .zip file that contains the SAF-T files. This file is ready to be uploaded to Skatteetaten.

> [!Note]
> SAF-T exports will generate one file with master data, and separate files for each of the months included in the selected mapping range. Consider the amount of transactions in the selected period and adjust the **Max No. of Jobs** accordingly on the SAF-T Export page. As a general recommendation, start with three parallel jobs to allow parallel export and still leave resources for other [!INCLUDE[d365fin](../../includes/d365fin_md.md)] users. Additionally, for on-premises, you can specify a network share in the **Folder path** to generate the SAF-T files directly on a network share instead of in the database. For online versions of [!INCLUDE[d365fin](../../includes/d365fin_md.md)] this is always the case. If you specify the **Folder Name**, the generated .zip file will be located here. 

## See Also
[Customizing [!INCLUDE[d365fin](../../includes/d365fin_md.md)] Using Extensions](../../ui-extensions.md)  
[Getting Started](../../product-get-started.md)
