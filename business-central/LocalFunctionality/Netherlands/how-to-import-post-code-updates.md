---
title: How to import post code updates [NL]
description: Import the post code file to update the relevant data in the Post Code Range table.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: import post code file, post code file, Dutch version, Netherlands, post code range table, post code import, post code update
ms.date: 03/18/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Import post code updates in the Dutch version

Every month, a post code file is delivered with all post code mutations for that month. This post code file can be imported to update the relevant data of the **Post Code Range** table.  

## Import the update file  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Post Codes Updates**, and then choose the related link.  
1. On the **Post Codes Updates** page, choose the **Import Post Codes Update** action.  
1. Specify the path and name of the post code update file, and then choose the **OK** button. If you don't want to import the file, choose the **Cancel** button to close the page.  

If there's no file imported with a full set of post code data, then a message appears.  

Before you update the post codes, the following checks are performed:  

- Is there already an update file imported with a **Date Field** later than the date of this new update file? If so then the process stops.  

- Is there a gap between the date of this file and the value in the **Date Field** for the last imported file? If there's a gap, then a message appears. You can choose if you still want to import the update file.  

Information about the imported post code is saved in the **Post Code Update Log Entry Table**.  

## Related information

[Dutch Post Codes](dutch-post-codes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
