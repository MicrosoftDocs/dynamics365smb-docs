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
# How to: Validate Customer Data
Customer data must be validated before you apply the records to the ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> database.  
  
> [!NOTE]  
>  In most cases, invalid data is not created in the database. However, the application can occasionally be blocked if an imported migration table contains errors.  
  
### To validate customer data  
  
1.  In the **Migration Overview** window, review the **No. of Migration Errors** field to see whether any errors occurred during import.  
  
2.  If there are errors, select the migration table and on the **Tables** FastTab, choose **Table**, and then choose **Errors**. The **Invalid** check box is selected for each record that has an error.  
  
3.  To review errors, select a line and on the **Home** tab choose **Show Error**.  
  
     The **Error Text** field contains the reason for the error. The **Field Caption** field contains the caption of the field that contains the error.  
  
4.  To correct an error or otherwise make an update, close the **Migration Data Errors** window. On the **Navigate** tab, choose **Migration Record**. The **Migration Record** window opens. Select the record with the error and make the correction.  
  
     After you make a correction, the record is removed from the list of records in the **Migration Data Errors** window.  
  
 You are now ready to apply the customer’s data to the database.  
  
## See Also  
 [How to: Apply Customer Data](../how-to-apply-customer-data.md)