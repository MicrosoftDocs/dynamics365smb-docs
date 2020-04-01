---
    title: Electronic Accounting Regulations in Mexico
    description: Learn how Business Central helps you comply with electronic accounting requirements in Mexico.
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: bholtorf

---
# Complying with Electronic Accounting Regulations in Mexico
In Mexico, individuals and businesses must do their bookkeeping electronically and forward their monthly results to the Mexican Tax Authorities (SAT) as separate XML files at the end of each month. The XML files must contain the following:

* The chart of accounts. This file is to be submitted whenever the chart of accounts has been modified.  
* The trial balance, including opening balances, movements (debit / credit), and final balances.  
* All journal transactions, including all actual movements, such as purchases, sales, and so on. This file is to be submitted upon request from the authorities.

For more information about the structure of these files (also referred to as Annex 24), see the Secretaria de Gobernación website. The **Export Elect. Accounting** functionality has been developed to meet this regulatory requirement.

## Setup Data Required to Export Successfully
To export the G/L balance information successfully, you must first set up certain data. Missing data will result in a warning message that some mandatory fields are blank, but the export will not be canceled. If in doubt, you can submit the file to the authorities to get more details about the missing values. The following describes the fields to fill in before you export the XML files.

For the files that contain the chart of accounts and the trial balance:
1. For each account, you must specify an account in the **SAT Account Code** field. Only accounts with a SAT account code are included in the files for the chart of accounts and trial balance. 
2. Every G/L account that is used for export must be defined as either **Debit** or **Credit**. You cannot choose the **Both** option.

For the file that contains journal transactions:
* On the **Customer Bank Account Card**, **Vendor Bank Account Card**, and **Bank Account** pages you must choose a bank in the **Bank Code** field. This is required if the bank account is used in a transaction. 
* On the **Customer** and **Vendor** pages, you must choose an account in the **Preferred Bank Account** field. When a preferred bank account is set for a customer or vendor, that bank account is copied to the Recipient Bank Account field whenever a payment to a vendor or a cash receipt from a customer is created. This default value can be changed on the journal lines before posting.
* The **Fiscal Invoice Number PAC** field on all purchase documents is used to register the UUID of an electronic invoice. You can import electronic invoices (response) when you create a purchase invoice, order, or credit memo. Only the UUID is imported, but this functionality can easily be expanded. After data is imported it appears on the invoice after posting.
* On the **Payment Method** page, in the **SAT Method of Payment** field you must specify how payment was made.

## To generate the XML files
1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Export Elect. Accounting**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]

## See Also
[Mexico Local Funcationality](mexico-local-functionality.md)
