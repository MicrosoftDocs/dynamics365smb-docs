---
    title: Import Swiss Bank Clearing Numbers [CH]
    description: This article tells you how to import Swiss Bank Clearing Numbers using the Swiss version of Business Central. 
    author: brentholtorf
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.search.form: 11501
    ms.date: 06/21/2021
    ms.author: bholtorf
---
# Import Swiss Bank Clearing Numbers in the Swiss Version

Bank clearing numbers are unique numbers used to identify each bank agency or branch in the bank directory. This information is required for electronic payment. The file can be downloaded from the [SIX Interbank Clearing](https://go.microsoft.com/fwlink/?LinkId=145121) website.  

You can import the BC Bank Master .txt file—the official Swiss bank clearing number file—to update the bank clearing number information in the bank directory. When you import the bank clearing number file, the data is imported to the **Bank Directory** table, and the existing data is overwritten. After importing the bank clearing number file, you can define the updated bank branch number for customers and vendors. For more information, see the Customer Bank Account table and the Vendor Bank Account table.  

## To import Swiss bank clearing numbers  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Directory**, and choose the related link.  
2. Choose the **Import Bank Directory** action.  
3. Choose the **...** button to open the .txt bank clearing number file.
4. On the **Import Bank Directory** page, on the **Options** FastTab, select the **Automatically Update Clearing Numbers** field to update the bank clearing numbers automatically.  
5. Choose the **Print** button or the **Preview** button to import the bank clearing numbers, and then, on the **Open** page, locate the file that you have downloaded from the SIX Interbank Clearing website.
6. Choose the **Open** button.  

   If you choose the **Print** button, the contents of the file will be printed. If you choose the **Preview** button, the **Bank Directory** table will be updated and a report that has clearing numbers that have changed will be displayed.  

The following procedure describes how to define bank branch numbers for customer bank accounts. The same steps also apply for defining bank branch numbers for vendor bank accounts.  

## To define bank branch numbers for customer bank accounts  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.  
2. Select the customer for whom you want to create bank account information, and then choose the **Bank Accounts** action.  
3. On the **Customer Bank Account List** page, select the required bank account, and then choose the **Edit** action.  
4. On the **General** FastTab, in the **Bank Branch No.** field, select the number of the bank agency or branch.  
5. Choose the **OK** button.  

## See also

[Swiss Electronic Payments](swiss-electronic-payments.md)  
[Set Up Bank Accounts](../../bank-how-setup-bank-accounts.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
