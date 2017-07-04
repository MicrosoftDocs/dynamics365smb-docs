---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# How to: Import Payroll Transactions
You can import payroll transactions into a general journal from two external payroll solutions: Huldt & Lillevik and Hogia. You can then use the general journal to post the imported payroll transactions to general ledger accounts or bank accounts. To import payroll transactions, you must first set up payroll integration.  
  
### To set up payroll integration  
  
1.  In the **Search** box, enter **Payroll Integration Setup**, and then choose the related link.  
  
2.  On the **General** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Payroll System**|Select a payroll system.|  
    |**File Name**|Enter the full path of the file.|  
    |**Save Payroll File**|Select to save the payroll file.|  
    |**Import Department and Project**|Select to import department and project information.|  
    |**Journal Template Name**|Select the name of the journal template.|  
    |**Journal Name**|Select a journal to receive the imported payroll transactions.|  
    |**Post to**|Select the account type to post the payroll transactions to. Account types include **G/L Account** and **Bank Account**.|  
  
3.  Choose the **OK** button.  
  
### To import payroll transactions  
  
1.  In the **Search** box, enter **General Journals**, and then choose the related link.  
  
2.  On the **Home** tab, in the **Process** group, choose **Import Payroll**.  
  
3.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Posting Date**|Select a payroll system.|  
    |**Document text**|Enter the full path of the file.|  
    |**File Name**|Specify the file name for the payroll file.|  
  
4.  Choose the **OK** button.  
  
## See Also  
 [Norway Local Functionality](norway-local-functionality.md)   
 General Journal   
 Payroll Integration Setup   
 Import Hogia Windows Payroll   
 Import Huldt & Lillevik