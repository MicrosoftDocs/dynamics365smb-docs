---
title: "How to: Create Inventory Put-aways"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "inventory management, creating put-aways"
  - "putting away, creating put-aways"
  - "inventory put-aways, creating"
  - "put-aways, creating"
ms.assetid: cbfc33b4-06d5-4371-a689-070adc98905f
caps.latest.revision: 11
ms.author: "sgroespe"
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
# How to: Create Inventory Put-aways
When your location is set up to require put\-away processing but not receive processing, you will use the **Inventory Put\-away** document to organize and record your put\-away activity.  
  
 You have three options for creating an inventory put\-away:  
  
-   Create the put\-away in two steps by first creating a warehouse request from the source document, which acts as a signal to the warehouse that the source document is ready for put\-away. The inventory put\-away can then be created from the **Inventory Put\-away** window based on the source document.  
  
-   Create the inventory put\-away directly from the source document itself.  
  
-   You can create inventory put\-aways for several source documents at once by using the batch job.  
  
 Each of these three methods is described below.  
  
### To request an inventory put\-away by releasing the source document  
  
1.  In the case of purchase orders, sales return orders, and inbound transfer orders, you create the warehouse request by releasing the order.  
  
2.  In the **Search** box, enter the order document type, such as **Purchase Orders**, and choose the related link. Open the order you want to release.  
  
3.  On the **Actions** tab, in the **Release** group, choose **Release**.  
  
4.  In the case of production orders, you create the warehouse request by creating an inbound request from the released production order.  
  
    1.  In the **Search** box, enter **Production Orders**, and then select the related link.  
  
    2.  On the **Actions** tab, in the **Warehouse** group, choose **Create Inbound Whse. Request**.  
  
> [!NOTE]  
>  You can also create the inbound warehouse request by selecting the **Create Inbound Request** check box when you refresh the production order. For more information, see [How to: Refresh Production Orders](../OperationsPlanning/how-to-refresh-production-orders.md).  
  
 When the warehouse request is created, someone working in the warehouse creating put\-aways can see that the source document is ready and can create an inventory put\-away document.  
  
### To create an inventory put\-away based on the source document  
  
1.  In the **Search** box, enter **Inventory Put\-away**, and then select the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**.  
  
3.  In the **Source Document** field, select the type of source document you are putting away from.  
  
4.  In the **Source No.** field, select the source document.  
  
5.  Alternatively, on the **Actions** tab, in the **Functions** group, choose **Get Source Document** to select the document from a list of inbound source documents that are ready for put\-away at the location.  
  
6.  Choose the **OK** button to fill the put\-away lines according to the selected source document.  
  
### To create an inventory put\-away from the source document  
  
1.  In the source document, which can be a purchase order, sales return order, inbound transfer order, or production order, on the **Actions** tab, in the **Warehouse** group, choose the **Create Inventory Put\-away\/Pick** button.  
  
2.  On the **Options** FastTab, select the **Create Invt. Put\-away** field. To print a put\-away list, select the **Print Document** field.  
  
3.  Choose the **OK** button. A new inventory put\-away is created, and if the **Print Document** option was selected, the put\-away list will be printed.  
  
### To create several inventory put\-aways with the batch job  
  
1.  In the **Search** box, enter **\($ R\_7323 Create Invt. Put\-away \/ Pick $\)**, and then choose the related link.  
  
2.  On the **Warehouse Request** FastTab of the request window, use the **Source Document** and **Source No.** fields to filter on certain types of documents or ranges of document numbers.  
  
3.  On the **Options** FastTab, select the **Create Invt. Put\-away** field. If you would like to print a put\-away list, select the **Print Document** field.  
  
4.  Choose the **OK** button. The inventory put\-aways will be created, and if you selected the **Print Document** field, the put\-away list will be printed.  
  
## See Also  
 [\($ N\_7375 Inventory Put\-away $\)](../Topic/\($%20N_7375%20Inventory%20Put-away%20$\).md)   
 [Put Items Away](../WarehouseActivities/put-items-away.md)   
 [How to: Put Items Away with Inventory Put\-aways](../DesignAndEngineering/how-to-put-items-away-with-inventory-put-aways.md)