---
title: Synchronizing Business Central and Dataverse
description: Learn about synchronizing data between Business Central and Dataverse.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 03/31/2023
ms.custom: bap-template
ms.search.keywords: sales, crm, integration, sync, synchronize
ms.service: dynamics-365-business-central
---

# Scheduling a Synchronization between Business Central and Dataverse

You can synchronize [!INCLUDE[prod_short](includes/prod_short.md)] with [!INCLUDE[cds_long_md](includes/cds_long_md.md)] on scheduled intervals by setting up jobs in the job queue. The synchronization jobs synchronize data in [!INCLUDE[prod_short](includes/prod_short.md)] records and [!INCLUDE[cds_long_md](includes/cds_long_md.md)] records that are coupled. For records that are not already coupled, depending on the synchronization direction and rules, the synchronization jobs can create and couple new records in the destination system.

There are several synchronization jobs that are available out-of-the-box. The jobs are run in the following order to avoid coupling dependencies between tables. For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).

1. CURRENCY - Common Data Service synchronization job.
2. VENDOR - Common Data Service synchronization job.
3. CONTACT - Common Data Service synchronization job.
4. CUSTOMER - Common Data Service synchronization job.
5. SALESPEOPLE - Common Data Service synchronization job.

You can view the jobs on the **Job Queue Entries** page. For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).

## Default synchronization job queue entries

The following table describes the default synchronization jobs for [!INCLUDE[cds_long_md](includes/cds_long_md.md)].  

| Job Queue Entry | Description | Direction | Integration Table Mapping | Default Synchronization Frequency (mins) | Default inactivity sleep time (mins) |
|--|--|--|--|--|--|--|
| CONTACT - Common Data Service synchronization job | Synchronizes [!INCLUDE[cds_long_md](includes/cds_long_md.md)] contacts with [!INCLUDE[prod_short](includes/prod_short.md)] contacts. | Bidirectional | CONTACT | 30 | 720 <br>(12 hours) |
| CURRENCY - Common Data Service synchronization job | Synchronizes [!INCLUDE[cds_long_md](includes/cds_long_md.md)] transaction currencies with [!INCLUDE[prod_short](includes/prod_short.md)] currencies. | From [!INCLUDE[prod_short](includes/prod_short.md)] to [!INCLUDE[cds_long_md](includes/cds_long_md.md)] | CURRENCY | 30 | 720 <br> (12 hrs) |
| CUSTOMER - Common Data Service synchronization job | Synchronizes [!INCLUDE[cds_long_md](includes/cds_long_md.md)] accounts with [!INCLUDE[prod_short](includes/prod_short.md)] customers. | Bidirectional | CUSTOMER | 30 | 720<br> (12 hrs) |
| VENDOR - Common Data Service synchronization job | Synchronizes [!INCLUDE[cds_long_md](includes/cds_long_md.md)] accounts with [!INCLUDE[prod_short](includes/prod_short.md)] customers. | Bidirectional | VENDOR | 30 | 720<br> (12 hrs) |
| SALESPEOPLE - Common Data Service synchronization job | Synchronizes [!INCLUDE[prod_short](includes/prod_short.md)] salespeople with [!INCLUDE[cds_long_md](includes/cds_long_md.md)] users. | From [!INCLUDE[cds_long_md](includes/cds_long_md.md)] to [!INCLUDE[prod_short](includes/prod_short.md)] | SALESPEOPLE | 30 | 1440<br> (24 hrs) |

## Synchronization process

Each synchronization job queue entry uses a specific integration table mapping that specifies which [!INCLUDE[prod_short](includes/prod_short.md)] table and [!INCLUDE[cds_long_md](includes/cds_long_md.md)] table to synchronize. The table mappings also include some settings that control which records in the [!INCLUDE[prod_short](includes/prod_short.md)] table and [!INCLUDE[cds_long_md](includes/cds_long_md.md)] table to synchronize.  

To synchronize data, [!INCLUDE[cds_long_md](includes/cds_long_md.md)] table records must be coupled to [!INCLUDE[prod_short](includes/prod_short.md)] records. For example, a [!INCLUDE[prod_short](includes/prod_short.md)] customer must be coupled to a [!INCLUDE[cds_long_md](includes/cds_long_md.md)] account. You can set up couplings manually, before running the synchronization jobs, or let the synchronization jobs set up couplings automatically. The following list describes how data is synchronized between [!INCLUDE[cds_long_md](includes/cds_long_md.md)] and [!INCLUDE[prod_short](includes/prod_short.md)] when you are using the synchronization job queue entries. For more information, see [Couple and Synchronize Records Manually](admin-how-to-couple-and-synchronize-records-manually.md).

