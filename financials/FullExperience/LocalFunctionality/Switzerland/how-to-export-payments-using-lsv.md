---
title: "How to: Export Payments Using LSV"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "LSV payments, exporting"
ms.assetid: 3fbf75e9-3169-4204-a64b-6fc317ec57f5
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "de-ch"
  - "fr-ch"
---
# How to: Export Payments Using LSV
You can export or write Lastschrift Verfahren \(LSV\+\) files that contain payments information after closing the LSV collection. You can send the generated files to the bank on a disk, or use an electronic file transfer such as your online banking software or an Internet portal.  
  
### To export payments using LSV  
  
1.  In the **Search** box, enter **LSV Journal List**, and then choose the related link.  
  
2.  In the **LSV Journal List** window, select the required LSV journal.  
  
3.  On the **Actions** tab, in the **Functions** group, select **Write LSV File**.  
  
4.  In the **Write LSV File** window, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ B\_3010834\_F\_1\_5 No. $\)**|Specify the LSV journal number that you want to export.|  
    |**\($ B\_3010834\_F\_1\_3 Test $\)**|Specify if you are sending test deliveries to your bank. The bank does not process test files.|  
  
5.  All related lines are transferred to the LSV journal. The LSV file is generated in the predetermined folder.  
  
## See Also  
 [Swiss Electronic Payments Using LSV\+](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/swiss-electronic-payments-using-lsv-.md)   
 [How to: Process an LSV Collection](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-process-an-lsv-collection.md)   
 [How to: Close an LSV Collection](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-close-an-lsv-collection.md)   
 [How to: Post LSV\+ Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-post-lsv-payments.md)   
 LSV Journal   
 LSV Journal Line   
 LSV Setup