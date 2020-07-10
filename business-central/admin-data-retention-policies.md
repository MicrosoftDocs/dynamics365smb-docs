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
Administrators can define retention policies to specify how frequently they want Business Central to delete outdated data in tables that contain log entries and archived records. For example, cleaning up log entries can make it easier to work with the data that's actually relevant. Policies can include all data in the tables that is past the expiration date, or you can add filter criteria that will include only certain expired data in the policy. 

## Setting Up Retention Policies
> [!NOTE]
> To set up retention policies, you must have the SUPER user permissions or the Retention Policy Setup permission set.

Before you can create retention policies, you must set up the following.

|Setup  |Description  |
|---------|---------|
|**Allowed Tables**     |We provide a list of the tables that can be included in retention policies. However, if you want to add tables from an extension to a retention policy a developer must create a new list. For more information, see [Including Your Extension in a Retention Policy](admin-data-retention-policies.md#including-your-extension-in-a-retention-policy).          |
|**Retention Periods**     |Specify periods of time for which to keep data in the tables in a policy. The periods determine how often data will be deleted.         |

### To create retention period
Retention periods can be as long or as short as you want. To create retention periods, on the **Retention Policies** page, use the **Retention Period** action. The periods you define will be available for all policies.

### Set up a retention policy
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Retention Policies**, and choose the related link.
2. In the **Table ID** field, choose the table that you want to include in the policy.
3. In the **Retention Period** field, specify the length of time for which to keep the data in the table.
4. Optional: To apply the policy to only certain data in a table, turn off the **Apply to all records** toggle. The **Record Retention Policy** FastTab will display, where you can specify filters that will determine the subset of expired data to which the policy applies. For more information, see [Filtering](ui-enter-criteria-filters.md#filtering).

## Applying Retention Policies
You can use a job queue entry to apply retention policies to delete data automatically, or you can manually apply policies.

To apply a retention policy automatically, just create and enable a policy. When you enable a policy we create a job queue entry that will automatically apply retention policies according to the retention period you specify. All retention policies will use the same job queue entry. By default, the job queue entry applies the policy every day at 0200. You can change the default, but if you do we recommend that it runs outside business hours. For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md). 

If you prefer to manually apply a policy yourself, you can turn on the **Manual** toggle on the **Retention Policies** page. You can then can use the **Apply Manually** action on the **Retention Policies** page. 

## Viewing Retention Policy Log Entries
You can view activity related to retention policies in the **Retention Policy Log** page. For example, entries are created when when a policy is applied, or if errors occurred when that happened. 

## Including Your Extension in a Retention Policy
By default, retention policies cover only tables that are included in the list of Business Central tables that we provide. You can remove default tables from the list, and you can add tables that you own. That is, you cannot add a table that you did not create yourself. For example, you cannot add other tables from Business Central or from an extension that you have purchased.

To build your own list of allowed tables, a developer must add some code to the installer codeunit for the extension (a codeunit with the subtype install). You can add or edit the list of allowed tables only during installation or upgrade, and you must publish a new version of your extension. 

The following code example shows how we added a table to the allowed tables list in codeunit 3907 "Retention Policy Installer". 

```
trigger OnInstallAppPerCompany()    
var        
  RetentionPolicyLogEntry: Record "Retention Policy Log Entry";        
  RetenPolAllowedTables: Codeunit "Reten. Pol. Allowed Tables";        
  CurrModuleInfo: ModuleInfo;    
begin        
  NavApp.GetCurrentModuleInfo(CurrModuleInfo);        
  RetenPolAllowedTables.AddAllowedTable(Database::"Retention Policy Log Entry", RetentionPolicyLogEntry.FieldNo("Date/time"), CurrModuleInfo);    
end;
```

After a developer has added tables to the list, an administrator can include them in a retention policy. 

## See Also
[Auditing Changes in Business Central](across-log-changes.md)  
[Filtering](ui-enter-criteria-filters.md#filtering)  
[Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  