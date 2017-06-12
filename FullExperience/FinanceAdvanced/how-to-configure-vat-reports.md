---
title: "How to: Configure VAT Reports"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "VAT report, configuring"
ms.assetid: d87b58ae-7d22-4bc3-b3c5-096151806d39
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
# How to: Configure VAT Reports
Before you can create VAT reports, you must specify which processes must be used to print or export the reports.  
  
> [!IMPORTANT]  
>  In order to configure these processes, you must be familiar with C\/AL development and understand how codeunits work in [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]. If you are not familiar with codeunits, you must consult with your [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] certified partner.  
  
## VAT Report Configuration Codeunits  
 The VAT report configuration in [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] takes place in codeunits. At the center of the configuration is codeunit ID 740 that works as a mediator that can be called from different objects and pass data around without these objects knowing of each other.  
  
 In codeunit ID 740, you can specify which codeunits must run when users want to print or export a VAT report. By following a mediation design pattern, the **VAT Report** window calls codeunit ID 740, and [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] then reads how to print or export. You can add additional functions in this codeunit, but the following table describes the preconfigured functions. For each function, you can specify one or more codeunits or reports to handle actual process.  
  
|Function|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
|--------------|---------------------------------------|  
|**GetLines**|Specifies which process to run when a user wants to import VAT entries into the **VAT Report** window.|  
|**Export**|Specifies which process to run when a user wants to export a VAT report from the **VAT Report** window in order to submit it to the tax authorities.|  
|**Release**|Specifies which process to run when a user has printed or exported a VAT report so that it must be marked as released.|  
|**Reopen**|Specifies which process to run when a user wants to resubmit an existing VAT report in order to make a correction.|  
|**Print**|Specifies which process to run when a user wants to print a VAT report from the **VAT Report** window.<br /><br /> If you have multiple report formats, you can write a CASE statement to run the appropriate process depending on the user’s selection of menu item.|  
  
 [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] comes with default values for each function, but you can change these to suit your needs. For example, if your company wants to submit a VAT report that is printed in a specific format or on specific paper, for example, then you can edit the **Print** function in codeunit 740 to point to a report object that you create. This way, you will not have to edit the **VAT Report** window object to access your report because the menu item on the window always just calls codeunit 740 to run whatever the **Print** function specifies.  
  
 In the standard version of this codeunit, more functions exist to handle other pieces of functionality. For example, you can change the default implementation to print using a different report, or to accept other values for the [VAT Report Config. Code](assetId:///c0a1de7e-b69b-4b51-9a30-42c96d8cbfc6) field.  
  
#### To configure VAT reports  
  
1.  In the [!INCLUDE[nav_dev_long](../BusinessFunctionality/DataExchange/includes/nav_dev_long_md.md)], open **Object Designer**.  
  
2.  Open codeunit 740 in design mode.  
  
3.  Identify the function for the activity that you want to configure, such as the **Print** function, and make the appropriate changes.  
  
 When users create a VAT report, and they choose to print it, the report will print in the format that is defined by your report object, **My VAT Report**.  
  
### Preconfigured Codeunits  
 In your country\/region, [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] can have been modified to change the way VAT reports work. As with other functionality, you can modify relevant tables and reports and create new objects, and you can modify the preconfigured codeunits to include your modifications.  
  
 The following table describes the predefined codeunits in [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] that configure VAT reports.  
  
|ID|Name|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
|--------|----------|---------------------------------------|  
|740|**VAT Report Mediator**|Central codeunit for configuring activities that are related to VAT reports. Based on the mediation pattern, other objects will refer to this codeunit to trigger the code that carries out the activity.|  
|741|**VAT Report Release\/Reopen**|Handles the code for marking a VAT report as released or reopened.|  
|743|**VAT Report Export**|Handles the code for exporting a VAT report into a file format such as XML or plain text so that the file can be submitted to the tax authorities.|  
|744|**VAT Report Check**|Handles the code for testing if the current VAT report is set up correctly.<br /><br /> Users will not be able to submit VAT reports that fail the validation that is specified in this codeunit.|  
  
## See Also  
 [VAT and VIES Report Setup](../Finance/vat-and-vies-report-setup.md)