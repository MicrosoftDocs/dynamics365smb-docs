---
    title: Prepare Customer Data Migration | Microsoft Docs
    description: After you import and apply setup data in the new database, you can start migrating the customer’s existing master data, such as item and customer numbers and names. To make sure that this data is created quickly and accurately in the new company, you should use templates to structure the data.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 03/07/2018
    ms.author: sgroespe

---
# Prepare to Migrate Customer Data
After you import and apply setup data in the new database, you can start migrating the customer’s existing master data, such as item and customer numbers and names. To make sure that this data is created quickly and accurately in the new company, you should use templates to structure the data.  

Typically, you create data templates for the following master data tables:  

-   **Contact**  
-   **Customer**  
-   **Item**  
-   **Vendor**  

However, you can create a template structure for and apply it to any table in [!INCLUDE[d365fin](includes/d365fin_md.md)].  

> [!TIP]  
>  You can also use data templates for daily operations to create new records that are based on templates. These data templates only work for the supported master data tables. For more information, see, for example, [Register New Items](inventory-how-register-new-items.md).  

When you import customer data, such as for items, from a file, the mandatory field data that you have specified is taken from the linked data template. When you create a new item, you only enter general information such as item name, description, and price and then collect the rest of the mandatory field data from a selected data template.  

When you create a new master data record, such as a customer card, some fields are mandatory and must be filled in. You can group most mandatory fields, such as posting groups and payment terms, to make creating master data records easier and more stable. For example, you can group mandatory fields for table 18, **Customer**, as **Domestic**, **Foreign**, or **Export** types.

## To select a data template
When you select an existing data template, you must evaluate if the templates that you created for the new company are sufficient for the customer. Review the provided fields and values to determine which templates are appropriate for a new company.  

> [!TIP]  
>  You can also use data templates to create new records quickly. Use them for faster and more accurate data creation. For more information, see [Register New Items](inventory-how-register-new-items.md).

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Configuration Templates**, and then choose the related link.  
2. In the **Config. Template List** window, select a data template from the list, and then choose the **Edit** action.  

If the default templates do not meet your needs, you can create new templates or add fields to an existing template. If the default templates are sufficient, you can use them to create records based on master data templates.

## To create a data template
You can create a new data template if the default templates do not the needs of your new company. If you are creating more than one, you may find it useful to adopt a naming convention for the **Code** field.

Each template consists of a header and lines. When you create a template, you can specify which fields to always apply to data of a certain type. For example, you can create different customer templates to apply to different customer types. When you create the customer using a template, you can use template data to prepopulate certain fields.

### To create a data template header
1. Open the **Config. Template List** window.
2. Choose the **New** action.
3. In the **Table ID** field, enter the table to which this template applies. The **Table Name** field is automatically filled in when the **Table ID** field is set.

### To create a data template line
1. On the first line, select the **Field Name** field. The **Field List** window displays the list of fields in the table.
2. Select a field, and then choose the **OK** button. The **Field Caption** field is filled in with the field name.
3. In the **Default Value** field, enter an appropriate value. In some cases, you may want to use a value that is not a value that is available in the database. In that case, you can select the **Skip Relation Check** check box, to make it possible to apply data without error.

    > [!TIP]  
    > Since the **Default Value** field does not have a look up to the corresponding [!INCLUDE[d365fin](includes/d365fin_md.md)] field options, you copy and paste the value that you want from the related page into the template.

    > Select the **Mandatory** check box. The check box is informational only. It tells you that information must be entered in the field by the user, but no business logic is enforced. For example, you cannot invoice and post an order if posting groups have not been set up. Since posting groups are required, you can select the **Mandatory** check box for those fields.

3. In the **Reference** field, enter information about the field as needed.
4. Choose the **OK** button

## To export to a template in Excel
You can create an Excel workbook to serve as a template that is based on the structure of an existing database table quickly. You can then use the template to gather together customer data in a consistent format for later import into [!INCLUDE[d365fin](includes/d365fin_md.md)].

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Configuration Worksheet**, and then choose the related link.
2. Add a table to the list, or select an existing table. For more information, see [Manage Company Configuration in a Worksheet](admin-how-to-manage-company-configuration-in-a-worksheet.md).
3. Define the fields from the table that you want to include in the template.
4. Choose the **Export to Template** action.
5. Name and save the Excel file. The Excel workbook is automatically opened.

You can now enter customer data in the Excel worksheet. If you have exported multiple tables, each table will be on its own worksheet. Save the workbook before you continue with the next procedure.

> [!NOTE]  
> You may encounter the following error when you run an English version of Excel, but have your regional settings configured for a non-English language: "Old format or invalid type library." To fix this error, make sure that the language pack for the non-English language is installed.

## To import from a template in Excel
1. In the **Config. Worksheet** window, choose the **Import from Template** action.
3. Navigate to the template worksheet that you have created, and then choose the **Open** action.
4. To add the collected customer data to the database, choose the **Apply Data** action.

When you apply data from a template in Excel to a table that also has a configuration template linked to it in the configuration package, the default field values from the configuration template are also applied.

Any record whose data is applied in this manner is complete, because it consists of data entered by a user in Excel, plus the default values specified by the configuration template.

## To create a record from a configuration template
You can use the structure of data that is contained in the data templates to convert your information into records in the database, one-by-one. To do so, you use the **Create Instance** function. This is a miniature version of the data migration process and can be useful for prototyping or treating smaller data creation tasks.  

The following steps illustrate how to create an item card from an item data template. You can create a record from any data template using the same procedure.  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Configuration Templates**, and then choose the related link.  
2. Select the **Item** template, and then choose the **Edit** action. For more information, see the "To create a data template" section.
3. Choose the **Create Instance** action. An item card is created.  
4. Choose the **OK** button.  
5. To review the new item card, choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Items**, and then choose the related link.  
6. Open the new item card.  
7. Expand various FastTabs, and verify that the information was created correctly on them.  

## To use a configuration template on a record
You can apply a data template to any record that is in [!INCLUDE[d365fin](includes/d365fin_md.md)] and use this technique to change or modify a record. However, when you do this, you overwrite existing values in the record with those of the template. Consequently, you should be careful when you apply a template to existing records.

> [!WARNING]  
>  The **Apply Template** function overwrites existing data in a record. If this function is used in master data migration, it will overwrite the imported data when you create records.

The following procedure is based on a new customer card.  

1. Create a customer. For more information, see [Register New Customers](sales-how-register-new-customers.md).
2. In the **Customer Card** window, choose the **Apply Template** action.  
3. In the **Customer Templates** window, select one of the templates, and then choose the **OK** button.  

The default values from the chosen customer template are inserted on the customer card.

## See Also  
[Setting Up a Company With RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)  
[Register New Customers](sales-how-register-new-customers.md)
