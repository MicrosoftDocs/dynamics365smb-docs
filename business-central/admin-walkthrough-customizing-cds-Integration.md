---
title: Custom Integration with Common Data Service
description: Learn how to integrate your extension with Common Data Service.
author: bholtorf

ms.custom: na
ms.reviewer: na
ms.topic: article
ms.service: "dynamics365-business-central"
ms.author: bholtorf
ms.date: 01/08/2020
---

# Walkthrough: Customizing an Integration with Common Data Service
This walkthrough describes how to customize an integration between [!INCLUDE[prodshort](includes/prodshort.md)] and Common Data Service (CDS). The walkthrough will guide you through setting up integration of an employee in [!INCLUDE[prodshort](includes/prodshort.md)] and worker in CDS. 

## About This Walkthrough
This walkthrough describes how to integrate new and existing extensions with CDS. At a high-level, those process involve the following tasks:  

- Develop an AL extension to integrate entities in CDS and [!INCLUDE[prodshort](includes/prodshort.md)]. <!--Add a link to a topic about developing AL extensions. [About Developing Extensions in AL]().-->

    -   Create an integration table object in [!INCLUDE[prodshort](includes/prodshort.md)] for mapping a CDS entity to a [!INCLUDE[prodshort](includes/prodshort.md)] record type.  
    -   Use a CDS integration table as a data source for a page in [!INCLUDE[prodshort](includes/prodshort.md)] that displays data from CDS entity records.  
    -   Extend a page in [!INCLUDE[prodshort](includes/prodshort.md)] for coupling and sychronizing entity records in CDS with table records in [!INCLUDE[prodshort](includes/prodshort.md)].  
    -   Use events to create an integration table and a field mapping between a table in [!INCLUDE[prodshort](includes/prodshort.md)] table and an integration table for CDS.  
-   Develop an extension to extend an existing integration between entities in CDS and [!INCLUDE[prodshort](includes/prodshort.md)]. 
    -   Create a table extension for an existing integration table object.
    -   Use events to add custom integration field mappings for existing integration table mappings.

> [!NOTE]
> The customization in this walkthrough is done entirely in the online version of [!INCLUDE[prodshort](includes/prodshort.md)], and does not describe how to modify your CDS solution, such as adding or modify entities and forms.  

## Requirements  
This walkthrough requires the following:  

-   CDS, including the following:  
    -   A worker entity.  
    -   The URL of your CDS environment.
    -   The user name and password of a user account that has full permissions to add and modify entities.  
