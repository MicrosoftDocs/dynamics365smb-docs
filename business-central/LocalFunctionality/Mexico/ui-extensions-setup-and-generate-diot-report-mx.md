---
title: Set Up and Generate DIOT Reports
description: Set up vendor operation types and VAT concept links, then export a 54-field DIOT declaration from Business Central for the Mexican tax authorities.
author: jswymer
ms.topic: how-to
ms.devlang: al
ms.search.keywords: extension, DIOT, authorities, export, compliance, DIOT declarations, DIOT reports
ms.search.form: 27030, 27031, 27032, 27033, 27034
ms.date: 10/20/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up and generate DIOT reports

As a company in Mexico, you must report VAT from vendor purchases to the Mexican government, to SAT - Servicio de Administración Tributaria. This can be done in [!INCLUDE[prod_short](../../includes/prod_short.md)] by generating a file that can be uploaded to SAT. This article describes how to set up the functionality and generate the report. The DIOT (Declaración Informativa de Operaciones con Terceros) report functionality is created as an extension (app) for [!INCLUDE[prod_short](../../includes/prod_short.md)] and is preinstalled in the online version. However, it must be installed manually in the on-premises version of [!INCLUDE[prod_short](../../includes/prod_short.md)].

> [!NOTE]
> Starting with version 26.3, the exported DIOT file complies with the new SAT regulations effective in 2025. The file is in TXT format and includes 54 fields.

## What does this extension handle?

The extension provides the following capabilities:

* Setup of the DIOT-related information
* Vendor settings
* Export the DIOT report so it can be uploaded to the authorities

## Setup of the Mexican DIOT extension

You set up the DIOT extension through Assisted Setup, which provides an easy, step-by-step guide for getting started with DIOT in [!INCLUDE[prod_short](../../includes/prod_short.md)]. If needed, you can run the guide several times until the setup is completed.

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Assisted Setup**, and then choose the related link.
1. Select **Set up DIOT reporting**.
1. The first page in the setup guide explains what you are about to set up. Choose the **Next** button.
1. In **Default Vendor DIOT Type of Operation**, select the default operation type, and then select **Next**.

    A nonblank default updates all existing vendors when you leave this step and applies to new vendors. Review the existing values before you rerun the guide. Don't select **Lease and Rent** if you have vendors outside Mexico.
1. Choose the **Open Vendor List** action to select another **Type of Operation** value individually for vendors if you want the setting to be different from what you chose in the previous step.

    The vendor list includes **DIOT Type of Operation**. Close the list when you're finished.
1. Select **Next**, and then select **Open DIOT Concepts** to configure how VAT entries are collected for the report.

    You'll see a list of predefined DIOT concepts that look like VAT setup. These DIOT concepts must be linked to VAT product posting groups and VAT business posting groups. You may not have to link all of the DIOT concepts. Investigate each DIOT concept and decide how these map to your VAT posting setup.

    Select **VAT Links Count** to open **DIOT Concept Links**. Add the combinations of **VAT Business Posting Group** and **VAT Product Posting Group** that belong to the concept. Link only the concepts that apply to your transactions. Concepts with **Column Type** set to **None** are disabled and can't have links. A zero link count on an enabled concept means that no VAT posting setup is linked to it.

1. Close **DIOT Concepts**, and then select **Next**.
1. Choose the **Finish** button.

### Choose the operation type

The report supports the following operation types. The captions match the values shown in [!INCLUDE[prod_short](../../includes/prod_short.md)].

|DIOT Type of Operation|Exported code|
|----------------------|-------------|
|**Prof. Services**|03|
|**Lease and Rent**|06|
|**Others**|85|
|**Transfer of Goods**|02|
|**Import of Goods or Services**|07|
|**Import by Virtal Transfer**|08|
|**Global Operations**|87|

Every reported operation needs an operation type. **Lease and Rent** is only valid for vendors in Mexico.

## Vendor setup

> [!NOTE]
> The vendor's **DIOT Type of Operation** is copied to a purchase document when the pay-to vendor is validated. You can change the value before posting. The report uses the type stored on the VAT entry. If that value is blank, it uses the vendor's current operation type.

To update necessary fields on the **Vendor** card, perform the following steps:

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Vendors**, and then select the related link.
1. Open the vendor card and verify **Country/Region Code**. Use **MX** for vendors in Mexico and fill in **RFC No.** for these vendors.
1. Set **DIOT Type of Operation** to the appropriate value.
1. Select **Tax Effects Applied** if tax effects are applied to invoices for transactions with the vendor. The 54th field exports `01` when the field is selected and `02` otherwise.
1. Fill in **Tax Jurisdiction Location** for a foreign vendor whose country/region maps to **ZZZ** in the DIOT export.

The report maps a foreign vendor's country/region through **DIOT Country/Region Data**. If it can't find a mapping, it exports **ZZZ** and includes **Tax Jurisdiction Location**. You don't need to set the vendor's **Country/Region Code** to **ZZZ** to edit this field.

## Optional setup for reporting withholding tax with the DIOT extension

The DIOT report can include withholding tax amounts for vendor transactions. The DIOT extension's withholding percentage affects reporting only. It doesn't calculate or post withholding tax. If you record withholding tax by posting extra lines to a predefined G/L account, continue that process.

Use **DIOT WHT %** on **VAT Posting Setup** to specify the withholding percentage used by the report for entries with that posting setup.

For example, if you have transactions that are supposed to be 10% VAT and 5% withholding tax, use a posting setup where the **VAT %** field contains *10* and the **DIOT WHT %** field contains *5*.  

This field will only affect the DIOT report calculations and not the actual posting of the lines/entries/documents, so you must continue the existing workaround that you may have for calculating withholding tax, regardless of setting up the DIOT Report extension.

The **DIOT WHT %** value can't exceed **VAT %**.

## Create an export of DIOT report files

Complete the assisted setup before you run the report. The report collects purchase VAT entries for the selected posting dates and the linked VAT posting setups. For setups with unrealized VAT, it collects entries that realize VAT. Otherwise, it collects invoice entries.

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Create DIOT Report**, and then choose the related link.  
1. On the **Create DIOT Report** request page, fill in **Starting Date** and **Ending Date**. Both dates are required, and the ending date can't be before the starting date.
1. Choose the **OK** button.

    If the report lists errors, correct them and run it again. For example, vendors in Mexico need **RFC No.** on the **Payments** FastTab of the **Vendor Card**.

When the report runs without errors and finds data, save `diot.txt` for submission to SAT. Each line represents one vendor and operation type. The file has 54 pipe-separated fields, and amounts are rounded to whole numbers. If no data matches, the report shows a message instead of downloading a file.

## Related information

- [Customizing [!INCLUDE[prod_short](../../includes/prod_short.md)] Using Extensions](../../ui-extensions.md)  
- [Getting Ready for Doing Business](../../ui-get-ready-business.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
