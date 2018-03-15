---
    title: Design Details - Table Structure | Microsoft Docs
    description: To understand how the dimension entry storing and posting is redesigned, it is important to understand the table structure.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Design Details: Table Structure
To understand how the dimension entry storing and posting is redesigned, it is important to understand the table structure.  

## New Tables  
 Three new tables have been designed to manage dimension set entries.  

### Table 480 Dimension Set Entry  
 Table 480 **Dimension Set Entry** is a new table. You cannot change this table. After data has been written to the table, you cannot delete or edit it. Deleting data requires that you check against all occurrences of the dimension set ID in the entire database, including partner solutions.  

|Field No.|Field Name|Data Type|Comment|  
|---------------|----------------|---------------|-------------|  
|1|**ID**|Integer|>0.0 is reserved for the empty dimension set. References field 3 in table 481.|  
|2|**Dimension Code**|Code 20|Table relation to table 348.|  
|3|**Dimension Value Code**|Code 20|Table relation to table 349.|  
|4|**Dimension Value ID**|Integer|References field 12 in table 349. It is the secondary key that is used when traversing table 481.|  
|5|**Dimension Name**|Text 30|CalcField. Lookup to table 348.|  
|6|**Dimension Value Name**|Text 30|CalcField. Lookup to table 349.|  

#### Table 481 Dimension Set Tree Node  
 Table 481 **Dimension Set Tree Node** is a new table. You cannot change this table. It is used to search for a dimension set. If the dimension set is not found, a new set is created.  

|Field No.|Field Name|Data Type|Comment|  
|---------------|----------------|---------------|-------------|  
|1|**Parent Dimension Set ID**|Integer|0 for top level node.|  
|2|**Dimension Value ID**|Integer|Table relation to field 12 in table 349.|  
|3|**Dimension Set ID**|Integer|AutoIncrement. Used in field 1 in table 480.|  
|4|**In Use**|Boolean|False if not in use.|  

##### Table 482 Reclas. Dimension Set Buffer  
 Table 482 **Reclas. Dimension Set Buffer** is a new table. The table is used to edit a dimension set ID. It is required when you edit a dimension value code and a new dimension value code, for example, in the **Item Reclas. Journal** table.  

|Field No.|Field Name|Data Type|Comment|  
|---------------|----------------|---------------|-------------|  
|1|**Dimension Code**|Code 20|Table relation to table 348.|  
|2|**Dimension Value Code**|Code 20|Table relation to table 349.|  
|3|**Dimension Value ID**|Integer|References field 12 in table 349.|  
|4|**New Dimension Value Code**|Code 20|Table relation to table 349.|  
|5|**New Dimension Value ID**|Integer|References field 12 in table 349.|  
|6|**Dimension Name**|Text 30|CalcField. Lookup to table 348.|  
|7|**Dimension Value Name**|Text 30|CalcField. Lookup to table 349.|  
|8|**New Dimension Value Name**|Text 30|CalcField. Lookup to table 349.|  

## Modified Tables  
 All transaction and budget tables have been modified to manage dimension set entries.  

### Changes to Transaction and Budget Tables  
 A new field has been added to all transaction and budget tables.  

|Field No.|Field Name|Data Type|Comment|  
|---------------|----------------|---------------|-------------|  
|480|**Dimension Set ID**|Integer|References field 1 in table 480.|  

#### Changes to Table 83 Item Journal Line  
 Two new fields have been added to table 83 **Item Journal Line**.  

|Field No.|Field Name|Data Type|Comment|  
|---------------|----------------|---------------|-------------|  
|480|**Dimension Set ID**|Integer|References field 1 in table 480.|  
|481|**New Dimension Set ID**|Integer|References field 1 in table 480.|  

##### Changes to Table 349 Dimension Value  
 A new field has been added to table 349 **Dimension Value**.  

|Field No.|Field Name|Data Type|Comment|  
|---------------|----------------|---------------|-------------|  
|12|**Dimension Value ID**|Integer|AutoIncrement. Used for references in table 480 and table 481.|  

###### Tables That Get New Field 480 Dimension Set ID  
 A new field, 480 **Dimension Set ID**, has been added to the following tables. For the tables that store posted data, the field only provides a non-editable display of dimensions, which is marked as Drill-down. For the tables that store working documents, the field is editable. The buffer tables that are used internally do not need editable or non-editable capabilities.  

 The 480 field is non-editable in the following tables.  

