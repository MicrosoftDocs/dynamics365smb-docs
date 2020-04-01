---
title: Upload books of purchases and sales in Russia
description: Russian enhancements include books of purchases and sales VAT in XML format.
author: DianaMalina

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 04/01/2020
ms.reviewer: edupont
ms.author: soalex
---

# Upload Books of Purchases and Sales and the VAT Declaration in XML Format

To upload VAT reports to XML files, you must configure the folder where the files will be uploaded.

Go to **Statutory Report Setup** and fill **Excel Reports Folder Name** and **Electronic Files Folder Name**.

## VAT Declaration

The VAT Declaration file is formed on the basis of the generated data on VAT Purchase Ledgers or VAT Sales Ledgers, additional sheets and the journal of invoices.

For the correct formation of the VAT Declaration is necessary:

1. Generate VAT Purchase Ledgers or VAT Sales Ledgers, additional sheets for the required period (see [Create VAT Ledgers](How-to-Create-VAT-Ledgers.md)).

2. Correct the data of VAT Purchase Ledgers or VAT Sales Ledgers, if necessary.

3. Generate and check the journal of invoices.

4. Upload purchase and sales books, as well as additional sheets in XML format.

5. Upload the journal of issued and received invoices (if there are operations for the period) in XML format.

6. Generate the VAT Declaration in XML format.

7. The generated files will be located in the folder specified in the setting **Statutory Report Setup, Electronic Files Folder Name.**

## Upload purchase and sales books, and additional sheets to XML files

To upload VAT Purchase Ledgers or VAT Sales Ledgers to XML, you need to stand on the line with the generated VAT Ledger, click Print, Export XML (to upload the book).

The system will generate an XML file in the folder specified in the settings and fill the Name of XML file field for the book.

You should upload additional sheets to XML only if they are not empty.

For unloading of additional sheets of VAT Purchase Ledgers or VAT Sales Ledgers in the XML you need to stand on the line with the generated  VAT Ledger, click Print, Export additional sheet XML (for upload of additional sheet in the workbook in XML).

The system will generate an XML file in the folder specified in the settings and fill the Name of XML file field for the additional sheet.

## Uploading VAT Declaration to XML

To generate a Declaration file, go to **Departments -> VAT Declaration -> Export VAT Declaration to XML**:

To calculate and upload a file, you must specify:

- **Year** 
- **Period type** – Quarter if the Declaration is submitted quarterly
- **Period number**

In the **VAT purchase ledgers** and **VAT sales ledgers** fields, you must select the generated purchase and sales books.

If the books do not appear in the selected period, you can remove the filter and all the books will be available for selection.

The system automatically completes the data on the names of XML files for VAT Purchase Ledgers, VAT Sales Ledgers and additional sheets on the basis of previously unloaded files:

- XML Purchase Ledgers name
- XML Sales Ledgers name
- XML Sales Ledgers additional sheet name
- XML Purchase Ledgers additional sheet name

**Place Code** – you must specify the location code of the organization.

**SignatoryNo** – choose the code of the employee.

**Tax Auth No** – specify the code of the tax authority where the Declaration is submitted.

To upload the Declaration, click OK in the lower right corner of the form.

The generated file will be located in the folder specified in the configuration **Statutory Report Setup, Electronic Files Folder Name**.

## See Also

[Russia Local Functionality](russia-local-functionality.md)  
