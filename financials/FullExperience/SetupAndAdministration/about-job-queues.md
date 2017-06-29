---
title: "About Data Tables"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "RapidStart Services, data tables"
ms.assetid: b6f5f427-931e-404f-a8b8-2cddabd7c795
caps.latest.revision: 5
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
# About Data Tables
ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> data tables come in two basic types: Master and Setup. When you are setting up a company configuration, you can use these types to focus your configuration strategy.  
  
## Master Data Tables  
 The following table lists a some example ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> master data tables. When you initialize a new company, these tables are empty.  
  
### Master Data Tables  
  
|**Table No.**|**Table Name**|  
|-------------------|--------------------|  
|15|G\/L Account|  
|18|Customer|  
|23|Vendor|  
|27|Item|  
|5050|Contact|  
  
## Setup Data Tables  
 The following table provides examples of the setup data tables, in which you capture setup information in the configuration questionnaire. These tables contain baseline information when the company is created.  
  
|**Table No.**|**Table Name**|  
|-------------------|--------------------|  
|98|General Ledger Setup|  
|311|Sales & Receivables Setup|  
|312|Purchases & Payables Setup|  
|313|Inventory Setup|  
  
 In addition to setup data tables, ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> also has data tables that specify core information about the company and its business processes. The following table provides some examples.  
  
###  
  
|**Table No.**|**Table Name**|  
|-------------------|--------------------|  
|3|Payment Terms|  
|4|Currency|  
|6|Customer Price Groups|  
|5700|Stockkeeping Unit|  
  
## See Also  
 [How to: Manage Company Configuration in a Worksheet](../SetupAndAdministration/how-to-manage-company-configuration-in-a-worksheet.md)   
 [How to: Customize a Package or Worksheet](../SetupAndAdministration/how-to-customize-a-package-or-worksheet.md)