-   [!INCLUDE[prodshort](includes/prodshort.md)], including the following:  
    -  The CRONUS International Ltd. demonstration data.  <!--need to tell them where they can get the data -->
    -   CDS integration is enabled, including the default synchronization setup and a working connection between [!INCLUDE[prodshort](includes/prodshort.md)] and CDS. <!--For more information, see []()....  -->
    -   Visual Studio Code with the AL Language extension installed. For more information, see [AL Language Extension Configuration](devenv-al-extension-configuration.md). The AL Language extension for Visual Studio is free, and you can download it [here](https://marketplace.visualstudio.com/items?itemName=ms-dynamics-smb.al).

## Create an Integration Table in [!INCLUDE[prodshort](includes/prodshort.md)] for the CDS Entity  
To integrate data from a CDS entity into [!INCLUDE[prodshort](includes/prodshort.md)], you must create a table object in [!INCLUDE[prodshort](includes/prodshort.md)] that is based on the CDS entity, and then import the new table into the [!INCLUDE[prodshort](includes/prodshort.md)] database. For this walkthrough we will create a table object that describes the schema for the **Worker** entity in CDS in the [!INCLUDE[prodshort](includes/prodshort.md)] database. 

> [!NOTE]
> The table can contain some or all of the fields from the CDS entity. However, if you want to set up bi-directional synchronization you must include all fields in the table.  

### To create the integration table for the worker entity in CDS 
1.  Create a new AL extension. <!--For more information, see [About Developing Extensions in AL]()-->
2.  Export the **altpgen.exe** AL Table Proxy Generator from the VS Code AL extension. This executable tool allows you to create integration tables. <!--Talk to Susanne about this new thing?-->

3.  In PowerShell, run the tool with the following arguments:

    ```  
    -project:<Your AL project folder>
    -packagecachepath:<Your AL project cache folder>
    -serviceuri:<CDS server URL>
    -username:<Admin username for CDS>
    -password:<Password>
    -entities:cdm_worker
    -baseid:50001  
    ```

     This starts the process for creating the table. When completed, the output path contains the **Worker.al** file that contains the description of the **50001 CDS Worker** integration table. This table is set to the table type **CDS**.

## Create a Page for Displaying CDS Data  
For scenarios where we want to view CDS data for a specific entity, we can create a page object that uses the integration table for the CDS entity as its data source. For example, we might want to have a list page that displays the current records in a CDS entity, such as all workers. In this walkthrough we will create a list page that uses table 50001 CDS Worker as its data source.  

### To create a list page to display CDS workers  
1. Create a new page. For more information, see [Pages Overview](devenv-pages-overview.md). 
2. Name the page **CDS Worker List**, and specify **50001** as the page ID.  
3. Specify the **50001 CDS Worker** integration table as the source table. For example:
```
page 50001 "CDS Worker List"
{
    PageType = List;
    SourceTable = "CDS Worker";
    Editable = true;
    ContextSensitiveHelpPage = 'feature-overview';
    ...
}
``` 

4. Add the fields from the integration table to display on the page. 


## Enable Coupling and Synchorinization between Campaigns in CDS and [!INCLUDE[prodshort](includes/prodshort.md)]
To connect a [!INCLUDE[prodshort](includes/prodshort.md)] table record with a CDS entity record, you create a coupling. A coupling consists of the primary ID, which is typically a GUID, from a CDS record and the Integration ID, also often a GUID, from [!INCLUDE[prodshort](includes/prodshort.md)].  

1. In codeunit **7204 "CDS Setup Defaults"**, subscribe to the **OnGetCDSTableNo** event, as follows:

```
[EventSubscriber(ObjectType::Codeunit, Codeunit::"CDS Setup Defaults", 'OnGetCDSTableNo', '', true, true)]
local procedure HandleOnGetCDSTableNo(BCTableNo: Integer; var CDSTableNo: Integer)
begin
    if BCTableNo = DATABASE::Employee then
        CDSTableNo := DATABASE::"CDS Worker";
end;
```

Now we must enable integration records for the table in [!INCLUDE[prodshort](includes/prodshort.md)] that will be used for integration with CDS. In this case, that's **table 5200 Employee**. The following code example is a subscriber to the **OnIsIntegrationRecord** event in **codeunit 5150 "Integration Management"** that we can use to enable integration records for **table 5200 Employee**.

```
[EventSubscriber(ObjectType::Codeunit, Codeunit::"Integration Management", 'OnIsIntegrationRecord', '', true, true)]
local procedure HandleOnIsIntegrationRecord(TableID: Integer; var isIntegrationRecord: Boolean)
begin
    if TableID = DATABASE::Employee then
        isIntegrationRecord := true;
end;
```

### To create actions on the employee page for managing coupling and synchronization
To enable users to create couplings between records in the two systems, we'll extend **page 5200 "Employee Card"** with actions for creating and deleting couplings, and for synchronizing. The following code example adds those actions to **page 5200 "Employee Card"**.

```
pageextension 50001 "Employee Synch Extension" extends "Employee Card"
{
    actions
    {
        addlast(Navigation)
        {
            group(ActionGroupCDS)
            {
                Caption = 'CDS';

                action(CRMSynchronizeNow)
                {
                    Caption = 'Synchronize';

                    trigger OnAction()
                    var
                        CRMIntegrationManagement: Codeunit "CRM Integration Management";
                    begin
                        CRMIntegrationManagement.UpdateOneNow(RecordId);
                    end;
                }
                action(ShowLog)
                {
                    Caption = 'Synchronization Log';

                    trigger OnAction()
                    var
                        CRMIntegrationManagement: Codeunit "CRM Integration Management";
                    begin
                        CRMIntegrationManagement.ShowLog(RecordId);
                    end;
                }
                action(ManageCRMCoupling)
                {
                    Caption = 'Set Up Coupling';

                    trigger OnAction()
                    var
                        CRMIntegrationManagement: Codeunit "CRM Integration Management";
                    begin
                        CRMIntegrationManagement.DefineCoupling(RecordId);
                    end;
                }
                action(DeleteCRMCoupling)
                {
                    Caption = 'Delete Coupling';

                    trigger OnAction()
                    var
                        CRMCouplingManagement: Codeunit "CRM Coupling Management";
                    begin
                        CRMCouplingManagement.RemoveCoupling(RecordId);
                    end;
                }
            }
        }
    }
}
```

## Create Integration Table Mappings and Field Mappings  
For synchronization to work, mappings must exist to associate the table ID and fields of the integration table (in this case, **table 50001 CDS Worker**) with the table in [!INCLUDE[prodshort](includes/prodshort.md)] (in this case table **5200 Employee**). There are two types of mapping:  

- **Integration table mapping** - Integration table mapping links the [!INCLUDE[prodshort](includes/prodshort.md)] table to the integration table for the CDS entity.  
- **integration field mapping** - Field mapping links a field in an entity record in CDS with a field in a record in [!INCLUDE[prodshort](includes/prodshort.md)]. This determines which field in [!INCLUDE[prodshort](includes/prodshort.md)] corresponds to which field in CDS. Typically, there are multiple field mappings for an entity.  

In this scenario, we will create integration table and field mappings so that we can synchronize data for a worker in CDS with an employee in [!INCLUDE[prodshort](includes/prodshort.md)]. 

### To create an integration table mappings  
We can create the integration table mapping by subscribing to the **OnAfterResetConfiguration** event in codeunit **7204 "CDS Setup Defaults"**.

1. Create a codeunit.  
2. Add a local procedure called **InsertIntegrationTableMapping**, as follows:

    ```
    local procedure InsertIntegrationTableMapping(var IntegrationTableMapping: Record "Integration Table Mapping"; MappingName: Code[20]; TableNo: Integer; IntegrationTableNo: Integer; IntegrationTableUIDFieldNo: Integer; IntegrationTableModifiedFieldNo: Integer; TableConfigTemplateCode: Code[10]; IntegrationTableConfigTemplateCode: Code[10]; SynchOnlyCoupledRecords: Boolean)
    begin
        IntegrationTableMapping.CreateRecord(MappingName, TableNo, IntegrationTableNo,  IntegrationTableUIDFieldNo, IntegrationTableModifiedFieldNo, TableConfigTemplateCode, IntegrationTableConfigTemplateCode, SynchOnlyCoupledRecords, IntegrationTableMapping.Direction::Bidirectional, 'CDS');
    end;
    ```

3. In codeunit **7204 "CDS Setup Defaults"**, subscribe to the **OnAfterResetConfiguration** event, as follows:

    ```
    [EventSubscriber(ObjectType::Codeunit, Codeunit::"CDS Setup Defaults", 'OnAfterResetConfiguration', '', true, true)]
    local procedure HandleOnAfterResetConfiguration(CDSConnectionSetup: Record "CDS Connection Setup")
    var
        IntegrationTableMapping: Record "Integration Table Mapping";
        IntegrationFieldMapping: Record "Integration Field Mapping";
        CDSWorker: Record "CDS Worker";
        Employee: Record Employee;
    begin
        InsertIntegrationTableMapping(
            IntegrationTableMapping, 'EMPLOYEE-WORKER',
            DATABASE::Employee, DATABASE::"CDS Worker",
            CDSWorker.FieldNo(cdm_workerId), CDSWorker.FieldNo(ModifiedOn),
            '', '', true);

        ...
    end;
    ``` 

   For each integration table mapping entry, there must be integration field mapping entries to map the fields of the records in the table and the integration table. The next step is to add integration field mappings for each field in the Campaign table in [!INCLUDE[prodshort](includes/prodshort.md)] that we want to map to the Campaign entity in CDS.  

### To create integration fields mappings  
To create an integration field mapping, follow these steps:  

1. In codeunit **7204 "CDS Setup Defaults"**, add a local procedure called **InsertIntegrationFieldMapping**, as follows:

    ```
    procedure InsertIntegrationFieldMapping(IntegrationTableMappingName: Code[20]; TableFieldNo: Integer; IntegrationTableFieldNo: Integer; SynchDirection: Option; ConstValue: Text; ValidateField: Boolean; ValidateIntegrationTableField: Boolean)
    var
        IntegrationFieldMapping: Record "Integration Field Mapping";
    begin
        IntegrationFieldMapping.CreateRecord(IntegrationTableMappingName, TableFieldNo, IntegrationTableFieldNo, SynchDirection,
            ConstValue, ValidateField, ValidateIntegrationTableField);
    end;
    ```

2.  In the event subscriber we created for our integration table mapping (Step 3 in the previous process), after we insert the integration table mapping we'll add field mappings as follows:

    ```
    InsertIntegrationFieldMapping('EMPLOYEE-WORKER', Employee.FieldNo("First Name"), CDSWorker.FieldNo(cdm_FirstName), IntegrationFieldMapping.Direction::Bidirectional, '', true, false);
    ```      

3.  We'll repeat these steps for each field that we want to map.  

    > [!TIP]  
    >  If a field in one of the tables does not have a corresponding field in the other table, we can use a constant value.

3. After we publish the extension, we can update the default mappings to include our new integration table mapping by opening the **CDS Connection Setup** page in [!INCLUDE[prodshort](includes/prodshort.md)] and choosing **Use Default Synchronization Setup**.  

Users can now manually synchronize employee records in [!INCLUDE[prodshort](includes/prodshort.md)] with Worker entity records in CDS from the [!INCLUDE[prodshort](includes/prodshort.md)] client.  

> [!TIP]  
>  To learn how to schedule the synchronization by using a job queue entry, examine the code on the **RecreateJobQueueEntry** function in codeunit **5330 CRM Integration Management** and see how it is called by the integration code for other CDS entities in the codeunit. For more information, see [Scheduling a Synchronization](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md).

## Customizing Synchronization  
 When synchronizing data, some entities may require custom code to successfully synchronize data. Other entities might require the initialization of fields, the validation of relationships, or the transformation of data.  

 You can either use the standard transformation rules on **page 5361 "Integration Field Mapping List"** or you can transform data programmatically. For more information, see [Transformation Rules](across-how-to-set-up-data-exchange-definitions#transformation-rules).

 During the synchronization process, certain events are published and raised by **codeunit 5335 Integration Table Synch.**. We can add code that subscribes to these events so that we can add custom logic at different stages of the synchronization process. The following table describes the events that are published by **codeunit 5335 Integration Table Synch.**.  

|Event|Description|  
|-----------|-----------------|  
|OnFindUnCoupledDestinationRecord|Occurs when the process tries to synchronize an uncoupled record (new record). Use this event to implement custom resolution algorithms for automatic mapping between records. For example, use this event to automatically map records by fields. For an example, see codeunit **5341 CRM Int. Table. Subscriber**, which includes the event subscriber function **CRMTransactionCurrencyFindUncoupledDestinationRecord**. The event resolves [!INCLUDE[prodshort](includes/prodshort.md)] currency codes with ISO currency codes in CDS.|  
|OnBeforeApplyRecordTemplate|Occurs before applying configuration templates to new records, and can be used to implement algorithms for determining which configuration template to use.<!--point to section about templates.-->|  
|OnAfterApplyRecordTemplate|Occurs after configuration templates are applied to new records, and can be used to change data after configuration templates have been applied.|  
|OnBeforeTransferRecordFields|Occurs before transferring data in modified fields (which are defined in the Integration Field Mapping table) from the source table to the destination table. It can be used to validate the source or destination before the data is moved.|  
|OnAfterTransferRecordFields|Occurs after transferring modified field data (which are defined in the Integration Field Mapping table) from the source table to the destination table. It can be used to transfer additional data, validate lookups, and so on. Setting the **AdditionalFieldsWereModified** parameter will cause a destination record modification even though no fields were modified.|  
|OnBeforeInsertRecord|Occurs before inserting a new destination record, and can be used to initialize fields, such as primary keys.|  
|OnAfterInsertRecord|Occurs after a new destination record is inserted, and can be used to perform post-insert operations such as updating related data.|  
|OnBeforeModifyRecord|Occurs before modifying an existing destination record, and can be used to validate or change data before modification.|  
|OnAfterModifyRecord|Occurs after an existing destination record is modified, and can be used to perform post-modify operations such as updating related data.|  
|OnTransferFieldData|Occurs before an existing destination field value is transferred to a source field, and can be used to perform specific transformations of data when the data types of the source and the destination field are different but can be mapped.|  

For more information about how to subscribe to events, see [Subscribing to Events](Subscribing-to-Events.md).

## Create a Table Extension for an Integration Table in [!INCLUDE[prodshort](includes/prodshort.md)]
Let's explore another scenario. Let's say that we have added a **Shoe Size** field to the **Contact** entity in our CDS solution, and now we want to include the field in our integration with CDS.

### To create the integration table extension for table 5342 "CRM Contact"
1.  Create a new AL extension.
2.  Export AL Table Proxy Generator **altpgen.exe** from the VS Code AL extension.  

3.  In PowerShell, run the tool with the following arguments:

    ```  
    -project:<Your AL project folder>
    -packagecachepath:<Your AL project cache folder>
    -serviceuri:<CDS server URL>
    -username:<Admin username for CDS>
    -password:<Password>
    -entities:contact
    -baseid:60001  
    ```

     <!--New para needed. The process for creating the table starts. The AL Table Proxy Generator tool finds that an integration table for the **Contact** entity already exists, so it creates a table extension with only new fields, in this case **Shoe Size**. When the process is completed, the output path contains the Worker.al file <!--so this is a new .al file, or an update to the earlier one? with the description of the integration table **50001 CDS Worker**. These tables are set to the type **CDS**.-->

## Extend the Contact Table and Page with the Shoe Size Field
To synchronize the **Shoe Size** field we need to add the field in [!INCLUDE[prodshort](includes/prodshort.md)]. The following code example extends **table 5050 "Contact"** and **page 5050 "Contact Card"** with new the field.

```
tableextension 60001 ContactExtension extends Contact
{
    fields
    {
        field(70116; "Shoe Size"; Integer)
        {
        }
    }
}

pageextension 60001 ContactCardExtension extends "Contact Card"
{
    layout
    {
        addlast(General)
        {
            field("Shoe Size"; "Shoe Size")
            {
                ApplicationArea = All;
                Caption = 'Shoe Size';
            }
        }
    }
}
```

## Add New Integration Field Mapping for Shoe Size
Now that we have the field in both [!INCLUDE[prodshort](includes/prodshort.md)] and CDS, we can add a new integration field mapping for it. To do that we will subscribe to the **OnAfterResetContactContactMapping** event in codeunit **7204 "CDS Setup Defaults"**, as follows:

```
[EventSubscriber(ObjectType::Codeunit, Codeunit::"CDS Setup Defaults", 'OnAfterResetContactContactMapping', '', true, true)]
local procedure HandleOnAfterResetContactContactMapping(IntegrationTableMappingName: Code[20])
var
    CDSContact: Record "CRM Contact";
    Contact: Record Contact;
    IntegrationFieldMapping: Record "Integration Field Mapping";
begin
    InsertIntegrationFieldMapping(
        IntegrationTableMappingName,
        Contact.FieldNo("Shoe Size"),
        CDSContact.FieldNo(cr07b_ShoeSize),
        IntegrationFieldMapping.Direction::Bidirectional,
        '', true, false);
end;
```

After we publish the extension we can update the mappings by running the **CDS Connection Setup** page and choosing **Use Default Synchronization Setup**.  

## See Also
[Overview](admin-common-data-service.md)  
[Setting Up User Accounts for Integrating with Common Data Service](admin-setting-up-integration-with-dynamics-sales.md)  
[Set Up a Connection to Common Data Service](admin-how-to-set-up-a-dynamics-crm-connection.md)  
[Synchronizing Business Central and Common Data Service](admin-synchronizing-business-central-and-sales.md)  
[Mapping the Tables and Fields to Synchronize](admin-how-to-modify-table-mappings-for-synchronization.md)  
[Manually Synchronize Table Mappings](admin-manual-synchronization-of-table-mappings.md)  
[Schedule a Synchronization](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md)  