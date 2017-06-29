---
title: "How to: Use a Configuration Template on a Record"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "data migration, using a data template"
  - "master data, using"
  - "RapidStart Services, migrating data"
ms.assetid: e5f930a4-cd14-4df8-b0b2-b4b1728c0ee4
caps.latest.revision: 13
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
# How to: Use a Configuration Template on a Record
You can apply a data template to any record that is in FIX INCLUDE HERE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] --> and use this technique to change or modify a record. However, when you do this, you overwrite existing values in the record with those of the template. Consequently, you should be careful when you apply a template to existing records.  
  
### To use a configuration template on a record  
  
1.  Create a new contact, customer, item, or vendor record. For example, to create a new customer record, in the **Search** box, enter **Customers**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**. The **New \- Customer Card** window opens.  
  
3.  Enter a customer number and enter a customer name. In the **Process** group, choose **Apply Template**.  
  
4.  Select a customer template that you have created from the list in the **Data Template List** window. Choose the **OK** button.  
  
 The default values from the chosen customer template are copied to the customer card.  
  
## See Also  
 [Migrate Customer Data](../SetupAndAdministration/migrate-customer-data.md)