---
    title: How to Import Swiss Bank Clearing Numbers
    description: Bank clearing numbers are unique numbers used to identify each bank agency or branch in the bank directory. This information is required for electronic payment. The file can be downloaded from the SIX Interbank Clearing website.

    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Import Swiss Bank Clearing Numbers
Bank clearing numbers are unique numbers used to identify each bank agency or branch in the bank directory. This information is required for electronic payment. The file can be downloaded from the [SIX Interbank Clearing](https://go.microsoft.com/fwlink/?LinkId=145121) website.  

You can import the BC Bank Master file—the official Swiss bank clearing number file—to update the bank clearing number information in the bank directory. When you import the bank clearing number file, the data is imported to the **Bank Directory** table, and the existing data is overwritten. After importing the bank clearing number file, you can define the updated bank branch number for customers and vendors. For more information, see the Customer Bank Account table and the Vendor Bank Account table.  

## To import Swiss bank clearing numbers  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Bank Directory**, and choose the related link.  
2.  Choose the **Import Bank Directory** action.  
3.  On the **Import Bank Directory** page, on the **Options** FastTab, select the **Automatically Update Clearing Numbers** field to update the bank clearing numbers automatically.  
4.  Choose the **Print** button or the **Preview** button to import the bank clearing numbers, and then, on the **Open** page, locate the file that you have downloaded from the SIX Interbank Clearing website.
5. Choose the **Open** button.  

    If you choose the **Print** button, the contents of the file will be printed. If you choose the **Preview** button, the **Bank Directory** table will be updated and a report that has clearing numbers that have changed will be displayed.  

The following procedure describes how to define bank branch numbers for customer bank accounts, but the same steps also apply for defining bank branch numbers for vendor bank accounts.  

## To define bank branch numbers for customer bank accounts  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customers**, and then choose the related link.  
2.  Select the customer for whom you want to create bank account information, and then choose the **Bank Accounts** action.  
3.  On the **Customer Bank Account List** page, select the required bank account, and then choose the **Edit** action.  
4.  On the **General** FastTab, in the **Bank Branch No.** field, select the number of the bank agency or branch.  
5.  Choose the **OK** button.  

## See Also  
 [Swiss Electronic Payments](swiss-electronic-payments.md)   
 [Set Up Bank Accounts](../../bank-how-setup-bank-accounts.md)
