---
    title: View the Status of a Synchronization | Microsoft Docs
    description: Learn how to view the status of an individual synchronization job.
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: sales, crm, integration, sync, synchronize
    ms.date: 03/20/2019
    ms.author: bholtorf

---

# View the Status of a Synchronization
You can view the status of the individual synchronization jobs that have been run for [!INCLUDE[crm_md](includes/crm_md.md)] integration. This includes synchronization jobs that have been run from the job queue and manual synchronization jobs that were performed on records from [!INCLUDE[d365fin](includes/d365fin_md.md)]. This is helpful when troubleshooting synchronization problems because it gives you access to details about specific errors.

### To view all synchronization issues
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Coupled Data Synchronization Errors**, and then choose the related link.
2. On the **Coupled Data Synchronization Errors** page you can view of all issues that occurred in synchronization of data between [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[d365fin](includes/d365fin_md.md)], filter and sort records in the page by table, error message and take actions such as **Retry** or **Remove Coupling** to resolve issues one by one or in bulk.

### To view synchronization log for specific (manually synchronized) record
1. Open, for example, customer, item or any other record that is synchronizing data between [!INCLUDE[d365fin](includes/d365fin_md.md)] and Sales
2. Choose **Synchronization Log** action to view the synchronization log for selected record, for example, specific customer you synchronized manually

## See Also  
[Setting Up Dynamics 365 for Sales Integration in Business Central](admin-setting-up-integration-with-dynamics-sales.md)  
[Using Dynamics 365 for Sales from Business Central](marketing-integrate-dynamicscrm.md)
