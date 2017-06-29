---
title: "How to: Copy Versions of Production BOMs"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "production BOMs, copying"
ms.assetid: 5678881f-70ff-47d9-be17-3a138be6e68e
caps.latest.revision: 7
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
---
# How to: Copy Versions of Production BOMs
When working with long production BOMs or slight changes in the versions, it is useful to copy an existing version of a production BOM into a new version or into an existing version. Already existing information on the lines is overwritten in the destination version.  
  
 There are two ways you can copy Production BOM Versions:  
  
-   Use the **Copy BOM Version** function.  
  
-   Use the **Copy BOM Header** function.  
  
 When you use the **Copy BOM Version** function, you get a list of versions to select from.  
  
 When you use the **Copy BOM Header** function, the lines are copied from the first version.  
  
### To copy production BOM versions by using Copy BOM Version function  
  
1.  In the **Search** box, enter **Production BOM**, and then choose the related link.  
  
2.  On the **Navigate** tab, in the **Prod. BOM** group, choose **Versions**.  
  
3.  If you want to create a new version, follow the procedure for how to create new versions. Remember to fill in the new version number before you copy. If you want to copy to an existing version, check whether this version is to be overwritten and make sure the **Status** field is not set to **Certified**.  
  
4.  On the **Actions** tab, in the **Functions** group, choose **Copy BOM Version**.  
  
     In the **Prod. BOM Version List** window, select a version, and choose the **OK** button.  
  
     The lines of the selected BOM are copied into the current version, where you can further edit them.  
  
5.  Change the **Status** field to **Certified**.  
  
### To copy production BOM versions by using the Copy BOM Header function  
  
1.  In the **Search** box, enter **Production BOM**, and then choose the related link.  
  
2.  On the **Navigate** tab, in the **Prod. BOM** group, choose **Versions**.  
  
3.  If you want to create a new version, follow the procedure for how to create new versions. Remember to fill in the new version number before you copy. If you want to copy to an existing version, check whether this version is to be overwritten and make sure the **Status** field is not set to **Certified**.  
  
4.  On the **Actions** tab, in the **Functions** group, choose **Copy BOM Header**, and then choose the **Yes** button.  
  
     The lines of the first BOM version are copied into the current version, where you can further edit them.  
  
5.  Change the **Status** field to **Certified**.  
  
## See Also  
 [How to: Create Production BOMs](../DesignAndEngineering/how-to-create-production-boms.md)   
 [How to: Create New Versions of Production BOMs](../DesignAndEngineering/how-to-create-new-versions-of-production-boms.md)