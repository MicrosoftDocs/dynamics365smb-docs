---
title: Import Swiss Bank Clearing Numbers [CH]
description: Learn how to import Swiss Bank Clearing Numbers using the Swiss version of Business Central. 
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: clearing numbers, bank clearing numbers, import bank clearing numbers, Swiss version
ms.search.form: 11501
ms.date: 04/29/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Import Swiss bank clearing numbers in the Swiss version

Bank clearing numbers are unique numbers used to identify each bank agency or branch in the bank directory. This information is required for electronic payment. The file can be downloaded from the [SIX Interbank Clearing](https://go.microsoft.com/fwlink/?LinkId=145121) website.  

You can import the BC Bank Master .txt file—the official Swiss bank clearing number file—to update the bank clearing number information in the bank directory. When you import the bank clearing number file, the data is imported to the **Bank Directory** table, and the existing data is overwritten. After importing the bank clearing number file, you can define the updated bank branch number for customers and vendors. For more information, see the Customer Bank Account table and the Vendor Bank Account table.  

## Import Swiss bank clearing numbers  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Directory**, and choose the related link.  
1. Choose the **Import Bank Directory** action.  
1. Choose the **...** button to open the .txt bank clearing number file.
1. On the **Import Bank Directory** page, on the **Options** FastTab, select the **Automatically Update Clearing Numbers** field to update the bank clearing numbers automatically.  
1. Choose the **Print** button or the **Preview** button to import the bank clearing numbers, and then, on the **Open** page, locate the file that you downloaded from the SIX Interbank Clearing website.
1. Choose the **Open** button.  

   If you choose the **Print** button, the contents of the file is printed. If you choose the **Preview** button, the **Bank Directory** table is updated and a report that has clearing numbers that have changed is displayed.  

## Define bank branch numbers for customer bank accounts

The following procedure describes how to define bank branch numbers for customer bank accounts. The same steps also apply for defining bank branch numbers for vendor bank accounts.  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.  
1. Select the customer for whom you want to create bank account information, and then choose the **Bank Accounts** action.  
1. On the **Customer Bank Account List** page, select the required bank account, and then choose the **Edit** action.  
1. On the **General** FastTab, in the **Bank Branch No.** field, select the number of the bank agency or branch.  
1. Choose the **OK** button.  

## Related information

- [Swiss Electronic Payments](swiss-electronic-payments.md)  
- [Set Up Bank Accounts](../../bank-how-setup-bank-accounts.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
