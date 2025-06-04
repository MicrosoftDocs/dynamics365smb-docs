---
title: Coupling and synchronizing
description: Synchronizing an integration table mapping enables data syncing in all records in a table in Business Central and Sales tables that are coupled.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 04/25/2025
ms.custom: bap-template
ms.search.keywords: crm, sales, couple, decouple, synchronize
ms.search.form: 6250,
ms.service: dynamics-365-business-central
---

# Couple and synchronize records between Dataverse and Business Central

This article describes how to couple one or more records in [!INCLUDE[prod_short](includes/prod_short.md)] with records in Dataverse or [!INCLUDE[crm_md](includes/crm_md.md)]. Coupling records lets you view Dataverse information from [!INCLUDE[prod_short](includes/prod_short.md)], and vice versa. The coupling also enables you to synchronize data between the records. You can couple existing records, or create and couple new records.

> [!NOTE]
> Coupling and synchronizing data is available only if your system administrator creates a connection between [!INCLUDE[prod_short](includes/prod_short.md)] and Dataverse or [!INCLUDE[crm_md](includes/crm_md.md)]. A quick way to check is to open the **Customer** card and look for the **Set Up Coupling** action. If the action is available, the apps are connected.

<!--## Video Example

This video shows coupling and synchronizing data in the context of an integration with [!INCLUDE[crm_md](includes/crm_md.md)].

> [!VIDEO https://go.microsoft.com/fwlink/?linkid=2098376] -->

## To couple a record  

1. In [!INCLUDE[prod_short](includes/prod_short.md)], open the card for the record you want to couple. For example, the Customer Card or Contact Card pages.  

    You can also just open the list page and select the record that you want to couple.  

2. Choose the **Set Up Coupling** action.  
3. Fill in the fields, and then choose **OK**.  

## To synchronize a single record  

1. In [!INCLUDE[prod_short](includes/prod_short.md)], open the card for the record you want to couple. For example, the Customer Card or Contact Card pages.  
2. Choose the **Synchronize Now** action.  
3. If a record can synchronize in one direction, select the option that specifies the direction of data update, and then choose **OK**.  

## To synchronize a single record from [!INCLUDE[crm_md](includes/crm_md.md)]  

1. In [!INCLUDE[crm_md](includes/crm_md.md)], open the form for the record you want to couple. For example, the Account or Contact pages.  
2. Choose the **[!INCLUDE[prod_short](includes/prod_short.md)]** action in the ribbon to open and couple records automatically.

    > [!Note]
    > You can synchronize a single record from [!INCLUDE[crm_md](includes/crm_md.md)] automatically only when **Sync. Only Coupled Records** is disabled and the synchronization direction is set to **Bidirectional** or **From Integration Table** on the **Integration Table Mapping** page for the record. To learn more, go to [Mapping the Tables and Fields to Synchronize](admin-how-to-modify-table-mappings-for-synchronization.md#create-new-records).

## To couple multiple records using match-based coupling

Specify the data to synchronize for an entity, such as a customer or contact, by coupling records based on matches. Refine the matches by making the search case sensitive, and assigning a priority for each match. If no match is found, you can also specify that you want to create the entity in Dataverse. To learn more, go to [Customize the match-based coupling](admin-how-to-set-up-a-dynamics-crm-connection.md#customize-the-match-based-coupling).  

> [!NOTE]
> The match-based coupling process skips records that are already matched. To include those records when you run match-based coupling, uncouple the records and then try again. To learn more about uncoupling records, go to [Uncoupling Records](#uncoupling-records).

1. In [!INCLUDE[prod_short](includes/prod_short.md)], open the list page for the record, such as the Customers or Contacts list pages.
2. Choose the **Match-Based Coupling** action.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To synchronize multiple records  

1. In [!INCLUDE[prod_short](includes/prod_short.md)], open the list page for the record, such as the Customers or Contacts pages.  
2. Select the records that you want to synchronize, and then choose the **Synchronize Now** action.  
3. If records can synchronize in one direction, select the option that specifies the direction, and then choose **OK**.  

## Bulk-insert and couple records

If you have many Dataverse entities that correspond to records in [!INCLUDE [prod_short](includes/prod_short.md)], you can insert and couple them in-bulk. For example, you might want to bulk-insert and couple records when you're setting up synchronization for the first time.

Use the **Data import wizard** in the **Microsoft Power Platform admin center**.

The following example describes how to bulk-insert and couple customers with accounts in Dataverse. Use the same process for other types of entities, such as vendors, items, and resources.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Choose the **Open in Excel** action to open customer data in Excel.
3. To map and import data to the **Account** entity in Dataverse, follow the steps described in [Import data (all record types) from multiple sources](/power-platform/admin/import-data-all-record-types).  

    If the Account entity has a **bcbi_companyid** column, when you map the data columns make sure that the import assigns the appropriate company ID in the column for every imported record. To find the company ID in [!INCLUDE [prod_short](includes/prod_short.md)], follow these steps:

    1. Open the **Integration Table Mappings** page.
    2. Choose the **CUSTOMER** mapping, and then choose **Edit List**.
    3. Choose the assist edit :::image type="icon" source="media/assist-edit-icon.png" border="false"::: button in the **Integration Table Filter** field. This shows the default filter for customer mapping, and it contains the company ID. The company ID is the first part of the value. Copy only that part, and disregard the 0s. The following example highlights the part to copy.

    :::image type="content" source="media/dataverse-company-id-guid.png" alt-text="Shows the part of the company ID to copy.":::

    > [!NOTE]
    > Not all of the names of Dataverse entities and [!INCLUDE [prod_short](includes/prod_short.md)] records match. Depending on what you're importing, double-check that the following columns have the following values after you import:
    >
    >* For customers, the **CustomerTypeCode** column should contain **Customer**.
    >* For vendors, the **CustomerTypeCode** column should contain **Vendors**. 
    >* For items, **ProductTypeCode** column should contain **Sales Inventory**.
    >* For resources, the **ProductTypeCode** column should contain **Service**.
 
4. After you import data to the Dataverse environment, in [!INCLUDE [prod_short](includes/prod_short.md)], follow the steps [To couple multiple records using match-based coupling](#to-couple-multiple-records-using-match-based-coupling) to couple the Dataverse entities with [!INCLUDE [prod_short](includes/prod_short.md)] records.

## Uncoupling Records

You can uncouple one or more records from list pages or the **Coupled Data Synchronization Errors** page by choosing one or more lines and choosing **Delete Coupling**. You can also remove all couplings for one or more table mappings on the **Integration Table Mappings** page.

## Related information

[Use Dynamics 365 Sales from Business Central](marketing-integrate-dynamicscrm.md)  
[View the Status of Synchronization Jobs](admin-how-to-view-synchronization-status.md)  
[Use Dynamics 365 Sales from Business Central](marketing-integrate-dynamicscrm.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
