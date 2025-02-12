---
title: Export data for auditing
description: This article explains how to set up different export formats and then use them, based on auditor or authority requirements.
author: altotovi
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.devlang: al
ms.search.keywords: audit, export, SIE, SAF-T, FAC, GDPdU, file export
ms.search.form: 5260, 5261, 5264, 5266, 5267, 5270
ms.date: 08/07/2024
ms.author: altotovi
ms.reviewer: bholtorf
---

# Export data for auditing

Export of bookkeeping information from the system is a common request by some local authorities or auditors. Exports of formats and required information can differ. Entries for export are usually General ledger (G/L) entries or value-added tax (VAT) entries. However, other information is sometimes required.

**Audit Files Export** is a preinstalled extension that lets you export different entries, based on auditor or authority requirements. Regardless of the format type or entries, you can use the extension's functionality to control the data export process. The functionality doesn't have a preinstalled file format for export. Therefore, you must either install an app that has a specific format (for example, SIE, SAF-T, or FAC) or develop your own.

> [!NOTE]
> Currently, you can select SIE (Sweden), FEC (France), and SAF-T format as an additional app. Partners can also develop a custom format. The number of available formats will increase over time.

## Set up audit file export

1. Select the search button ![Magnifying glass button that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do"), enter **Audit File Export Setup**, and then select the related link.
2. On the **Audit File Export Setup** page, follow these steps:

    1. On the **General** FastTab, in the **Audit File Export Format Code** field, specify the code for the default audit file export format. Only those formats that were enabled when a specific file format was installed from Feature management and those that were added as a custom format are available.
    2. On the **Data Quality** FastTab, select the **Check Company Information** checkbox to be notified about company information fields that haven't been set up correctly.
    3. Select the **Check Customer** checkbox to be notified about fields that haven't been set up correctly for specific customers.
    4. Select the **Check Vendor** checkbox to be notified about fields that haven't been set up correctly for specific vendors.
    5. Select the **Check Bank Account** checkbox to be notified about fields that haven't been set up correctly for specific bank accounts.
    6. Select the **Check ZIP Code** checkbox to be notified about a postal code that hasn't been set up correctly.
    7. Select the **Check Address** checkbox to be notified when an address hasn't been set up correctly.
    8. In the **Default ZIP Code** field, enter the postal code to use if no postal code is specified on the customer or vendor card.

3. Select the search button ![Magnifying glass button that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do"), enter **Audit File Export Format Setup**, and then select the related link.
4. On the **Audit File Export Format Setup** page, follow these steps:

    1. Select the audit file export format that you want to configure. Only those formats that were enabled when a specific file format was installed from Feature management and those that were added as a custom format are available.
    2. In the **Audit File Name** field, specify the default file name or the file name template for the audit file that you want to export.
    3. Select the **Archive to Zip** checkbox to automatically zip exported files.

## Provide the G/L account mapping for audit file export

Most formats that are required by authorities for G/L accounts require a specific standard chart of accounts. Therefore, after you configure your G/L accounts, your exported file will be based on the mappings. You can use more mappings in your system.

Follow these steps to provide the G/L account mapping for audit file export.

1. Select the search button ![Magnifying glass button that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do"), enter **G/L Account mapping**, and then select the related link.
2. On the **G/L Account Mapping** page, select **New** to create a mapping.
3. In the **Code** field, specify the mapping code that represents the reporting period.
4. In the **Standard Account Type** field, select the type of standard G/L accounts.
5. In the **Audit File Export Format** field, specify the audit file export format that the standard G/L accounts are linked to.
6. In the **Period Type** field, the system specifies an accounting period or a custom period type that has a flexible start date and time, based on your selection. If you select a specific accounting period, the field will be set to **Accounting Period**. Otherwise, it will be set to **Data Range**.
7. In the **Accounting Period** field, specify the start date of the accounting period that will be used as the reporting period, if you want them to be the same.
8. If you set the **Accounting Period** field, the **Starting Date** and **Ending Date** fields are automatically set, based on the period that you specified. Otherwise, you can manually set the start and end dates for your reporting.
9. If you've already added a standard chart of accounts, follow these steps:

    1. In the **Standard Account Category No.** field, specify the category of the standard account or grouping code that's used for mapping.
    2. In the **Standard Account No.** field, specify the standard account code or grouping code that's used for mapping.

10. Select the **Include Incoming Balance** checkbox to consider the incoming balance of the G/L account of the **Balance Account** type for mapping instead of the reporting period's net change.
11. To start the mapping, follow these steps:

    1. To generate lines on the **G/L Account Mapping** page, based on an existing chart of accounts, select **Initialize Source for Mapping**. To copy the G/L account mapping from some another mapping code, select **Copy from Another Mapping**. When you've finished creating lines, all G/L accounts that have posted entries will be marked in green.
    2. To mark only G/L accounts that have entries, select **Update G/L Entry Availability**. If the **Include Incoming Balance** option is enabled, all posted G/L entries are considered for calculation. Otherwise, only G/L entries of the reporting period are considered.

## Export the audit file

1. Select the search button ![Magnifying glass button that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do"), enter **Audit File Export Documents**, and then select the related link.
2. On the **Audit File Export Documents** page, select **New**.
3. On the **General** FastTab, follow these steps:

    1. In the **Audit File Export Format** field, select the format that's used to export the audit file.
    2. In the **G/L Account Mapping Code** field, select the G/L account mapping code for the reporting period.
    3. Select the **Split By Month** checkbox if multiple audit files should be generated per month.
    4. Select the **Split By Date** checkbox if multiple audit files should be generated per day.
    5. In the **Header Comment** field, enter the comment to include on the audit file header.
    6. In the **Contact** field, specify the contact that's exported to the header of the audit file.
    7. Select the **Create Multiple Zip Files** checkbox to generate multiple zip files.

        > [!IMPORTANT]
        > Select this checkbox only if you previously installed some of the format apps or created a custom one. Installation of one or more of the specific formats will likely add fields and functions to the **Audit Files Export** functionality, based on the format requirements.

4. On the **Processing** FastTab, follow these steps:

    1. Select the **Parallel Processing** checkbox if you want audit file generation to be processed by parallel background jobs. Clear the checkbox to export data in your current session.
    2. If you selected the **Parallel Processing** checkbox, in the **Max No. Of Jobs** field, specify the maximum number of background jobs that can be run at the same time.
    3. In the **Earliest Start Date/Time** field, specify the earliest date and time when the background job must be run. If you run the process by selecting **Start**, you can track the status on the **Processing** and **Lines** FastTabs.

5. When you've finished, select **Download as File** to download the audit file for the selected line.

> [!IMPORTANT]
> If you have multiple entries to export, we don't recommend that you export them in the current session, because of possible performance issues. Instead, we recommend that you use parallel processing during non-working days or hours.

## See also
[Financial Management](finance.md)    
[Understanding the General Ledger and Chart of Accounts](finance-general-ledger.md)    
[Work with Dimensions](finance-dimensions.md)    
[Work with Business Central](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
