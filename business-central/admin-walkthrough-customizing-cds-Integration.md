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
This walkthrough describes how to customize an integration between [!INCLUDE[prodshort](includes/prodshort.md)] and Common Data Service (CDS). The walkthrough will guide you through setting up integration of campaigns in [!INCLUDE[prodshort](includes/prodshort.md)] and campaigns in CDS.  

## About This Walkthrough
This walkthrough describes <!--how to integrate new and existing extensions with CDS. At a high-level, those process involve--> the following tasks:  

- Develop an extension to integrate entities in CDS and [!INCLUDE[prodshort](includes/prodshort.md)]. <!--Should this be listed as a requirement? We don't explain how to develop an extension.-->

    -   Create an integration table object in [!INCLUDE[prodshort](includes/prodshort.md)] for mapping a CDS entity to a [!INCLUDE[prodshort](includes/prodshort.md)] record type \(table\).  <!--is this a record type or a table object?-->

    -   Use a CDS integration table as a <!--data--> source for a page in [!INCLUDE[prodshort](includes/prodshort.md)] that displays <!--data--> from CDS entity records.  

    -   Extend a page in [!INCLUDE[prodshort](includes/prodshort.md)] for coupling and sychronizing entity records in CDS with table records in [!INCLUDE[prodshort](includes/prodshort.md)].  

    -   Use events to create an integration table and a field mapping between a table in [!INCLUDE[prodshort](includes/prodshort.md)] table and an integration table for CDS.  

-   Develop an extension to extend an existing integration between entities in CDS and [!INCLUDE[prodshort](includes/prodshort.md)]. 

    -   Create a table extension for an existing integration table object.
      
    -   Use events to add custom integration field mappings for existing integration table mappings.

> [!NOTE]
> The customization in this walkthrough is done entirely in <!--the online version of--> [!INCLUDE[prodshort](includes/prodshort.md)], and does not describe how to modify your CDS solution, such as adding or modify entities and forms.  

## Requirements  
This walkthrough requires the following:  

-   CDS, including the following:  

    -   <!--At least one?-->Worker entity.  

    -   The URL of your CDS Server.  <!--is this called the "CDS Server, or is it service?-->

    -   The user name and password of a user account that has full permissions to add and modify entities <!--in CDS? in the note above we said that we don't change anything in CDS.-->.  

