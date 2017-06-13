---
title: "How to: Validate Customer Data"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "RapidStart Services, customer data"
ms.assetid: c5058b33-8de0-4d25-833f-2384c2f111b4
caps.latest.revision: 8
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Validate Customer Data
Customer data must be validated before you apply the records to the [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] database.  
  
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
 [How to: Apply Customer Data](../SetupAndAdministration/how-to-apply-customer-data.md)