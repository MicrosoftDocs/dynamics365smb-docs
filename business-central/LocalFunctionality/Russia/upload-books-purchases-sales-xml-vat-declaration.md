---
title: Upload books of purchases and sales in Russia
description: Russian enhancements include books of purchases and sales VAT in XML format.
author: DianaMalina
ms.topic: how-to
ms.search.keywords: VAT declaration, VAT report, XML, upload books, purchases, sales, additional sheets, Russia
ms.date: 07/22/2025
ms.reviewer: v-soumramani
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Upload books of purchases and sales and the VAT declaration in XML format

To upload VAT reports to XML files, you must configure the folder where the files are uploaded.

Go to **Statutory Report Setup** and fill **Excel Reports Folder Name** and **Electronic Files Folder Name**.

## VAT declaration

The VAT Declaration file is formed on the basis of the generated data on VAT Purchase Ledgers or VAT Sales Ledgers, additional sheets, and the journal of invoices.

For the correct formation of the VAT Declaration is necessary:

1. Generate VAT Purchase Ledgers or VAT Sales Ledgers, additional sheets for the required period (see [Create VAT Ledgers](How-to-Create-VAT-Ledgers.md)).

1. Correct the data of VAT Purchase Ledgers or VAT Sales Ledgers, if necessary.

1. Generate and check the journal of invoices.

1. Upload purchase and sales books, and additional sheets in XML format.

1. Upload the journal of issued and received invoices (if there are operations for the period) in XML format.

1. Generate the VAT Declaration in XML format.

1. The generated files are located in the folder specified in the setting **Statutory Report Setup, Electronic Files Folder Name.**

## Upload purchase and sales books, and additional sheets to XML files

To upload VAT Purchase Ledgers or VAT Sales Ledgers to XML, you need to stand on the line with the generated VAT Ledger, select **Print, Export XML** (to upload the book).

The system generates an XML file in the folder specified in the settings and fill the Name of XML file field for the book.

You should upload additional sheets to XML only if they aren't empty.

For unloading of additional sheets of VAT Purchase Ledgers or VAT Sales Ledgers in the XML you need to stand on the line with the generated  VAT Ledger, select **Print, Export additional sheet XML** (for upload of additional sheet in the workbook in XML).

The system generates an XML file in the folder specified in the settings and fill the Name of XML file field for the additional sheet.

## Uploading VAT declaration to XML

To generate a Declaration file, go to **Departments -> VAT Declaration -> Export VAT Declaration to XML**:

To calculate and upload a file, you must specify:

- **Year** 
- **Period type** – Quarter if the Declaration is submitted quarterly
- **Period number**

In the **VAT purchase ledgers** and **VAT sales ledgers** fields, you must select the generated purchase and sales books.

If the books don't appear in the selected period, you can remove the filter and all the books are available for selection.

The system automatically completes the data on the names of XML files for VAT Purchase Ledgers, VAT Sales Ledgers, and additional sheets on the basis of previously unloaded files:

- XML Purchase Ledgers name
- XML Sales Ledgers name
- XML Sales Ledgers additional sheet name
- XML Purchase Ledgers additional sheet name

**Place Code** – you must specify the location code of the organization.

**SignatoryNo** – choose the code of the employee.

**Tax Auth No** – specify the code of the tax authority where the Declaration is submitted.

To upload the Declaration, select **OK** in the lower right corner of the form.

The generated file is located in the folder specified in the configuration **Statutory Report Setup, Electronic Files Folder Name**.

## Related information

[Russia Local Functionality](russia-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
