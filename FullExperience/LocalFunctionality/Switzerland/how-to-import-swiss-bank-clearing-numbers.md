---
title: "How to: Import Swiss Bank Clearing Numbers"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "bank branch numbers, defining"
  - "bank clearing numbers, importing"
ms.assetid: 81b24476-1d38-4282-ad2c-e577b8bf6d4a
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "de-ch"
  - "fr-ch"
---
# How to: Import Swiss Bank Clearing Numbers
Bank clearing numbers are unique numbers used to identify each bank agency or branch in the bank directory. This information is required for electronic payment. The file can be downloaded from the [SIX Interbank Clearing](http://go.microsoft.com/fwlink/?LinkId=145121) website.  
  
 You can import the BC Bank Master file—the official Swiss bank clearing number file—to update the bank clearing number information in the bank directory. When you import the bank clearing number file, the data is imported to the **\($ T\_11500 Bank Directory $\)** table, and the existing data is overwritten. After importing the bank clearing number file, you can define the updated bank branch number for customers and vendors. For more information, see the [\($ T\_287 Customer Bank Account $\)](../../Sales/-$-t_287-customer-bank-account-$-.md) table and the [\($ T\_288 Vendor Bank Account $\)](../Topic/\($%20T_288%20Vendor%20Bank%20Account%20$\).md) table.  
  
### To import Swiss bank clearing numbers  
  
1.  In the **Search** box, enter **Bank Directory**, and choose the related link.  
  
2.  On the **Home** tab, in the **Process** group, select **Import Bank Directory**.  
  
3.  In the **\($ B\_11504 Import Bank Directory $\)** window, on the **Options** FastTab, select the **\($ B\_11504\_N\_2\_1150004 Automatically Update Clearing Numbers $\)** field to update the bank clearing numbers automatically.  
  
4.  Choose the **Print** button or the **Preview** button to import the bank clearing numbers, and then, in the **Open** window, locate the file that you have downloaded from the SIX Interbank Clearing website. Choose the **Open** button.  
  
     If you choose the **Print** button, the contents of the file will be printed. If you choose the **Preview** button, the **\($ T\_11500 Bank Directory $\)** table will be updated and a report that has clearing numbers that have changed will be displayed.  
  
 The following procedure describes how to define bank branch numbers for customer bank accounts, but the same steps also apply for defining bank branch numbers for vendor bank accounts.  
  
### To define bank branch numbers for customer bank accounts  
  
1.  In the **Search** box, enter **Customers**, and then choose the related link.  
  
2.  Select the customer for whom you want to create bank account information, and on the **Navigate** tab, in the **Customer** group, select **Bank Accounts**.  
  
3.  In the **\($ N\_424 Customer Bank Account List $\)** window, select the required bank account, and on the **Home** tab, select **Edit**.  
  
4.  On the **General** FastTab, in the **\($ T\_287 Bank Branch No. $\)** field, select the number of the bank agency or branch.  
  
5.  Choose the **OK** button.  
  
## See Also  
 [Swiss Electronic Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/swiss-electronic-payments.md)   
 [\($ T\_11500 Bank Directory $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/-$-t_11500-bank-directory-$-.md)   
 [\($ T\_287 Customer Bank Account $\)](../../Sales/-$-t_287-customer-bank-account-$-.md)   
 [\($ T\_288 Vendor Bank Account $\)](../Topic/\($%20T_288%20Vendor%20Bank%20Account%20$\).md)   
 [How to: Set Up Vendor Bank Accounts](../../Purchasing/how-to-set-up-vendor-bank-accounts.md)