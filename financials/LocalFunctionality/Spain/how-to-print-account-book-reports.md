---
    title: How to: Print Account Book Reports | Microsoft Docs
    description: Account book reports display all the general ledger entries created in a specific period. The two account book reports are:
    services: project-madeira
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
# How to: Print Account Book Reports
Account book reports display all the general ledger entries created in a specific period. The two account book reports are:  
  
-   **Official Account Book** report - Displays information for every general ledger entry, grouped by transaction.  
  
-   **Official Account Summarized Book** report - Displays a summary of general entries, grouped by heading or posting accounts.  
  
 When sending these reports to the authorities or auditors, you can include additional pages that will precede your report. To do this, you need to manually set the report's first page number. For example, if you have three pages of information preceding your report, you can set the first page of the report to indicate that it is page 4.  
  
### To print an official account book report  
  
1.  In the **Search** box, enter **Account - Official Acc. Book**, and then choose the related link.  
  
2.  In the **Options** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Closing Transaction Description**|Enter the description for the closing period transaction.|  
    |**Opening Transaction Description**|Enter the description for the opening period transaction.|  
    |**First Page**|Enter the number that you want to include on the first page of the report.|  
    |**Show Amounts in Add. Currency**|Select to show the report amounts in additional reporting currency (ACY).|  
  
3.  In the **GL Register** FastTab, select appropriate filters.  
  
4.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  
  
### To print an official account summarized book report  
  
1.  In the **Search** box, enter **Official Acc.Summarized Book**, and then choose the related link.  
  
2.  In the **Options** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**From Date**|Enter the start date of the report.|  
    |**To Date**|Enter the end date of the report.|  
    |**Include Closing Entries**|Select to include the closing entries in the report.|  
    |**Show Amounts in Add. Currency**|Select to show the report amounts in additional reporting currency (ACY).|  
    |**First page**|Enter the number that you want to include on the first page of the report.|  
    |**Account Type**|Select **Posting** or **Heading**. **Posting** implies that entries can be posted to the account, and **Heading** implies that entries cannot be posted to the account.|  
  
3.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  
  
## See Also  
 [Spain Local Functionality](spain-local-functionality.md)   
 Account - Official Acc. Book   
 Official Acc. Summarized Book