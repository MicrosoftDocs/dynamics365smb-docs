---
    title: View the Status of Synchronization Jobs | Microsoft Docs
    description: Learn how to view the status after synchronizing coupled records.
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: sales, crm, integration, sync, synchronize
    ms.date: 04/01/2021
    ms.author: bholtorf

---

# View the Status of Synchronization Jobs
[!INCLUDE[prod_short](includes/cc_data_platform_banner.md)]

Use the **Coupled Data Synchronization Errors** page to view the status of synchronization jobs that have been run for coupled records in a Dataverse or [!INCLUDE[crm_md](includes/crm_md.md)] integrations. This includes jobs that were run from the job queue and manual synchronization jobs that ran on records from [!INCLUDE[prod_short](includes/prod_short.md)]. For example, viewing their status is helpful when troubleshooting because it gives you access to details about errors related to coupled records. Typically, these types of errors are caused by user actions, for example, when:  

* Two people made a change to the same data in both business apps.
* Someone deleted data in one of the apps, but not both.

> [!Note]
> The **Coupled Data Synchronization Errors** page shows information about jobs related to coupled records. If you resolve all of the errors but records are still not synchronizing, it might have something to do with a setting for the integration. Typically, your administrator will need to resolve those types of errors.   

<!--

> [!VIDEO https://go.microsoft.com/fwlink/?linkid=2098171]

-->

## To view and resolve synchronization errors for coupled records
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Coupled Data Synchronization Errors**, and then choose the related link.
2. The **Coupled Data Synchronization Errors** page shows issues that occurred when you synchronized coupled records. The following table includes actions that you can use to resolve issues one by one:

|Action|Description|
|----|----|
|**Remove Coupling**|Uncouples the records and they will no longer synchronize. To restart the synchronization you must couple them again. |
|**Retry** and **Retry All**|For each record where an error is found, synchronization is skipped unless you fix the issue. Retry will include the selected record in the next synchronization, and **Retry All** includes all of the records.|
|**Synchronize**|The app will try to resolve a conflict where data was changed in both business apps. You can choose the data to use.|
|**Restore Records** and **Delete Records**|These are useful when a record was deleted in one of the business apps. Delete Records deletes the record or row in the app where it still exists. Restore Records recreates the record or row in the business app where it was deleted.|

> [!NOTE]
> To reduce the number of conflicts you need to resolve, you can set up your integration table mappings to apply these actions automatically. For more information, [Mapping Integration Tables](admin-how-to-modify-table-mappings-for-synchronization.md#mapping-integration-tables).

## To view the synchronization log for a specific (manually synchronized) record
1. Open, for example, a customer, item or any other record that is synchronizing data between [!INCLUDE[prod_short](includes/prod_short.md)] and Dataverse or [!INCLUDE[crm_md](includes/crm_md.md)].
2. Choose the **Synchronization Log** action to view the synchronization log for a selected record. For example, a specific customer you synchronized manually.

## See Also  
[Setting Up User Accounts for Integrating with Dynamics 365 Sales](admin-setting-up-integration-with-dynamics-sales.md)  
[Using Dynamics 365 Sales from Business Central](marketing-integrate-dynamicscrm.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]