- The **Sync. Only Coupled Records** check box controls whether new records are created when you synchronize. By default, the check box is selected, which means that only records that are coupled will be synchronized. In the integration table mapping, you can change the table mapping between a [!INCLUDE[cds_long_md](includes/cds_long_md.md)] table and a [!INCLUDE[prod_short](includes/prod_short.md)] table so that the integration synchronization jobs will create new records in the destination database for each row in the source database that is not coupled. For more information, see [Creating New Records](admin-how-to-modify-table-mappings-for-synchronization.md#create-new-records).

    **Example**
    If you clear the **Sync. Only Coupled Records** check box, when you synchronize customers in [!INCLUDE[prod_short](includes/prod_short.md)] with accounts in [!INCLUDE[cds_long_md](includes/cds_long_md.md)], a new account is created for each customer in [!INCLUDE[prod_short](includes/prod_short.md)] and automatically coupled. Additionally, because the synchronization is bidirectional in this case, a new customer is created and coupled for each [!INCLUDE[cds_long_md](includes/cds_long_md.md)] account that is not already coupled.  

    > [!NOTE]  
    > There are rules and filters that determine what data is synchronized. For more information, go to [Synchronization Rules](admin-synchronizing-business-central-and-sales.md).

- When new records are created in [!INCLUDE[prod_short](includes/prod_short.md)], the records use the either the template that is defined for the integration table mapping or the default template that is available for the row type. Fields are populated with data from [!INCLUDE[prod_short](includes/prod_short.md)] or [!INCLUDE[cds_long_md](includes/cds_long_md.md)] depending on the synchronization direction. For more information, see [Modify Table Mappings for Synchronization](admin-how-to-modify-table-mappings-for-synchronization.md).  

- With subsequent synchronizations, only records that have been modified or added after the last successful synchronization job for the table will be updated.  

     New records in [!INCLUDE[cds_long_md](includes/cds_long_md.md)] are added in [!INCLUDE[prod_short](includes/prod_short.md)]. If data in fields in [!INCLUDE[cds_long_md](includes/cds_long_md.md)] records has changed, the data is copied to the corresponding field in [!INCLUDE[prod_short](includes/prod_short.md)].  

- With bidirectional synchronization, the job synchronizes from [!INCLUDE[prod_short](includes/prod_short.md)] to [!INCLUDE[cds_long_md](includes/cds_long_md.md)], and then from [!INCLUDE[cds_long_md](includes/cds_long_md.md)] to [!INCLUDE[prod_short](includes/prod_short.md)].

## About inactivity timeouts

Some job queue entries, such as those that schedule synchronization between [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[cds_long_md](includes/cds_long_md.md)], use the **Inactivity Timeout** field on the **Job Queue Entry** page to prevent the job queue entry from running unnecessarily.  

:::image type="content" source="media/on-hold-with-inactivity-timeout.png" alt-text="Flowchart for when job queue entries are put on hold due to inactivity.":::

When the value in this field is not zero, and the job queue did not find any changes during the last run, [!INCLUDE[prod_short](includes/prod_short.md)] puts the job queue entry on hold. When that happens, the **Status of Job Queue** field will show **On Hold Due to Inactivity**, and [!INCLUDE[prod_short](includes/prod_short.md)] will wait for the period of time specified in **Inactivity Timeout** field before it runs the job queue entry again.  

For example, by default, the CURRENCY job queue entry, which synchronizes currencies in [!INCLUDE[cds_long_md](includes/cds_long_md.md)] with exchange rates in [!INCLUDE[prod_short](includes/prod_short.md)], will look for changes to exchange rates every 30 minutes. If no changes are found, [!INCLUDE[prod_short](includes/prod_short.md)] puts the CURRENCY job queue entry on hold for 720 minutes (twelve hours). If an exchange rate is changed in [!INCLUDE[prod_short](includes/prod_short.md)] while the job queue entry is on hold, [!INCLUDE[prod_short](includes/prod_short.md)] will automatically reactivate the job queue entry and restart the job queue. 

> [!Note]
> [!INCLUDE[prod_short](includes/prod_short.md)] will automatically activate job queue entries that are on hold only when changes happen in [!INCLUDE[prod_short](includes/prod_short.md)]. Changes in [!INCLUDE[cds_long_md](includes/cds_long_md.md)] will not activate job queue entries.

## To view the synchronization job log

1. Choose the :::image type="icon" source="media/ui-search/search_small.png" border="false"::: icon, enter **Integration Synchronization Log**, and then choose the related link.
2. If one or more error occurred for a synchronization job, the number of errors appears in the **Failed** column. To view the errors for the job, choose the number.  

    > [!TIP]  
    > You can view all synchronization job errors by opening the synchronization job error log directly.

## To view the synchronization job log from the table mappings

1. Choose the :::image type="icon" source="media/ui-search/search_small.png" border="false"::: icon, enter **Integration Table Mappings**, and then choose the related link.
2. In the **Integration Table Mappings** page, select an entry, and then choose **Integration Synch. Job Log**.  

## To view the synchronization error log

- Choose the :::image type="icon" source="media/ui-search/search_small.png" border="false"::: icon, enter **Integration Synchronization Errors**, and then choose the related link.

## Related information

[Synchronizing Data in Business Central and [!INCLUDE[cds_long_md](includes/cds_long_md.md)]](admin-synchronizing-business-central-and-sales.md)  
[Manually Synchronize Table Mappings](admin-manual-synchronization-of-table-mappings.md)  
[Scheduling a Synchronization between Business Central and [!INCLUDE[cds_long_md](includes/cds_long_md.md)]](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md)  
[About Integrating Dynamics 365 Business Central with [!INCLUDE[cds_long_md](includes/cds_long_md.md)]](admin-prepare-dynamics-365-for-sales-for-integration.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
