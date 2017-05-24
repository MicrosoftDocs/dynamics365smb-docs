---
title: "EU Sales List in Germany"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: c42f1963-06e7-4432-b1f2-530fa1a1cd27
caps.latest.revision: 7
ms.author: "edupont"
manager: "tsiggaar"
translation.priority.ht: 
  - "de-de"
---
# EU Sales List in Germany
In Germany, the German EU sales list is submitted to the "Bundeszentralamt für Steuern" \(BZSt\) through the BZSt Online Portal by using the ELMA5 interface.  
  
 In order to increase security, all types of taxes and tax reports must be submitted under an authentication method. Beginning in January 1, 2013, it has become mandatory that you make submissions with authentication. To do so, you sign in with your BZSt number and private key using your pass phrase on the ELMA5 communications server. ELMA5 is designed to handle the transmission of large datasets of more than 1000 records. Following successful login, you can upload the data transfer in an interactive way. You can also set up the transfer to be automatic.  
  
## Implementation in [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]  
 [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] supports making submissions via the BZSt Online Portal in the ELMA5 format, which requires that a submission be signed with the sender's private key. After you have created a report, and verified all information, you can export the report from [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] and then submit it to the processing agency \(ZIVIT\).  
  
> [!IMPORTANT]  
>  The ability to submit a VAT report in an XML format is not supported. However, you can make a submission of fewer than 1000 records in a .csv file. For this, you can use the Elster Online portal, and use the VAT – VIES Declaration Disk batch job, report 88.  
  
## See Also  
 [BZSt Online Portal](http://www.bzst.de)   
 [\($ B\_88 VAT\- VIES Declaration Disk $\)](../Topic/\($%20B_88%20VAT-%20VIES%20Declaration%20Disk%20$\).md)   
 [How to: Create VAT Reports](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-create-vat-reports.md)