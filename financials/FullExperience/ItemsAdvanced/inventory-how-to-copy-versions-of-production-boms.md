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
 [How to: Create Production BOMs](../how-to-create-production-boms.md)   
 [How to: Create New Versions of Production BOMs](../how-to-create-new-versions-of-production-boms.md)