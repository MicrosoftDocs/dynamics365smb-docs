---
title: Setup and generate SAF-T files
description: Use the SAF-T extension to set up and generate SAF-T files for the Norwegian authorities in Business Central.
author: sorenfriisalexandersen
ms.topic: install-set-up-deploy
ms.devlang: al
ms.search.keywords: extension, saf-t, authorities, export, compliance
ms.search.form: 10670, 10671, 10672, 10673, 10674, 10675, 10677, 10678, 10679, 10680, 10685, 10686, 10687, 10688, 10689, 10690, 10691, 
ms.date: 05/16/2025
ms.author: soalex
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Standard audit files - tax

Starting in January, 2020, companies in Norway must report financial data and provide a set of Standard Audit Files - Tax (SAF-T) to the Norwegian authorities upon request. This extension makes it easy to set up, generate, and export Standard Audit Files - Tax in [!INCLUDE[prod_short](../../includes/prod_short.md)]. The exported SAF-T files are automatically compressed as a .zip file ready to be uploaded by the user on the website of Skatteetaten, the Norwegian tax authorities.  

> [!NOTE]
> Starting with version 25.3, [!INCLUDE[prod_short](../../includes/prod_short.md)] in Norway supports SAF-T versions 1.20 and 1.30, as the newer version is required in 2025. Earlier versions only support the SAF-T 1.20 format.

## What does this extension handle?

This extension provides the following capabilities:

* Choosing SAF-T version for reporting.
* Setup and mapping of chart of accounts to SAF-T standard accounts.
* Mapping VAT setup to SAF-T VAT codes.
* Control to which extent dimensions are exported in SAF-T files.
* Export SAF-T files, either directly or by using the Job Queue. Using Job Queue lets you schedule the export to occur during quiet hours, which is useful for potentially large datasets.

## Setup of the Norwegian SAF-T extension

Set up the SAF-T extension through Assisted Setup, which provides an easy, step-by-step guide for get started with SAF-T in [!INCLUDE[prod_short](../../includes/prod_short.md)]. If needed, you can run the guide several times until you finish the setup.

