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
# How to: Copy Routing Versions
You can copy the created routing versions. This is useful for long routings or when slight changes are to be made to versions. You can copy an existing version of a routing into a new version or into an existing version. Already existing information on the lines is overwritten in the destination version.  
  
### To copy routing versions  
  
1.  In the **Search** box, enter **Routings**, and then choose the related link.  
  
2.  On the **Navigate** tab, in the **Routing** group, choose **Versions**.  
  
3.  If you want to create a new version, fill in the version number of the new version.  
  
     To use an existing version, select the version you want to copy to. Check whether this version is to be overwritten and make sure the status is not set to **Certified**. It is not possible to change versions with the status **Certified**.  
  
4.  To copy the standard routing, from the **Routing Version** window, On the **Actions** tab, in the **Functions** group, choose **Copy Routing Header**, and then choose the **Yes** button.  
  
     To select a routing version, On the **Actions** tab, in the **Function** group, choose **Copy Routing Version**. Select the version you want to copy from and choose the **OK** button.  
  
     The routing lines of the source version are copied into the current version and can be further processed from there.  
  
5.  Change the **Status** field to **Certified**.  
  
## See Also  
 [How to: Create Routings](../DesignAndEngineering/how-to-create-routings.md)   
 [How to: Create New Versions of Routings](../DesignAndEngineering/how-to-create-new-versions-of-routings.md)