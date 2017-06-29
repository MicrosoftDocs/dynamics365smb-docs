---
title: "Digipoort Overview"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "Digipoort, overview"
  - "electronic declarations, about"
ms.assetid: 80bb0a1c-0d13-491d-8546-2f854993ad00
caps.latest.revision: 4
ms.author: "edupont"
translation.priority.ht: 
  - "nl-nl"
---
# Digipoort Overview
In the Netherlands, you use Digipoort to make periodic electronic filings for VAT declarations and ICP reports in EU sales list submissions. Digipoort is the electronic post office provided by the Dutch government for companies. It provides the common infrastructure for the communication of information between companies and the government, including VAT declarations. The reports are in XBRL format.  
  
 FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] --> --> --> --> provides a .dll component to provide the communication between [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] and the Digipoort server. Typically, the [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] installer installs the .dll to the following location: c:\\Program Files \(x86\)\\Microsoft Dynamics NAV\\\<version\>\\RoleTailored Client\\Add\-ins\\Microsoft.Dynamics.NL.Digipoortservice.dll.  
  
 The Digipoort channel replaces the BAPI method for making submissions.  
  
## Certificate Storage  
 In order to communicate electronically using Digipoort with the Dutch government, you will need two certificates \(PKIoverheid\). You will need a private certificate for the company as well as a public certificate from the website of the Dutch tax authorities. need a private certificate for the company as well as a public certificate from the Dutch authorities. You can get more specific information from the website of the Dutch tax authority. For more information, see the Dutch Tax Administration website[Logius](https://aansluiten.procesinfrastructuur.nl/site/en/).  
  
 You will have to import the certificates that you receive into the Windows Certificate store. This is a change from prior releases, in which you stored your certificates in [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)].  
  
 For more information, see [How to: Set Up Certificates for use with Digipoort](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/how-to-set-up-certificates-for-use-with-digipoort.md).  
  
## See Also  
 [How to: Set Up Certificates for use with Digipoort](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/how-to-set-up-certificates-for-use-with-digipoort.md)