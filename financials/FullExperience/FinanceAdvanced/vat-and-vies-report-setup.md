---
title: "VAT and VIES Report Setup"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "VAT, setting up reporting"
  - "VAT reports, about"
ms.assetid: 14dbaba9-1bfd-4f9c-ae05-fe65ec3e832b
caps.latest.revision: 7
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
# VAT and VIES Report Setup
Depending on the requirements of your country\/region, you must submit periodic VAT reports. In [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)], you can define statutory reports such as periodic VAT reports and VIES declarations.  
  
## VAT and VIES Reports  
 In addition to the periodic VAT statements that you submit to settle VAT, the tax authorities can require that you submit periodic reports of transactions that include VAT. If you are a resident of a country\/region in the EU, you must also submit a VIES declaration for trade with other EU countries\/regions. In most cases, the required report must have general information about the company name and the reporting period, and it must have lines or groups of lines that describe the VAT\-related transactions. In [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)], in the **VAT Report** window, you can define these reports much like you create documents such as orders, invoices, and credit memos. You can fill in the lines based on VAT entries, and then export the VAT report to the appropriate authorities. Depending on your country\/region and the type of VAT report that you have set up, the report can be exported in different formats.  
  
 For detailed information about how [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] supports VAT reports in your country\/region, search the [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] Help collection.  
  
### VAT and VIES Report Configuration  
 Before you can create VAT reports, you must specify a number series that will be used for VAT reports and you must specify if your company can make corrective VAT reports. For more information, see [How to: Set Up VAT Reports\-duplicate](../Finance/how-to-set-up-vat-reports-duplicate.md).  
  
 You must also set up general information about how the VAT reports will be created. As part of this, you must specify which processes must be used to print or export the reports. This configuration is performed in preconfigured codeunits. For more information, see [How to: Configure VAT Reports](../Finance/how-to-configure-vat-reports.md).  
  
> [!IMPORTANT]  
>  You must be familiar with C\/AL development in order to configure how VAT reports are printed or exported.  
  
## See Also  
 [How to: Configure VAT Reports](../Finance/how-to-configure-vat-reports.md)