-   [!INCLUDE[prodshort](includes/prodshort.md)], including the following:  

    -  Demo data.  <!--Is this just the standard demo data? Should we tell them where to get it, and should we recommend that they use a certain type of company, or maybe a sandbox? -->

    -   CDS integration is enabled, including the default synchronization setup and a working connection between [!INCLUDE[prodshort](includes/prodshort.md)] and CDS. <!--For more information, see []()....  -->

    -   Visual Studio Code with the AL Language extension installed. For more information, see [AL Language Extension Configuration](devenv-al-extension-configuration.md). The AL Language extension for Visual Studio is free, and you can download it [here](https://marketplace.visualstudio.com/items?itemName=ms-dynamics-smb.al).

## Creating an Integration Table in [!INCLUDE[prodshort](includes/prodshort.md)] for the CDS Entity  
To integrate data from a CDS entity into [!INCLUDE[prodshort](includes/prodshort.md)], you must create a table object in [!INCLUDE[prodshort](includes/prodshort.md)] that is based on the CDS entity, and then import the new table into the [!INCLUDE[prodshort](includes/prodshort.md)] database. For this walkthrough we will create a table object that describes the schema for the **Worker** entity in CDS in the [!INCLUDE[prodshort](includes/prodshort.md)] database. 

> [!NOTE]
> The table can contain some or all of the fields from the CDS entity. If you intend to write back to CDS, however, you must include all fields in the table. <!--by "write back" do you mean a bi-directional sync?-->  

#### To create the integration table for the Worker entity in CDS 
1.  Create a new AL extension. <!--Link to more information?-->
2.  Export the **altpgen.exe** AL Table Proxy Generator from the VS Code AL extension. This executable tool allows you to create integration tables. <!--Is this a new thing?-->

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

     This starts thee process for creating the table. When completed, the output path contains the **Worker.al** file that contains the description of the **50001 CDS Worker** integration table. These tables <!--table, or tables?--> are set to the type <!--type of what?--> **CDS**.

## Creating a Page for Displaying CDS Data  
For scenarios where we want to view CDS data for a specific entity, we can create a page object that uses the integration table for the CDS entity as its source. For example, we might want to have a page that displays a list of the current records in a CDS entity <!--such as all workers, maybe?-->. In this walkthrough we will create a list page that uses table 50001 CDS Worker as its source.  

#### To create a list page to display CDS workers  
1. Create a new page. For more information, see [Pages Overview](devenv-pages-overview.md). 
2. Set the source table to the integration table **50001 CDS Worker**. 

<!--this is in the metadata, right? maybe we can show an example? Something like

page <XXXXX> PageName
{
    PageType = List;
    SourceTable = TableName;
    Editable = true;
    ContextSensitiveHelpPage = 'feature-overview';
    ...
}

--> 

3. Add the table fields that you want to display on the page. <!--how do they do this step?--> 
4. Name the page **CDS Worker List**, and specify **50001** as the page ID.  <!--should this step be earlier?-->

## Enabling Coupling and Synchorinization between Campaigns in CDS and [!INCLUDE[prodshort](includes/prodshort.md)]
To connect a [!INCLUDE[prodshort](includes/prodshort.md)] table record with a CDS entity record, you create a coupling. A coupling consists of the primary ID, which is typically a GUID, from a CDS record and the Integration <!--table?--> ID, also often a GUID, from [!INCLUDE[prodshort](includes/prodshort.md)].  

1. In codeunit **7204 "CDS Setup Defaults"**, subscribe to the **OnGetCDSTableNo** event, as follows:

```
[EventSubscriber(ObjectType::Codeunit, Codeunit::"CDS Setup Defaults", 'OnGetCDSTableNo', '', true, true)]
local procedure HandleOnGetCDSTableNo(BCTableNo: Integer; var CDSTableNo: Integer)
begin
    if BCTableNo = DATABASE::Employee then
        CDSTableNo := DATABASE::"CDS Worker";
end;
```

Now we must enable integration records for [!INCLUDE[prodshort](includes/prodshort.md)] table that will be used for integration with CDS, in this case, table **5200 Employee**. Following code is a subscriber to event **OnIsIntegrationRecord** in codeunit **5150 "Integration Management"** that you can use to enable integration records for table **5200 Employee**.

```
[EventSubscriber(ObjectType::Codeunit, Codeunit::"Integration Management", 'OnIsIntegrationRecord', '', true, true)]
local procedure HandleOnIsIntegrationRecord(TableID: Integer; var isIntegrationRecord: Boolean)
begin
    if TableID = DATABASE::Employee then
        isIntegrationRecord := true;
end;
```

#### To create actions on the employee page for managing the coupling and synchronizing
To enable users to create couplings between records in the two systems, you extend page **5200 "Employee Card"** with actions to create and delete coupling, and synchronizing. The following code extends page **5200 "Employee Card"** with necessary actions to couple and synchronize entities.

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

## Creating Integration Table Mappings and Field Mappings  
For synchronization of data between [!INCLUDE[prodshort](includes/prodshort.md)] and CDS to work, mappings must exist to associate the table ID and fields of the integration table (in this case, table **50001 CDS Worker**) with the [!INCLUDE[prodshort](includes/prodshort.md)] business data table (in this case table **5200 Employee**). To accomplish this, we must create two types of mappings:  

- **Integration table mapping** - An integration table mapping links the [!INCLUDE[prodshort](includes/prodshort.md)] table to the integration table for the CDS entity.  
- **integration field mapping** - A field mapping associates a field in a CDS entity record with a field in a [!INCLUDE[prodshort](includes/prodshort.md)] record. This determines which field in [!INCLUDE[prodshort](includes/prodshort.md)] corresponds to which field in CDS. Typically, there are multiple field mappings for an entity.  

We can create the integration table mapping by subscribing to the **OnAfterResetConfiguration** event in codeunit **7204 "CDS Setup Defaults"**.

In this scenario, we will create integration table and field mappings so that we can synchronize data for a worker in CDS with an employee in [!INCLUDE[prodshort](includes/prodshort.md)]. 

### To Create an Integration Table Mapping  
To add an integration table mapping in codeunit **7204 "CDS Setup Defaults"**, follow these steps:  

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

### To Create Integration Fields Mappings  
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

2.  In the event subscriber we created for our integration table mapping (Step 3 in the previous process), after we insert the integration table mapping, insert field mappings as follows:

    ```
    InsertIntegrationFieldMapping('EMPLOYEE-WORKER', Employee.FieldNo("First Name"), CDSWorker.FieldNo(cdm_FirstName), IntegrationFieldMapping.Direction::Bidirectional, '', true, false);
    ```      

3.  Repeat these steps for each field that you want to map.  

    > [!TIP]  
    >  If a field in one of the tables does not have a corresponding field in the other table, you can use a constant value.

3. After you publish the extension, you can update the mappings by running the **CDS Connection Setup** page and choosing **Use Default Synchronization Setup**.  


Users can now manually synchronize [!INCLUDE[prodshort](includes/prodshort.md)] Employee records with CDS Worker entity records from the [!INCLUDE[prodshort](includes/prodshort.md)] client.  

> [!TIP]  
>  If you want to learn how to schedule the synchronization by using a job queue entry, examine the code on the **RecreateJobQueueEntry** function in codeunit **5330 CRM Integration Management** and see how it is called by the integration code for other CDS entities in the codeunit.  

## Customizing Synchronization  
 When synchronizing data, some entities may require custom code to successfully synchronize data. Other entities might require the initialization of fields, the validation of relationships, or the transformation of data.  

 You can either use transformation rules in page **5361 "Integration Field Mapping List"** (see ... for more details) or you can transform data programmatically.

 During the synchronization process, certain events are published and raised by codeunit **5335 Integration Table Synch.**. You can add code that subscribes to these events, which enables you to add custom logic at different stages of the synchronization process. The following table describes the events that are published by codeunit 5345.  

|Event|Description|  
|-----------|-----------------|  
|OnFindUnCoupledDestinationRecord|Occurs when the process tries to synchronize an uncoupled record \(new record\). Use this event to implement custom resolution algorithms for automatic mapping between records. For example, you can use this event to automatically map records by fields. You can see an example in codeunit **5341 CRM Int. Table. Subscriber**, which includes the event subscriber function **CRMTransactionCurrencyFindUncoupledDestinationRecord**. The event is used to resolve [!INCLUDE[prodshort](includes/prodshort.md)] currency codes with ISO currency codes in CDS.|  
|OnBeforeApplyRecordTemplate|Occurs before applying configuration templates to new records, and can be used to implement algorithms for determining what configuration template to use.|  
|OnAfterApplyRecordTemplate|Occurs after configuration templates are applied to new records, and can be used to change data after configuration templates have been applied.|  
|OnBeforeTransferRecordFields|Occurs before transferring data in modified fields \(which are defined in the Integration Field Mapping table\) from the source table to the destination table. It can be used to validate the source or destination before the data is moved.|  
|OnAfterTransferRecordFields|Occurs after transferring modified field data \(which are defined in the Integration Field Mapping table\) from the source table to the destination table. It can be used to transfer additional data, validate lookups, and so on. Setting the **AdditionalFieldsWereModified** parameter will cause a destination record modification even if no fields were modified.|  
|OnBeforeInsertRecord|Occurs before inserting a new destination record, and can be used to initialize fields, such as primary keys.|  
|OnAfterInsertRecord|Occurs after new destination record is inserted, and can be used to perform post-insert operations such as updating related data.|  
|OnBeforeModifyRecord|Occurs before modifying an existing destination record, and can be used to validate/change data before modification.|  
|OnAfterModifyRecord|Occurs after an existing destination record is modified, and can be used to perform post-modify operations such as updating related data.|  
|OnTransferFieldData|Occurs before an existing destination field value is going to be transferred to a source field, and can be used to perform specific transformations of data when types of the source and the destination field are different but can be mapped.|  

For more general information about how to subscribe to events, see [Subscribing to Events](Subscribing-to-Events.md).

## Creating a Table Extension to an Integration Table in [!INCLUDE[prodshort](includes/prodshort.md)]

Assume a scenario where CDS solution is extended by adding a new field **Shoe Size** to **Contact** entity. This part of the walkthrough shows how to develop an extension to extend CDS integration to include new field.

#### To create the integration table extension to the table **5342 "CRM Contact"**

1.  Create a new AL extension.

2.  Export AL Table Proxy Generator **altpgen.exe** from the VS Code AL extension. This executable tool allows you to create integration tables. 

3.  Run the tool from PowerShell with following arguments:

    ```  
    -project:<Your AL project folder>
    -packagecachepath:<Your AL project cache folder>
    -serviceuri:<CDS server URL>
    -username:<Admin username for CDS>
    -password:<Password>
    -entities:contact
    -baseid:60001  
    ```

     The process for creating the table starts. AL Table Proxy Generator tool sees that an integration table for given entity **Contact** already exists, so it creates a table extension with only new fields, in this case **Shoe Size**. When the process is completed, the output path contains the file Worker.al contains the description of the integration table **50001 CDS Worker**. These tables are set to the type **CDS**.

## Extending Contact Table and Page with Shoe Size

In order to synchronize field **Shoe Size** you need this field in [!INCLUDE[prodshort](includes/prodshort.md)]. Following code extends table **5050 Contact** and page **5050 "Contact Card"** with new field.

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

## Adding New Integration Field Mapping for Shoe Size

Now that you have the field in both [!INCLUDE[prodshort](includes/prodshort.md)] and CDS, you can add a new integration field mapping for this field. This is done by subscribing to event **OnAfterResetContactContactMapping** in codeunit **7204 "CDS Setup Defaults"** as below.

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

After you publish the extension, you can update the mappings by running the **CDS Connection Setup** page and choosing **Use Default Synchronization Setup**.  