1. In [!INCLUDE[prod_short](../../includes/prod_short.md)], choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Assisted Setup**, and then choose **Assisted Setup**.  
1. Choose **Set up SAF-T**.
1. The first page in the setup guide explains what you are about to set up. Choose **Next**.
1. Choose the SAF-T version you want to use for reporting.  
1. In the in **Mapping Type** field, choose the type of Chart of Accounts you want to SAF-T accounts, and then choose **Next**.

   > [!Note]
   > If you are using the on-premises version of [!INCLUDE[prod_short](../../includes/prod_short.md)], there are some additional steps.
   > 1. Download and import source files with SAF-T accounts. Download the SAF-T mapping files from [Skatteetaten's repo on Github](https://github.com/Skatteetaten/saf-t).
   > 1. Choose **Import The Source Files For Mapping**.
   > 1. Import all required files. If you are setting up the mapping for income statement import files, make sure to import mapping codes for all records with **Income Statement** in the **Source Type** column.
   > 1. For each imported file, choose **Update mapping codes from file**.

1. To define the period for the first SAF-T reporting, choose **Accounting Period**, confirm the data range, and then choose **Next**.

   Typically, this is done for a specific accounting period, but you can also define a date range without specifying an accounting period.

1. To map your chart of accounts to the SAF-T accounts, choose **Open setup to define G/L account mappings**. Lines where the G/L Account No. is marked with green indicates that here are transactions on the account within the date range specified in the previous step, in which case it must be mapped. Other G/L accounts can be skipped. When finished, close the **SAF-T Mapping Setup Card**, and then choose **Next** in the setup guide.
1. To map the VAT Posting Setup to standard sales and purchase SAF-T tax codes, choose **Open setup to define VAT Posting Setup Mapping**. When finished close the **SAF-T VAT Posting Setup card**, and then choose **Next** in the setup guide.
1. Norwegian authorities recommend that you export dimensions for financial transactions. However, in some situations you may not want to export dimensions - for example if you have internal dimensions that do provide value to auditors. This step lets you open the Dimensions list and choose which dimensions to export. Choose the value in the **Export to SAF-T** field, and then choose **Close**.
1. To specify the employee who is the SAF-T contact in your company, choose the employee in the **Employee No.** field. This is useful when Norwegian authorities have questions about the SAF-T files. When finished, choose **Next**.
1. The setup of SAF-T is now finished. Choose **Finish**.

> [!Note]
> The mappings are tied to the date range you specified. You can create additional mappings for other periods without changing the mapping you already created. You can also copy mappings from previously made setups. This is to ensure that you can report SAF-T for different periods while managing changes in your chart of accounts.

## Exporting SAF-T files

To export SAF-T files from [!INCLUDE[prod_short](../../includes/prod_short.md)], you must first create and set up a **SAF-T Export** to define the mapping range. For example, you can define a mapping and export the entire year of 2019, and another mapping for just the month of April 2019 if the authorities ask you to provide this data specifically.

### Create an export of SAF-T files

1. In [!INCLUDE[prod_short](../../includes/prod_short.md)], choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **SAF-T Exports**, and then choose **SAF-T Exports**.  
1. On the **SAF-T Exports** page, choose **Create**.
1. On the **SAF-T Export** page, choose the SAF-T version and in the **Mapping Range Code** field, choose the mapping range for which to define an export.
1. To start the SAF-T export, do one of the following actions:
   * To export immediately, choose **Start**.
   * To schedule the export to be handled by the jobs in the Job Queue, choose **Parallel Processing**. Exporting G/L entries can take time. To speed up the process, consider specifying how many jobs to run in parallel.
1. To check the status of the SAF-T file generation, look at the **Lines** section in the lower part of this page.
1. When all files are generated, choose **Download file** to download a .zip file that contains the SAF-T files. This file is ready to be uploaded to Skatteetaten.

### SAF-T files and data quality

You can configure [!INCLUDE[prod_short](../../includes/prod_short.md)] with extra data quality validation controls that help make sure that your SAF-T files can be validated by Skatteetaten. For example, SAF-T files can only be validated when certain information exists on relevant records in [!INCLUDE[prod_short](../../includes/prod_short.md)]. To help ensure data quality for SAF-T, you can enable more proactive controls on the **Data Quality** FastTab on the **SAF-T Setup** page. Additionally, on the **SAF-T Export** card page, use the **Data check** action to check the data quality before you export the file.

> [!NOTE]
> SAF-T exports by default generate one file with master data, and separate files for each of the months included in the selected mapping range. Consider the amount of transactions in the selected period and adjust the **Max No. of Jobs** accordingly on the SAF-T Export page. As a general recommendation, start with three parallel jobs to allow parallel export and still leave resources for other [!INCLUDE[prod_short](../../includes/prod_short.md)] users. Additionally, for on-premises, you can specify a network share in the **Folder path** to generate the SAF-T files directly on a network share instead of using the database. For online versions of [!INCLUDE[prod_short](../../includes/prod_short.md)] this is always the case. If you specify the **Folder Name**, the generated .zip file is located here.
> [!IMPORTANT]
> Due to the nature of exporting transactions, exporting SAF-T files impacts performance of [!INCLUDE[prod_short](../../includes/prod_short.md)].

There are a couple of things you can do to improve performance:

* **Split by Date** option

   This approach collects general ledger entries by date, not by month as is the default with better performance as a result.

* **XML** option

   For [!INCLUDE[prod_short](../../includes/prod_short.md)] on-premises, you have an option to not generate .ZIP files from the export. This exports the raw XML files and is only possible where there's a **Folder Path** to export to. The user can then compress the files manually, which saves server performance. SAF-T files can be large and compressing them to a .ZIP file is a costly operation for the server.

* **Create Multiple Zip Files** option

   Finally, for both online and on-premises, for large exports with many transactions, you can also use the option to create multiple .ZIP files. This is useful if individual files per month are large, or the count of files per date is too big. Use this option when the single large ZIP file doesn't validate on the authorities' web site due to its size, for example. Using this feature splits up the export into multiple ZIP files, up to 10 in alignment with the requirements that are stated in the general SAF-T documentation. The **SAF-T Export File** page is always opened when using the **Download File** action. Here you can see how many files were generated and download them one by one.  

## Related information

- [Customizing [!INCLUDE[prod_short](../../includes/prod_short.md)] Using Extensions](../../ui-extensions.md)  
- [Getting Ready for Doing Business](../../ui-get-ready-business.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
