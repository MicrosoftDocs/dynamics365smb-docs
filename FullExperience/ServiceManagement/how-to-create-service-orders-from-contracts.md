---
title: "How to: Create Service Orders from Contracts"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "service orders, creating"
  - "service contracts, creating service orders"
  - "contracts (service), creating service orders"
ms.assetid: 8e288a3e-8d43-439f-a40c-7b54dd26fdd5
caps.latest.revision: 6
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
# How to: Create Service Orders from Contracts
You can automatically create service orders for the maintenance of service items based on service contracts.  
  
### To create a service order from a contract  
  
1.  In the **Search** box, enter **Create Contract Service Orders**, and then choose the related link.  
  
2.  On the **Service Contract Header** FastTab, set the filters you want to apply.  
  
3.  On the **Options** FastTab, fill in the **Starting Date** and **Ending Date** fields with the starting date and ending date for the period that you want to create contract service orders for. The batch job creates service orders that include service items in service contracts with next planned service dates within this period.  
  
    > [!NOTE]  
    >  There is a limit to the number of days you can use as the date range each time you use this batch job. You set this limit in the **Contract Serv. Ord. Max. Days** field in the **Service Mgt. Setup** window.  
  
4.  In the **Action** field, choose **Create Service Order**.  
  
5.  Choose the **OK** button to create the service orders.  
  
## See Also  
 [How to: Create Service Orders](../Service/how-to-create-service-orders.md)   
 [How to: Create Service Contracts and Service Contract Quotes](../Service/how-to-create-service-contracts-and-service-contract-quotes.md)