|Table No.|Table Name|  
|---------------|----------------|  
|17|**G/L Entry**|  
|21|**Cust. Ledger Entry**|  
|25|**Vendor Ledger Entry**|  
|32|**Item Ledger Entry**|  
|110|**Sales Shipment Header**|  
|111|**Sales Shipment Line**|  
|112|**Sales Invoice Header**|  
|113|**Sales Invoice Line**|  
|114|**Sales Cr.Memo Header**|  
|115|**Sales Cr.Memo Line**|  
|120|**Purch. Rcpt. Header**|  
|121|**Purch. Rcpt. Line**|  
|122|**Purch. Inv. Header**|  
|123|**Purch. Inv. Line**|  
|124|**Purch. Cr. Memo Hdr.**|  
|125|**Purch. Cr. Memo Line**|  
|169|**Job Ledger Entry**|  
|203|**Res. Ledger Entry**|  
|271|**Bank Account Ledger Entry**|  
|281|**Phys. Inventory Ledger Entry**|  
|297|**Issued Reminder Header**|  
|304|**Issued Fin. Charge Memo Header**|  
|5107|**Sales Header Archive**|  
|5108|**Sales Line Archive**|  
|5109|**Purchase Header Archive**|  
|5110|**Purchase Line Archive**|  
|5601|**FA Ledger Entry**|  
|5625|**Maintenance Ledger Entry**|  
|5629|**Ins. Coverage Ledger Entry**|  
|5744|**Transfer Shipment Header**|  
|5745|**Transfer Shipment Line**|  
|5746|**Transfer Receipt Header**|  
|5747|**Transfer Receipt Line**|  
|5802|**Value Entry**|  
|5832|**Capacity Ledger Entry**|  
|5907|**Service Ledger Entry**|  
|5908|**Service Header**|  
|5933|**Service Order Posting Buffer**|  
|5970|**Filed Service Contract Header**|  
|5990|**Service Shipment Header**|  
|5991|**Service Shipment Line**|  
|5992|**Service Invoice Header**|  
|5993|**Service Invoice Line**|  
|5994|**Service Cr. Memo Header**|  
|5995|**Service Cr. Memo Line**|  
|6650|**Return Shipment Header**|  
|6651|**Return Shipment Line**|  
|6660|**Return Receipt Header**|  
|6661|**Return Receipt Line**|  

 The 480 field is editable in the following tables.  

|Table No.|Table Name|  
|---------------|----------------|  
|36|**Sales Header**|  
|37|**Sales Line**|  
|38|**Purchase Header**|  
|39|**Purchase Line**|  
|81|**Gen. Journal Line**|  
|83|**Item Journal Line**|  
|89|**BOM Journal Line**|  
|96|**G/L Budget Entry**|  
|207|**Res. Journal Line**|  
|210|**Job Journal Line**|  
|221|**Gen. Jnl. Allocation**|  
|246|**Requisition Line**|  
|295|**Reminder Header**|  
|302|**Finance Charge Memo Header**|  
|5405|**Production Order**|  
|5406|**Prod. Order Line**|  
|5407|**Prod. Order Component**|  
|5615|**FA Allocation**|  
|5621|**FA Journal Line**|  
|5635|**Insurance Journal Line**|  
|5740|**Transfer Header**|  
|5741|**Transfer Line**|  
|5900|**Service Header**|  
|5901|**Service Item Line**|  
|5902|**Service Line**|  
|5965|**Service Contract Header**|  
|5997|**Standard Service Line**|  
|7134|**Item Budget Entry**|  
|99000829|**Planning Component**|  

 The 480 field has been added to the following buffer tables.  

|Table No.|Table Name|  
|---------------|----------------|  
|49|**Invoice Post. Buffer**|  
|212|**Job Posting Buffer**|  
|372|**Payment Buffer**|  
|382|**CV Ledger Entry Buffer**|  
|461|**Prepayment Inv. Line Buffer**|  
|5637|**FA G/L Posting Buffer**|  
|7136|**Item Budget Buffer**|  

## See Also  
 [Design Details: Dimension Set Entries](design-details-dimension-set-entries.md)   
 [Dimension Set Entries Overview](design-details-dimension-set-entries-overview.md)   
 [Design Details: Searching for Dimension Combinations](design-details-searching-for-dimension-combinations.md)   
 [Design Details: Codeunit 408 Dimension Management](design-details-codeunit-408-dimension-management.md)   
 [Design Details: Code Examples of Changed Patterns in Modifications](design-details-code-examples-of-changed-patterns-in-modifications.md)
