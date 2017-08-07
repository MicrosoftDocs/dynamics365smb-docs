---
    title: How to: Post Prepaid Contract Entries | Microsoft Docs
    description: If you work with prepaid service contracts, you must regularly post prepaid contract entries, thereby transferring the prepaid payments from the prepaid contract accounts to the regular contract accounts.
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
# How to: Post Prepaid Contract Entries
If you work with prepaid service contracts, you must regularly post prepaid contract entries, thereby transferring the prepaid payments from the prepaid contract accounts to the regular contract accounts.  
  
 Before you can post prepaid contract entries, you must specify a number series in the **Prepaid Posting Document Nos.** field in the **Service Mgt. Setup** window.  
  
### To post prepaid contract entries  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Post Prepaid Contract Entries**, and then choose the related link.  
  
2.  On the **Service Ledger Entry** FastTab, enter the filters you want to apply.  
  
3.  On the **Options** FastTab, in the **Post until Date** field, enter a date. The batch job posts prepaid service ledger entries with posting dates up to this date.  
  
4.  In the **Posting Date** field, enter the date you want to use as the posting date on the general journal line.  
  
5.  In the **Action** field, select **Post Prepaid Transactions**.  
  
6.  Choose the **OK** button to post the entries.  
  
## See Also  
 [Service Management Setup](../service-management-setup.md)   
 Service Mgt. Setup