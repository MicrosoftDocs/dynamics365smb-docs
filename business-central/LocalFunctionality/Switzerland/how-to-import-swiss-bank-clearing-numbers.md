---
title: Import Swiss Bank Clearing Numbers in the Swiss Version [CH]
description: Import Swiss bank clearing numbers from CSV or legacy files in Business Central, review changed numbers, and update customer and vendor bank accounts.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: clearing numbers, bank clearing numbers, import bank clearing numbers, Swiss version
ms.search.form: 11501
ms.date: 10/19/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Import Swiss bank clearing numbers in the Swiss version

Bank clearing numbers are unique numbers used to identify each bank agency or branch in the bank directory. This information is required for electronic payment. The file can be downloaded from the [SIX Interbank Clearing](https://go.microsoft.com/fwlink/?LinkId=145121) website.  

You can import a semicolon-delimited CSV V3 bank directory file with a header that starts with `IID`, or a legacy fixed-width bank directory file. The import updates the **Bank Directory** table. After importing the file, you can define the updated bank branch number for customers and clearing number for vendors.

## Import Swiss bank clearing numbers  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Bank Directory**, and choose the related link.  
1. Choose the **Import Bank Directory** action.  
1. In **File Name**, choose the assist-edit button and select the downloaded bank directory file.
1. On the **Import Bank Directory** page, on the **Options** FastTab, select the **Automatically Update Clearing Numbers** field to update the bank clearing numbers automatically.  
1. Choose **Print** or **Preview** to run the import and review the report.

   Both actions update the bank directory. **Automatically Update Clearing Numbers** controls whether related account and payment setup records are also updated. If you leave this option off, use the report to review outdated clearing numbers and update the affected records manually.

## Define bank branch numbers for customer bank accounts

The following procedure describes how to define bank branch numbers for customer bank accounts. For vendor bank accounts, use **Clearing No.** instead.

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Customers**, and then choose the related link.  
1. Select the customer for whom you want to create bank account information, and then choose the **Bank Accounts** action.  
1. On the **Customer Bank Account List** page, select the required bank account, and then choose the **Edit** action.  
1. On the **General** FastTab, in the **Bank Branch No.** field, select the number of the bank agency or branch.  
1. Choose the **OK** button.  

## Related information

- [Swiss Electronic Payments](swiss-electronic-payments.md)  
- [Set Up Bank Accounts](../../bank-how-setup-bank-accounts.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
