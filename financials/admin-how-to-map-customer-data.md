---
    title: How to Map Customer Data | Microsoft Docs
    description: You can map values from an existing ERP system into your Business Central already has.
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
# Map Customer Data
You can map values from an existing ERP system into your [!INCLUDE[d365fin](includes/d365fin_md.md)] already has.  

In the procedures that follow, you should review in advance which values you want to retain during the migration process. To perform the following procedures, you will need data migration files (.xls) that you have exported from Microsoft Dynamics NAV. For more information, see [Export Migration Tables].

.  

### To add additional values to [!INCLUDE[d365fin](includes/d365fin_md.md)]  

1.  Open the configuration package for the company.  

2.  Select the table for which you want to add additional values, and on the **Tables** FastTab, choose **Table**, and then choose **Fields**.  

3.  For the fields for which you want [!INCLUDE[d365fin](includes/d365fin_md.md)] to permit additional values during migration, select the **Create Missing Codes** check box.  

4.  Import the customer data. For more information, see [Import Customer Data](admin-how-to-import-customer-data.md).  

### To map values to be used during import to [!INCLUDE[d365fin](includes/d365fin_md.md)]  

1.  Open the configuration package for the company.  

2.  Select the table for which you want to map values, and on the **Tables** FastTab, choose **Table**, and then choose **Fields**.  

3.  For each field that you want to map, on the **Home** tab, in the **Process** group, choose **Mapping**.  

     For more information on how mapping works, see [About Mapping](admin-about-mapping.md).  

4.  In the **Old Value** field, enter the value that you want to change. In the **New Value** field, enter the value that you want the old value to be changed to. Choose the **OK** button.  

5.  Import the customer data. For more information, see [Import Customer Data](admin-how-to-import-customer-data.md). In the **No. of Package Errors** field, see if there are any errors reported. If there are, drill down to see the errors. The **Config. Package Records** window opens.  

6.  On the **Home** tab, in the **Process** group, choose **Show Error**. You will receive the following error: **<option> is not a valid option. Valid options are <valid option list>**. Choose the **OK** button.  

     To apply the mapping that you have set up, on the **Home** tab, in the **Process** group, choose **Apply Data.**  

## See Also  

 [Apply Customer Data](admin-how-to-apply-customer-data.md)   
 [Clean Up and Process Data](admin-how-to-clean-up-and-process-data.md)   
