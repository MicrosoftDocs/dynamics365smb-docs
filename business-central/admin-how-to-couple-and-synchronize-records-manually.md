---
title: Couple and Synchronize Records Manually| Microsoft Docs
description: Synchronizing an integration table mapping enables data syncing in all records in a table in Business Central and Dynamics 365 Sales entity that are coupled.
services: project-madeira
documentationcenter: ''
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: crm, sales, couple, decouple, synchronize
ms.date: 04/01/2020
ms.author: bholtorf

---

# Couple and Synchronize Records Manually
This topic describes how to couple one or more records in [!INCLUDE[d365fin](includes/d365fin_md.md)] with records in Common Data Service or [!INCLUDE[crm_md](includes/crm_md.md)]. Coupling records lets you view Common Data Service information from [!INCLUDE[d365fin](includes/d365fin_md.md)], and vice versa. The coupling also enables you to synchronize data between the records. You can couple existing records, or create and couple new records.

> [!Note]
> Coupling and synchronizing data is available only if your system administrator has created a connection between [!INCLUDE[d365fin](includes/d365fin_md.md)] and Common Data Service or [!INCLUDE[crm_md](includes/crm_md.md)]. A quick way to check is to open the **Customer** card and look for the **Set Up Coupling** action. If the action is available, the apps are connected.   

## Video Example

> [!VIDEO https://go.microsoft.com/fwlink/?linkid=2098376]

## To couple a record  
1.  In [!INCLUDE[d365fin](includes/d365fin_md.md)], open the card for the record you want to couple. For example, the Customer or Contact card.  

    You can also just open the list page and select the record that you want to couple.  

2.  Choose the **Set Up Coupling** action.  
3.  Fill in the fields, and then choose **OK**.  

## To synchronize a single record  
1.  In [!INCLUDE[d365fin](includes/d365fin_md.md)], open the card for the record you want to couple. For example, the Customer or Contact card.  
2.  Choose the **Synchronize Now** action.  
3.  If a record can be synchronized in one direction, select the option that specifies the direction of data update, and then choose **OK**.  

## To synchronize a single record from [!INCLUDE[crm_md](includes/crm_md.md)]  
1.  In [!INCLUDE[crm_md](includes/crm_md.md)], open the form for the record you want to couple. For example, the Account card or Contact card form.  
2.  Choose the **[!INCLUDE[d365fin](includes/d365fin_md.md)]** action in the ribbon to open and couple record automatically.

> [!Note]
> You can synchronize a single record from [!INCLUDE[crm_md](includes/crm_md.md)] automatically only when **Sync. Only Coupled Records** is disabled and the synchronization direction is set to Bidirectional or From Integration Table on the **Integration Table Mapping** page for the record. For more information, see [Mapping the Tables and Fields to Synchronize](admin-how-to-modify-table-mappings-for-synchronization.md#creating-new-records).     

## To synchronize multiple records  
1.  In [!INCLUDE[d365fin](includes/d365fin_md.md)], open the list page for the record, such as the Customers or Contacts list pages.  
2.  Select the records that you want to synchronize, and then choose the **Synchronize Now** action.  
3.  If records can be synchronized in one direction, select the option that specifies the direction, and then choose **OK**.  

## See Also  
[Using Dynamics 365 Sales from Business Central](marketing-integrate-dynamicscrm.md)
