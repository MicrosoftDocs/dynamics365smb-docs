---
    title: How to Import Post Code Updates
    description: Every month a post code file will be delivered with all post code mutations in a month. This post code file can be imported and update the relevant data of the Post Code Range table.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Import Post Code Updates
Every month a post code file will be delivered with all post code mutations in a month. This post code file can be imported and update the relevant data of the **Post Code Range** table.  

## To import the update file  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Post Codes Updates**, and then choose the related link.  
2.  On the **Post Codes Updates** page, choose the **Import Post Codes Update** action.  
3.  Specify the path and name of the post code update file, and then choose the **OK** button. If you do not want to import the file, choose the **Cancel** button to close the page.  

If there is no file imported with a full set of post code data, then a message appears.  

Before updating the post codes the following checks will be performed:  

- Is there already an update file imported with a Date Field later then the date of this new update file? If so then the process will stop.  

- Is there a gap between the date of this file and the value in the Date Field field for the last imported file? If there is a gap then a message appears. You can choose if you still want to import the update file.  

Information about the imported post code will be saved in the Post Code Update Log Entry Table table.  

## See Also  
[Dutch Post Codes](dutch-post-codes.md)
