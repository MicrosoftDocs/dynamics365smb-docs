---
title: Clean Up Data with Retention Policies
description: You can specify how often you want to delete certain types of data.
author: brentholtorf
ms.topic: how-to
ms.author: bholtorf
ms.search.keywords: delete, data, retention, policy, policies
ms.search.form: 3903, 3901
ms.date: 01/27/2025
ms.custom: bap-template
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Define Retention Policies

This article describes how administrators can define retention policies to specify how often to delete outdated data in tables that contain log entries and archived records. For example, cleaning up log entries can make it easier to work with the more relevant data. Policies can delete data based on an expiration date, or you can add filters to include only certain expired data.

## Required setups and permissions

Before you can create retention policies, you must set up the tables to include and the periods of time to keep data.

|Setup  |Description  |
|---------|---------|
|**Allowed Tables**     |We provide a list of tables that you can include in retention policies. If you want to add tables from an extension to a retention policy, a developer must add their tables to the list. To learn more, go to [Include your extension in a retention policy](admin-data-retention-policies.md#include-your-extension-in-a-retention-policy-requires-help-from-a-developer).          |
|**Retention Periods**     |Specify periods of time for which to keep data in the tables in a policy. The periods determine how often data is deleted.         |

Additionally, you must have the **SUPER** user permissions or the **Retention Policy Setup** permission set. Users who have the Retention Policy Setup permission set can define retention policies for tables. That's true, even if they don't have Read and Delete permissions for the tables. The job queue entry must run as a user with permissions to read and delete the data. Don't grant the Retention Policy Setup permission set to users who shouldn't be allowed to delete data.

> [!NOTE]
> If you're using [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, and you want to try out retention policies in the the Cronus demonstration database, there are a few things you need to do. The demonstration company doesn't contain tables that you can use with retention policies, so you need to add them. To do that, create a new, blank company in the demonstration database. In the new company, import the RapidStart configuration package for your country/region that corresponds to the standard NAV17.0.W1.ENU.STANDARD.rapidstart package. The setup data for retention policies will be available in the new company.

### Create retention periods

Retention periods can be as long or as short as you want. To create retention periods, on the **Retention Policies** page, use the **Retention Period** action. The periods you define are available for all policies.

> [!NOTE]
> For compliance reasons, we have defined a minimum retention period for some tables. If you set a retention period that's shorter than minimum required, a message displays the mandatory period.

### Set up a retention policy

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Retention Policies**, and choose the related link.
2. Select **New** to create a new retention policy. 
3. In the **Table ID** field, choose the table that you want to include in the policy.
4. In the **Retention Period** field, specify the length of time for which to keep the data in the table.
5. Optional: You can apply the policy to specific data in a table, rather than all records, by filtering the data for each line. The policy will apply only to the records that the filters return. To specify the filter criteria, turn off the **Apply to all records** toggle. The **Record Retention Policy** FastTab displays, where you can set filter criteria. To learn more about how filters work, go to [Filtering](ui-enter-criteria-filters.md#filtering).

   > [!NOTE]
   > Each line has its own retention period. If you specify different retention periods for the same data, the longest period is used. Also, some tables contain filters that you can't change or remove. To help you identify these filters, they appear in a lighter color font.

#### Video guidance

This video provides an example of how to set up a retention policy.

>[!VIDEO https://learn-video.azurefd.net/vod/player?id=511928c9-f956-45f6-8748-0c96f7ff0d33]

## Apply retention policies

You can use a job queue entry to apply retention policies to delete data automatically, or you can manually apply policies.

To apply a retention policy automatically, just create and enable a policy. When you enable a policy,, [!INCLUDE [prod_short](includes/prod_short.md)] creates a job queue entry that applies the it according to its retention period. All retention policies will use the same job queue entry. By default, the job queue entry applies the policy every day at 0200. You can change the default, but if you do we recommend that it runs outside business hours. To learn more, go to [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md). 

You can manually apply a policy by using the **Apply Manually** action on the **Retention Policies** page. If you want to always apply a policy manually, turn on the **Manual** toggle. The job queue entry will disregard the policy when it runs.

## View retention policy log entries

You can view activity related to retention policies in the **Retention Policy Log** page. For example, entries are created when a policy is applied, or if errors occurred.

## Include your extension in a retention policy (requires help from a developer)

By default, retention policies cover only [!INCLUDE[prod_short](includes/prod_short.md)] in the list we provide. You can remove default tables from the list, and you can add tables that you own. That is, you can't add a table that you did not create yourself. For example, you can't add other tables from [!INCLUDE[prod_short](includes/prod_short.md)] or from an extension that you have purchased.

To add your tables to the list of allowed tables, a developer must add some code. For example, to the installer codeunit for the extension (a codeunit with the *install* subtype).

When a developer adds a table, they can specify mandatory and default filters. Mandatory filters can't be removed or modified later when you add tables to define a retention policy. The default filters are just suggestions.

The following are examples of how to add a table to the list of allowed tables with, and without, mandatory or default filters. For a more complex example, go to codeunit 3999 "Reten. Pol. Install - BaseApp".

```al
 trigger OnInstallAppPerCompany()
    var
        RetenPolAllowedTables: Codeunit "Reten. Pol. Allowed Tables";
    begin
        RetenPolAllowedTables.AddAllowedTable(Database::"Retention Policy Log Entry");
    end;
```

The following example includes a mandatory filter.

```al
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

## Related information

[Analyzing Retention Policy Trace Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-retention-policy-trace)  
[Auditing Changes in Business Central](across-log-changes.md)  
[Filtering](ui-enter-criteria-filters.md#filtering)  
[Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
