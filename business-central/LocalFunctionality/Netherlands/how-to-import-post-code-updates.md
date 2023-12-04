---
    title: How to import post code updates [NL]
    description: The post code file can be imported and update the relevant data of the Post Code Range table.
    author: brentholtorf
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 11/23/2023
    ms.author: bholtorf
---
# Import post code updates in the Dutch version
Every month a post code file is delivered with all post code mutations in a month. This post code file can be imported and update the relevant data of the **Post Code Range** table.  

## To import the update file  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Post Codes Updates**, and then choose the related link.  
2.  On the **Post Codes Updates** page, choose the **Import Post Codes Update** action.  
3.  Specify the path and name of the post code update file, and then choose the **OK** button. If you don't want to import the file, choose the **Cancel** button to close the page.  

If there's no file imported with a full set of post code data, then a message appears.  

Before you update the post codes, the following checks are performed:  

- Is there already an update file imported with a Date Field later than the date of this new update file? If so then the process stops.  

- Is there a gap between the date of this file and the value in the Date Field field for the last imported file? If there's a gap, then a message appears. You can choose if you still want to import the update file.  

Information about the imported post code is saved in the Post Code Update Log Entry Table table.  

## See also  
[Dutch Post Codes](dutch-post-codes.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]