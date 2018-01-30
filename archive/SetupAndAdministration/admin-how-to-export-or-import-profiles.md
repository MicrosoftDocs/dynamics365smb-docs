---
    title: How to Export or Import Profiles | Microsoft Docs
    description: You can export a profile, for example to reuse UI configurations in other [!INCLUDE[d365fin](includes/d365fin_md.md)] databases.
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
# Export or Import Profiles
You can export a profile, for example to reuse UI configurations in other [!INCLUDE[d365fin](includes/d365fin_md.md)] databases.  
  
 You can quickly implement UI configurations for a profile by importing an XML file that holds the configured profile.  
  
> [!NOTE]  
>  You cannot import a profile that already exists in the database, even though the XML file is named differently or has different content. You must delete the existing profile before you can import the new profile.  
  
### To export a profile  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Export Profiles**, and then choose the related link.  
  
2.  In the **Export Profiles** window, on the **Profile** FastTab, set a filter for the profile ID that you want to export, and then choose **OK**.  
  
3.  Name and save the XML file for the profile.  
  
### To import a profile  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Import Profiles**, and then choose the related link.  
  
2.  In the **Import from XML File** window, select the profile that you want to import.  
  
     If you are importing a profile that already exists in the database, then you must first delete that profile. For more information, see [Manage Profiles](../manage-profiles.md).  
  
3.  Choose the **OK** button to import the new profile.  
  
## See Also  
 [Administration in the Clients](../administration-in-the-clients.md)   
 [Configure the User Interface](../configure-the-user-interface.md)