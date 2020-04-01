---
    title: How to Import and Export Data in Standard Import Export Format
    description: You can import and export general ledger data according to the standard import export (SIE) format.

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
# Import and Export Data in Standard Import Export Format
You can import and export general ledger data according to the standard import export (SIE) format. By specifying SIE dimensions and file types, you can specify the level of detail covered by import or export transactions. For more information, see [Standard Import Export Group](https://go.microsoft.com/fwlink/?LinkID=164870&clcid=0x41d).  

## To import data in SIE format  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **SIE Import**, and then choose the related link.  
2.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Gen. Journal Template**|Select a general journal template.|  
    |**Gen. Journal Batch**|Select a general journal batch.|  
    |**Dimensions**|Select the SIE dimensions to import.|  
    |**Insert G/L Account**|Select if the general ledger account in the import file is missing in the chart of accounts and needs to be set up during the import process.|  
    |**Use Number Series for Doc. No.**|Select if a document number is not provided in the import file.|  

3. Choose the **OK** button.
4. Select the file to import.  

## To export data in SIE format  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **SIE Export**, and then choose the related link.  
2.  On the **G/L Account** FastTab, choose the appropriate filters.  
3.  On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**File Type**|Select the type of file to be created. Select from one of the following options:<br /><br /> -   **Year - End Balances** - Contains the annual account balance carried forward for all accounts in the chart of accounts.<br />-   **Periodic Balances** - Contains the annual account balance carried forward and monthly changes for all accounts in the chart of accounts.<br />-   **Object Balances** - Contains the annual account balance carried forward, monthly changes, and balances on the object level, such as cost units and projects, for all accounts in the chart of accounts.<br />-   **Transactions** - Contains all the general ledger entries for the period.|  
    |**Contact**|Enter the contact person. This field is optional.|  
    |**Comments**|Describe the content of the file.|  
    |**Dimensions**|Select the dimensions to export.|  
    |**Fiscal Year**|Enter the fiscal tax year.|

4. Choose the **OK** button.
5. Choose the **Open** or **Save** button to decide where to place the exported file.

## See Also  
 [Standard Import Export Group](https://go.microsoft.com/fwlink/?LinkID=164870&clcid=0x41d)   
 [Sweden Local Functionality](sweden-local-functionality.md)
