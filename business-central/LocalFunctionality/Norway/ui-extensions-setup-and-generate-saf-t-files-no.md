---
title: Set Up and Export Norwegian SAF-T Files
description: Set up Norwegian SAF-T mappings in Business Central, choose an export version, and generate XML or ZIP files to provide to the Norwegian tax authorities.
author: jswymer
ms.topic: how-to
ms.devlang: al
ms.search.keywords: extension, saf-t, authorities, export, compliance
ms.search.form: 10670, 10671, 10672, 10673, 10674, 10675, 10677, 10678, 10679, 10680, 10685, 10686, 10687, 10688, 10689, 10690, 10691, 
ms.date: 10/20/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up and export Norwegian SAF-T files

<a name="standard-audit-files---tax"></a>Starting in January, 2020, companies in Norway must report financial data and provide a set of Standard Audit Files - Tax (SAF-T) to the Norwegian authorities upon request. This extension makes it easy to set up, generate, and export Standard Audit Files - Tax in [!INCLUDE[prod_short](../../includes/prod_short.md)]. By default, the exported SAF-T files are automatically compressed as a ZIP file ready for you to upload on the website of Skatteetaten, the Norwegian tax authorities.

> [!NOTE]
> Starting with version 25.3, [!INCLUDE[prod_short](../../includes/prod_short.md)] in Norway supports SAF-T versions 1.20 and 1.30, as the newer version is required in 2025. Earlier versions only support the SAF-T 1.20 format.

## What does this extension handle?

This extension provides the following capabilities:

* Choosing SAF-T version for reporting.
* Setup and mapping of chart of accounts to SAF-T standard accounts.
* Mapping VAT setup to SAF-T VAT codes.
* Control to which extent dimensions are exported in SAF-T files.
* Export SAF-T files, either directly or by using parallel background jobs. Background processing lets you schedule the export to occur during quiet hours, which is useful for potentially large datasets.

## Set up the Norwegian SAF-T extension

Set up the SAF-T extension through **Assisted Setup**, which provides a step-by-step guide to get started with SAF-T in [!INCLUDE[prod_short](../../includes/prod_short.md)]. If needed, you can run the guide several times until you finish the setup.

On the **SAF-T Setup** page, use **Default Version** to choose **1.20** or **1.30** for new exports. You can also change **Version** on each **SAF-T Export**. The assisted setup guide configures mappings, not the export version.

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Assisted Setup**, and then choose **Assisted Setup**.
1. Choose **Set up SAF-T**.
1. The first page in the setup guide explains what you are about to set up. Choose **Next**.
1. In the **Mapping Type** field, choose **Two Digit Standard Account**, **Four Digit Standard Account**, or **Income Statement**, and then choose **Next**. If the source files aren't loaded, import them as described in [Import mapping source files on-premises](#import-mapping-source-files-on-premises) before choosing **Next**.
1. To define the period for the first SAF-T reporting, choose **Accounting Period** to fill in the fiscal year's starting and ending dates, or enter **Starting Date** and **Ending Date** for a custom range. Confirm the dates, and then choose **Next**.
1. To map your chart of accounts to the SAF-T accounts, choose **Open the setup page to define G/L account mappings.** Map every G/L account listed. For accounts without an applicable mapping, use **NA**. For version **1.30**, both **Category No.** and **No.** must be filled in. When finished, close **SAF-T Mapping Setup**, and then choose **Next** in the setup guide.
1. To map the VAT posting setup to standard sales and purchase SAF-T tax codes, choose **Open the setup page to define a VAT Posting Setup mapping.** Assign **Sales VAT Reporting Code** and **Purchase VAT Reporting Code** as relevant to each combination. When finished, close **SAF-T VAT Posting Setup**, and then choose **Next** in the setup guide.
1. Choose **Open the setup page to define which dimensions to export to SAF-T.** On the **Dimensions** page, select **Export to SAF-T** for dimensions to include, and clear it for dimensions to exclude. Close the page, and then choose **Next**.
1. To specify the employee who is the SAF-T contact in your company, choose the employee in the **Employee No.** field. This is useful when Norwegian authorities have questions about the SAF-T files. When finished, choose **Next**.
1. The setup of SAF-T is now finished. Choose **Finish**.

> [!NOTE]
> Both dates must be filled in. **Accounting Period** lets you select the start of a fiscal year, which must have an ending date. Entering either date manually changes **Range Type** to **Date Range**.

Green **G/L Account No.** values identify accounts with a nonzero net change for the range. **Include Incoming Balance** also considers earlier postings for balance sheet accounts. This highlighting doesn't limit which accounts require mapping. For standard-account mapping, you can use **Match chart of accounts** to match existing account numbers. If your chart of accounts is empty, **Create chart of accounts** can create it from the selected standard accounts.

Norwegian authorities recommend that you export dimensions for financial transactions. However, you might want to exclude internal dimensions that don't provide value to auditors. Only dimensions with **Export to SAF-T** selected are included. Export checks still require a **SAF-T Analysis Type** for every dimension, including excluded dimensions. The employee selected as the contact must also be specified before export.

> [!NOTE]
> The mappings are tied to the date range you specified. You can create additional mappings for other periods without changing the mapping you already created. You can also copy mappings from previously made setups. This is to ensure that you can report SAF-T for different periods while managing changes in your chart of accounts.

