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
|**Allowed Tables**     |We provide a list of tables that can be included in retention policies, however, if you want to add tables from an extension to a retention policy a developer must create a new list. For more information, see [Including Your Extension in a Retention Policy](admin-data-retention-policies.md#including-your-extensioin-in-a-retention-policy).          |
|**Retention Periods**     |Specify how often to delete data in the tables included in a retention policy.         |

### Including Your Extension in a Retention Policy
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

### To create retention period
Retention periods can be as long or as short as you want. To create retention periods, on the **Retention Policies** page, use the **Retention Period** action. The periods you define will be available for all policies.

### Set up a retention policy
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Retention Policies**, and choose the related link.
2. In the **Table ID** field, choose the table that you want to include in the policy.
3. 
1. 
1. If you want to apply the policy to certain data in a table, you can clear the Apply to All toggle. The Retention policy FastTab will display, where you can specify filters that will determine the subset of expired data to which the policy applies.


## Applying Retention Policies
When you enable a retention policy we create a job queue entry to automatically apply retention policies, or you can use the **Apply Manually** action on the **Retention Policies** page. All retention policies will use the same job queue entry. For more information, see Job queue entries

By default, the job queue entry applies the policy every day at 0200. You can change the default, but if you do we recommend that it runs outside business hours. 

If you turn on the **Manually** toggle, we will not create a job queue entry.

## Viewing Retention Policy Log Entries
You can view activity related to retention policies in the **Retention Policy Log** page. For example, entries are created when when a policy is applied, or if errors occurred when that happened. 

## See Also