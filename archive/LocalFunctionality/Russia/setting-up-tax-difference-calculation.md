---
    title: Setting up Tax Difference Calculation
    description: Tax difference calculations must be set up if there is a tax difference for the presentation of fixed asset entries, item cost entries, or finance transactions in bookkeeping and tax accounting for which expenses to write off must be fixed.

    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Setting up Tax Difference Calculation
Tax difference calculations must be set up if there is a tax difference for the presentation of fixed asset entries, item cost entries, or finance transactions in bookkeeping and tax accounting for which expenses to write off must be fixed. To set tax difference, choose the **Setup** action, and then choose the **Tax Differences** action.  

## Setting Up Posting Groups  
In the menu sub-item **Posting Groups**, you must determine finance accounts from the set up chart of accounts, where finance transactions with tax differences are accounted for.  

In the **Tax Difference Posting Groups** form, enter the fields described in the following table.  

|Field|Description|  
|-------------|-----------------|  
|**FA Posting Date**|Enter the transaction date.|  
|**Document No.**|Enter the document number that the current transaction is created with.|  
|**FA No.**|Enter the code of the expense of the future period that the current transaction is created with.|  
|**Depreciation Book Code**|Select the code of the depreciation book that the transaction will be formed with.|  
|**FA Posting Type**|Select the **Transaction** type. The values are: **Purchase**, **Depreciation**, and **Sales**.|  
|**Description**|Enter a description of the transaction.|  
|**Amount**|Enter the amount of the transaction.|  
|**Depr. Amount w/o Normalization**|Displays the depreciation amount before calculating norms of expenses to write off.|  

If there are journal lines that must be normalized before writing off expenses, those journals cannot be posted without running a periodic job of normalizing.  

The following procedure shows how to process a normalization function.  

1.  In the **Future Expenses Journal** window, choose the **Calculate Depreciation by Norm.** action  
2.  In the **Calculate FE Depr. With Norm** window, on the **Tax Difference** FastTab, enter the filter for the tax difference.  
3.  On the **Options** FastTab, enter the accounting period for which the counting is done.  
4.  Choose the **Print** action to print the report.  
5.  Post the future expenses journal.  

## See Also  
 [Tax Registers](tax-registers.md)   
 [Tax Differences](assetId:///e42ca8e7-1cee-4fb8-9f71-e596f29cabc3)   
 [Tax Difference Registers](tax-difference-registers.md)   
 [How to: Set Up Norm Jurisdictions](how-to-set-up-norm-jurisdictions.md)   
 [How to: Post Tax Differences](how-to-post-tax-differences.md)
