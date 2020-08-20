---
    title: Clean Up Data with Retention Policies | Microsoft Docs
    description: You can specify how often you want to delete certain types of data.
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: delete, data, retention
    ms.date: 04/01/2020
    ms.author: bholtorf

---
# Define Retention Policies
Administrators can define retention policies to specify how frequently they want [!INCLUDE[prodshort](includes/prodshort.md)] to delete outdated data in tables that contain log entries and archived records. For example, cleaning up log entries can make it easier to work with the data that's actually relevant. Policies can include all data in the tables that is past the expiration date, or you can add filter criteria that will include only certain expired data in the policy. 

## Setting Up Retention Policies
> [!NOTE]
> To set up retention policies, you must have the SUPER user permissions or the Retention Policy Setup permission set.

Before you can create retention policies, you must set up the following.

|Setup  |Description  |
|---------|---------|
|**Allowed Tables**     |We provide a list of the tables that can be included in retention policies. However, if you want to add tables from an extension to a retention policy a developer must add their tables to the list. For more information, see [Including Your Extension in a Retention Policy](admin-data-retention-policies.md#including-your-extension-in-a-retention-policy).          |
|**Retention Periods**     |Specify periods of time for which to keep data in the tables in a policy. The periods determine how often data will be deleted.         |

### To create retention periods
Retention periods can be as long or as short as you want. To create retention periods, on the **Retention Policies** page, use the **Retention Period** action. The periods you define will be available for all policies.

> [!NOTE]
> For compliance reasons, we have defined a minimum retention period for some tables. If you set a retention period that is shorter than minimum required, a message will display the mandatory period.

### Set up a retention policy
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Retention Policies**, and choose the related link.
2. In the **Table ID** field, choose the table that you want to include in the policy.
3. In the **Retention Period** field, specify the length of time for which to keep the data in the table.
4. Optional: To apply the policy to only certain data in a table, turn off the **Apply to all records** toggle. The **Record Retention Policy** FastTab will display, where you can specify filters that will determine the subset of expired data to which the policy applies. For more information, see [Filtering](ui-enter-criteria-filters.md#filtering).

> [!NOTE]
> Some tables contain filters that you cannot change or remove. To help you identify these filters, they appear in a lighter color font.

## Applying Retention Policies
You can use a job queue entry to apply retention policies to delete data automatically, or you can manually apply policies.

To apply a retention policy automatically, just create and enable a policy. When you enable a policy we create a job queue entry that will apply retention policies according to the retention period you specify. All retention policies will use the same job queue entry. By default, the job queue entry applies the policy every day at 0200. You can change the default, but if you do we recommend that it runs outside business hours. For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md). 

You can manually apply a policy by using the **Apply Manually** action on the **Retention Policies** page. If you want to always apply a policy manually, turn on the **Manual** toggle. The job queue entry will disregard the policy when it runs.

## Viewing Retention Policy Log Entries
You can view activity related to retention policies in the **Retention Policy Log** page. For example, entries are created when when a policy is applied, or if errors occurred when that happened. 

## Including Your Extension in a Retention Policy (Requires Help from a Developer)
By default, retention policies cover only tables that are included in the list of [!INCLUDE[prodshort](includes/prodshort.md)] tables that we provide. You can remove default tables from the list, and you can add tables that you own. That is, you cannot add a table that you did not create yourself. For example, you cannot add other tables from [!INCLUDE[prodshort](includes/prodshort.md)] or from an extension that you have purchased.

To add your tables to the list of allowed tables, a developer must add some code, for example to the installer codeunit for the extension (a codeunit with the *install* subtype). 

When a developer adds a table, they can specify mandatory and default filters. Mandatory filters cannot be removed or modified later when you add tables to define a retention policy. Default filters are just friendly suggestions.

The following are examples of how to add a table to the list of allowed tables with, and without, mandatory or default filters. For a more complex example, see codeunit 3999 "Reten. Pol. Install - BaseApp". 

```
 trigger OnInstallAppPerCompany()
    var
        RetenPolAllowedTables: Codeunit "Reten. Pol. Allowed Tables";
    begin
        RetenPolAllowedTables.AddAllowedTable(Database::"Retention Policy Log Entry");
    end;
```

The following example includes a mandatory filter.

```
 trigger OnInstallAppPerCompany()
    var
        ChangeLogEntry: Record "Change Log Entry";
        RetenPolAllowedTables: Codeunit "Reten. Pol. Allowed Tables";
        RetentionPeriod: Enum "Retention Period Enum";
        RecRef: RecordRef;
        TableFilters: JsonArray;
        Enabled: Boolean;
        Mandatory: Boolean;
    begin
        ChangeLogEntry.Reset();
        ChangeLogEntry.SetFilter("Field Log Entry Feature", '%1|%2', ChangeLogEntry."Field Log Entry Feature"::"Monitor Sensitive Fields", ChangeLogEntry."Field Log Entry Feature"::All);
        RecRef.GetTable(ChangeLogEntry);
        Enabled := true;
        Mandatory := true;
        RetenPolAllowedTables.AddTableFilterToJsonArray(TableFilters, RetentionPeriod::"28 Days", ChangeLogEntry.FieldNo(SystemCreatedAt), Enabled, Mandatory, RecRef);
        RetenPolAllowedTables.AddAllowedTable(Database::"Change Log Entry", ChangeLogEntry.FieldNo(SystemCreatedAt), TableFilters);
    end;
```
After a developer has added tables to the list, an administrator can include them in a retention policy. 

## See Also
[Auditing Changes in Business Central](across-log-changes.md)  
[Filtering](ui-enter-criteria-filters.md#filtering)  
[Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  