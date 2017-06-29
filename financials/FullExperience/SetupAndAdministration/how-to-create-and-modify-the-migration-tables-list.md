---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# How to: Create and Modify the Migration Tables List
You can create new data migration files and customize them to support your business. However, a file can only be used to migrate a field that has its **FieldClass** property set to **Normal**. For more information, see [FieldClass Property](../Topic/FieldClass%20Property.md).  
  
 To learn more about using the configuration process, see [How to: Manage Company Configuration in a Worksheet](../SetupAndAdministration/how-to-manage-company-configuration-in-a-worksheet.md).  
  
### To create a data migration file  
  
1.  In the **Search** box, enter **Configuration Package**, and then choose the related link.  
  
2.  Select and open the package that you want to use to migrate data. On the **Actions** tab, choose **Get Tables**. The **Get Package Table** window opens.  
  
3.  In the **TableID** field, enter a table number or select a table from the list, for example, table 18, **Customer**. The **Table Name** field is automatically filled in.  
  
4.  Select the new migration table, and on the **Tables** toolbar, on the **Table** menu, choose **Fields** to open the **Migration Fields** window.  
  
5.  Clear the **Include Field** check box for any field that you do not want to import. On the **Actions** tab, you can also choose **Set Included** or **Clear Included**.  
  
    > [!IMPORTANT]  
    >  If the **Include Field** check box is selected by default, that field is part of the primary key. The selection should not be cleared, or errors will be introduced and the record cannot be imported.  
  
    > [!IMPORTANT]  
    >  If you include a field that has a relationship with another table, the **Validate Field** check box is automatically selected. Validation can result in the update of other fields in this and other tables and is executed in the order of the field number.  
  
     A new migration table is created.  
  
## See Also  
 [How to: Export Migration Tables](../SetupAndAdministration/how-to-export-migration-tables.md)