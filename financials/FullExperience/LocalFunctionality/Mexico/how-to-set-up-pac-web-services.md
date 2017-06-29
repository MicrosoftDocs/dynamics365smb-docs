---
title: "How to: Set Up PAC Web Services"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "electronic invoices, setting up PAC"
ms.assetid: 6a3a8cdd-52cb-4539-9e78-b0dae3376558
caps.latest.revision: 8
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "es-mx"
---
# How to: Set Up PAC Web Services
Before you can send invoices and credit memos electronically, you must specify one or more providers of the electronic stamp that must be included in invoices in Mexico.  
  
 When you send an electronic document, it must receive a digital stamp by an authorized service provider, PAC, before it can be sent to your customer. The communication between FIX INCLUDE HERE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] --> and the PAC is managed through web services, and therefore, you must specify technical information about the web services of the PAC that you intend to use.  
  
 To use web services, you must identify the name of the method on the web service that processes requests for digital stamps. Your PAC can give you this information.  
  
 If your PAC offers the service of canceling signed documents, you must specify two web methods: one web method for requesting the digital stamp, and the other for canceling an already signed document.  
  
### To set up a PAC web service  
  
1.  In the **Search** box, enter **PAC Web Services**, and then choose the related link.  
  
2.  Fill in the fields as described in the following table.  
  
    |FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] --> -->|FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] --> -->|  
    |---------------------------------|---------------------------------------|  
    |**Code**|Specify a unique ID for the authorized service provider, PAC, such as **PAC1**.|  
    |**Name**|Specify the name of the PAC.|  
  
3.  On the **Navigate** tab, choose **Details**.  
  
4.  Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Environment**|Specify if the web service is for a test environment or a production environment.|  
    |**Type**|Specify if the web method is for requesting a digital stamp or for canceling.|  
    |**Method Name**|Specify the name of the web method, such as **GeneraTimbre** or **CancelaTimbre**.|  
    |**Address**|Specify the URL of the web method.|  
  
     Contact your PAC for this information.  
  
5.  Repeat the steps for any additional PAC that you want to set up.  
  
    > [!IMPORTANT]  
    >  SAT has certified more than one PAC in Mexico, and you must obtain the appropriate information for communication with the PAC of your choice.  
  
## See Also  
 [Electronic Invoicing](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Mexico/electronic-invoicing.md)   
 [How to: Set Up Electronic Invoicing](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Mexico/how-to-set-up-electronic-invoicing.md)