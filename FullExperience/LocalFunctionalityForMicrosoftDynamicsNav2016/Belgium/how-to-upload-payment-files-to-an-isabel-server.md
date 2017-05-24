---
title: "How to: Upload Payment Files to an Isabel Server"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "payment files, uploading"
ms.assetid: 1c5fd4d9-166c-4659-b7f0-5c93dc3c2d93
caps.latest.revision: 3
ms.author: "edupont"
translation.priority.ht: 
  - "fr-be"
  - "nl-be"
---
# How to: Upload Payment Files to an Isabel Server
Payment files can be uploaded using the **\($ N\_2000010 IBS Logs $\)** window. The **\($ T\_11306\_24 Upload Integration Mode $\)** and **\($ T\_11306\_26 Download Integration Mode $\)** fields in the **\($ T\_11306 Electronic Banking Setup $\)** window must be set to **Attended** to upload payment files.  
  
> [!NOTE]  
>  Before you can upload payment files you must be logged on to the Isabel server.  
  
### To upload payment files in attended mode  
  
1.  In the **Search** box, enter **IBS Logs**, and then choose the related link.  
  
2.  On the **Home** tab, in the **Process** group, choose **Get Contract and User**.  
  
3.  After verifying the payment files, a user ID and contract ID will be displayed in the **\($ T\_2000010\_40 IBS User ID $\)** and **\($ T\_2000010\_41 IBS Contract ID $\)** fields.  
  
     The **\($ T\_2000010\_42 Upload Status $\)** field will be set to **Ready for Upload**. If more than one contract exists on the Isabel server for the bank account, the **\($ T\_2000010\_42 Upload Status $\)** will be set to **Conflict Exists**. Select the correct contract.  
  
4.  On the **Home** tab, in the **Process** group, choose **Perform Download**. The payment files will be uploaded to the Isabel server and the **\($ T\_2000010\_21 Process Status $\)** field will be set to **Processed**.  
  
5.  Continue processing the payment files by signing and sending the files on the Isabel server.  
  
## See Also  
 [\($ N\_11308 Electronic Banking Setup $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/-$-n_11308-electronic-banking-setup-$-.md)   
 [\($ N\_2000010 IBS Logs $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/-$-n_2000010-ibs-logs-$-.md)   
 [How to: Archive IBS Log Entries](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-archive-ibs-log-entries.md)