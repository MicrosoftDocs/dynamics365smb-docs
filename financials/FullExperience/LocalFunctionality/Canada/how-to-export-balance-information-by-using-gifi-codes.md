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
# How to: Export Balance Information by Using GIFI Codes
You can export balance information using General Index of Financial Information \(GIFI\) codes and save the exported file in a Microsoft Excel workbook. You can modify, save, or delete the file. You can use the file to transfer information to your tax preparation software.  
  
### To export balance information using GIFI codes  
  
1.  In the **Search** box, enter **Export GIFI Info. to Excel**, and then choose the related link.  
  
2.  In the **Export GIFI Info. to Excel** window, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] -->|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
    |---------------------------------|---------------------------------------|  
    |**\($ B\_10005\_F\_1\_1020000 Balance As of Date $\)**|The balance as of the specified date.|  
    |**\($ B\_10005\_F\_1\_1020006 Use Add. Rpt. Currency $\)**|Select to display the amounts in additional reporting currency.|  
    |**\($ B\_10005\_F\_1\_1020004 Include GIFI Name $\)**|Select to include the GIFI name in the file.|  
    |**\($ B\_10005\_F\_1\_1020002 Include Unused Codes $\)**|Select to include the unused codes in the file.|  
  
3.  On the **G\/L Account** FastTab, select the appropriate filters.  
  
4.  To export the file to Excel, choose the **OK** button.  
  
     In the Excel file, the balance is rounded to the nearest percentage, but the cell value maintains the same percentage as it does in the general ledger.  
  
## See Also  
 GIFI Code   
 [GIFI Codes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/gifi-codes.md)   
 Account Balances by GIFI Code   
 Export GIFI Info. to Excel   
 [How to: Set Up GIFI Codes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-set-up-gifi-codes.md)   
 [How to: View Account Balances by Using the GIFI Code Report](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-view-account-balances-by-using-the-gifi-code-report.md)   
 [How to: Associate GIFI Codes with Chart of Accounts](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-associate-gifi-codes-with-chart-of-accounts.md)