### Import mapping source files on-premises

For [!INCLUDE[prod_short](../../includes/prod_short.md)] on-premises, load the mapping sources before continuing from the **Mapping Type** step. **Next** is available only when both the selected account-mapping sources and the standard tax code source are loaded.

1. Download the SAF-T mapping files from [Skatteetaten's repository on GitHub](https://github.com/Skatteetaten/saf-t).
1. In the guide, choose **Import the source files for mapping** to open **SAF-T Mapping Source**.
1. Select each required source record, choose **Update**, and import the matching XML file. Include the **Standard Tax Code** source and the sources for your mapping type. For **Income Statement**, import files for all records with that **Source Type**.
1. Close the page, and then choose **Next** in the guide.

## Export SAF-T files

To export SAF-T files from [!INCLUDE[prod_short](../../includes/prod_short.md)], you must first create and set up a **SAF-T Export** to define the mapping range. For example, you can define a mapping and export the entire year of 2019, and another mapping for just the month of April 2019 if the authorities ask you to provide this data specifically.

### Create an export of SAF-T files

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **SAF-T Exports**, and then choose **SAF-T Exports**.
1. On the **SAF-T Exports** page, choose **New**.
1. On the **SAF-T Export** page, choose **Version** and **Mapping Range Code**. The mapping range fills in **Starting Date** and **Ending Date**. Adjust these dates if needed for the requested export.
1. Choose how to process the export:
   * To export immediately in the current session, clear **Parallel Processing**.
   * To use background jobs, select **Parallel Processing**, specify **Max No. Of Jobs**, and set **Earliest Start Date/Time**.
1. Choose **Start**.
1. To check the status of the SAF-T file generation, look at the **Lines** section in the lower part of this page.
1. When all files are generated, choose **Download Files** on the **SAF-T Export** card. On **SAF-T Export Files**, select each file and choose **Download File** to download the ZIP files for upload to Skatteetaten.

> [!NOTE]
> **Parallel Processing** is available only when the task scheduler can create tasks. It is selected by default when tasks are available. If you leave **Earliest Start Date/Time** blank, starting the export prompts you to use the current date and time.

For on-premises exports to a folder, retrieve the generated files from **Folder Path** instead.

### SAF-T files and data quality

You can configure [!INCLUDE[prod_short](../../includes/prod_short.md)] with extra data quality validation controls that help make sure that your SAF-T files can be validated by Skatteetaten. For example, SAF-T files can only be validated when certain information exists on relevant records in [!INCLUDE[prod_short](../../includes/prod_short.md)]. To help ensure data quality for SAF-T, you can enable more proactive controls on the **Data Quality** FastTab on the **SAF-T Setup** page. Additionally, on the **SAF-T Export** card page, use the **Data check** action to check the data quality before you export the file.

Starting an export also checks G/L mappings, dimension analysis types, sales and purchase SAF-T tax codes, source-code mappings, and the company contact. On **Source Codes**, each source code needs a **SAF-T Source Code**. Resolve any errors shown before exporting.

> [!NOTE]
> By default, SAF-T exports generate one XML file with master data and separate XML files for months that contain G/L entries. Consider the number of transactions in the export period and adjust **Max No. Of Jobs** accordingly. As a general recommendation, start with three parallel jobs, which is the default, to leave resources for other [!INCLUDE[prod_short](../../includes/prod_short.md)] users.

For [!INCLUDE[prod_short](../../includes/prod_short.md)] online, XML data and generated ZIP files are stored in the database. **Folder Path** isn't available. On-premises, you can use the database or specify an empty folder accessible to the server, such as a network share, in **Folder Path**. When you specify a folder, the XML files and generated ZIP files are saved there.

> [!IMPORTANT]
> Due to the nature of exporting transactions, exporting SAF-T files impacts performance of [!INCLUDE[prod_short](../../includes/prod_short.md)].

There are a couple of things you can do to improve performance:

* **Split By Date**:

   This option groups general ledger entries by day instead of by month, which can improve performance. It clears **Split By Month**. Only days that contain G/L entries get an export line. If you clear both options, the entries are exported in one XML file for the full range, in addition to the master data file.

* **Disable Zip File Generation**:

   For [!INCLUDE[prod_short](../../includes/prod_short.md)] on-premises, select this option to export raw XML without generating ZIP files. It requires **Folder Path** and clears **Create Multiple Zip Files**. You can compress the XML files manually, which saves server resources. SAF-T files can be large, and compression can affect server performance.

* **Create Multiple Zip Files**:

   For both online and on-premises, this option distributes the XML files across up to 10 ZIP files. This can help when a single ZIP file is too large for the authorities' website. The split is based on the number of XML files, not their size. It doesn't split an individual XML file or guarantee a maximum ZIP file size. The option clears **Disable Zip File Generation**. On the **SAF-T Export** card, **Download Files** opens **SAF-T Export Files**, where you download files one by one. For folder exports on-premises, retrieve the ZIP files from **Folder Path**.

## Related information

- [Customizing [!INCLUDE[prod_short](../../includes/prod_short.md)] Using Extensions](../../ui-extensions.md)  
- [Getting Ready for Doing Business](../../ui-get-ready-business.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
