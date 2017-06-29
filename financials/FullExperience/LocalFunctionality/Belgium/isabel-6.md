---
title: "Isabel 6"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 282e91b1-7fe8-49cc-98d4-98ab9444318c
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "fr-be"
  - "nl-be"
---
# Isabel 6
The Isabel organization has developed a Client Isabel Synchronizer \(CIS\) platform that allows ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> to securely integrate with Isabel. CIS handles document exchange to and from the Isabel server.  
  
 To upload or download the bank files, you will have to set up your environment to work with Isabel. ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> communicates to the CIS.dll through a COM wrapper.  
  
 To set up your system to work with Isabel, complete the following:  
  
-   Install the Isabel security components. For more information, see the download area on the [Isabel website](http://go.microsoft.com/fwlink/?LinkId=210323).  
  
-   Install the COM wrapper that is manufactured by the Isabel organization. This wrapper is included with the Isabel GO 6.20 package.  
  
-   Register the COM wrapper on your computer. At the command prompt, locate the CIS.dll and then execute the **regsvr32 CISComWrapper.dll** command.  
  
## See Also  
 [Isabel website](http://go.microsoft.com/fwlink/?LinkId=210323)   
 [Belgian Electronic Banking](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/belgian-electronic-banking.md)   
 [How to: Set Up Electronic Banking](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-electronic-banking.md)