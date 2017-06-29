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
# How to: Configure VAT Reports
Before you can create VAT reports, you must specify which processes must be used to print or export the reports.  
  
> [!IMPORTANT]  
>  In order to configure these processes, you must be familiar with C\/AL development and understand how codeunits work in FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] --> --> --> --> --> --> -->. If you are not familiar with codeunits, you must consult with your [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] certified partner.  
  
## VAT Report Configuration Codeunits  
 The VAT report configuration in [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] takes place in codeunits. At the center of the configuration is codeunit ID 740 that works as a mediator that can be called from different objects and pass data around without these objects knowing of each other.  
  
 In codeunit ID 740, you can specify which codeunits must run when users want to print or export a VAT report. By following a mediation design pattern, the **VAT Report** window calls codeunit ID 740, and [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] then reads how to print or export. You can add additional functions in this codeunit, but the following table describes the preconfigured functions. For each function, you can specify one or more codeunits or reports to handle actual process.  
  
|Function|FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)] --> -->|  
|---
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

    --------|----------|---------------------------------------|  
|740|**VAT Report Mediator**|Central codeunit for configuring activities that are related to VAT reports. Based on the mediation pattern, other objects will refer to this codeunit to trigger the code that carries out the activity.|  
|741|**VAT Report Release\/Reopen**|Handles the code for marking a VAT report as released or reopened.|  
|743|**VAT Report Export**|Handles the code for exporting a VAT report into a file format such as XML or plain text so that the file can be submitted to the tax authorities.|  
|744|**VAT Report Check**|Handles the code for testing if the current VAT report is set up correctly.<br /><br /> Users will not be able to submit VAT reports that fail the validation that is specified in this codeunit.|  
  
## See Also  
 [VAT and VIES Report Setup](../Finance/vat-and-vies-report-setup.md)