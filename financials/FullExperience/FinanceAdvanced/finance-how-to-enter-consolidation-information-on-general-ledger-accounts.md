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
# How to: Enter Consolidation Information on General Ledger Accounts
After setting up the chart of accounts for a consolidated company, you must specify accounts for consolidation. In each company that will be included in the consolidation, for each general ledger account, you must specify the general ledger account in the consolidated company to which the balance will be transferred on consolidation.  
  
### To enter consolidation information on general ledger accounts  
  
1.  On the Application menu ![Microsoft Dynamics NAV Application menu](../media/rtc_applicationmenu.png "RTC\_ApplicationMenu"), choose **Select Company** to open the company for a business unit.  
  
2.  In the **Search** box, enter **Chart of Accounts**, and then choose the related link.  
  
3.  In the **Chart of Accounts** window, for each general ledger account that has the **Posting** type, fill in the **Consol. Debit Acc.**, **Consol. Credit Acc.**, and **Consol. Translation Method** fields.   
  
    > [!IMPORTANT]  
    >  These fields are available in the Chart of Accounts window, but not shown by default. [!INCLUDE[bp_customize](includes/bp_customize_md.md)]  
  
4.  After entering account numbers for all the general ledger accounts, close the **Chart of Accounts** window.  
  
 If you have more than one business unit in the same database, close the current company, open another business unit ,and repeat the procedure.  
  
## See Also  
 [How to: Process Consolidations](../how-to-process-consolidations.md)   
 Chart of Accounts