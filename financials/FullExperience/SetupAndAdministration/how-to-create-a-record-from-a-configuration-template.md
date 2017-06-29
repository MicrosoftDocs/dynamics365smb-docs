---
title: "How to: Create a Record from a  Configuration Template"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "master data, using"
  - "RapidStart Services, creating records"
  - "data migration, creating records"
ms.assetid: a83f5664-f6e7-4956-81ba-b1bd1223474f
caps.latest.revision: 12
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
# How to: Create a Record from a  Configuration Template
You can use the structure of data that is contained in the data templates to convert your information into records in the database, one\-by\-one. To do so, you use the **Create Instance** function. This is a miniature version of the data migration process and can be useful for prototyping or treating smaller data creation tasks.  
  
 The following steps illustrate how to create an item card from an item data template. You can create a record from any data template using the same procedure.  
  
### To create a record from a configuration template  
  
1.  In the **Search** box, enter **Configuration Templates**, and then choose the related link.  
  
2.  In the **\($ N\_8620 Setup Master Templates $\)** window, select the item template that you have created and choose **Edit**. For more information on how to create a template, see [How to: Create a Configuration Template](../SetupAndAdministration/how-to-create-a-configuration-template.md).  
  
3.  On the **Actions** tab, choose **Create Instance**. An item card is created.  
  
4.  Choose the **OK** button.  
  
5.  To review the new item card, in the **Search** box, enter **Items**, and then choose the related link.  
  
6.  Open the new item card.  
  
7.  Expand various FastTabs, and verify that the information was created correctly on them.  
  
 After you have created and verified the structure of the configuration templates, you can continue with the actual migration of your customer’s data into the new [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] database.  
  
## See Also  
 [How to: Use a Configuration Template on a Record](../SetupAndAdministration/how-to-use-a-configuration-template-on-a-record.md)