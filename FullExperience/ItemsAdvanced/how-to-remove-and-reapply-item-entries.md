---
title: "How to: Remove and Reapply Item Entries"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "item applications, reapplying"
  - "item applications, removing"
ms.assetid: 92d2812d-544f-4518-8c77-10efef7b4e0f
caps.latest.revision: 8
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Remove and Reapply Item Entries
You can view and manually change certain item application entries that are created automatically during inventory transactions.  
  
> [!NOTE]  
>  Certain limitations and consequences apply to this kind of work. For more information, see [Application Worksheet](../Topic/\($%20N_521%20Application%20Worksheet%20$\).md).  
  
### To remove an item application by using the Application Worksheet  
  
1.  In the **Search** box, enter **Application Worksheet**, and then choose the related link.  
  
2.  The **Application Worksheet** window opens displaying existing item ledger entries for all items.  
  
3.  Enter filters on the **General** FastTab to make it easier to find the item ledger entry for which you want to change the application.  
  
4.  Select the item ledger entry. On the **Navigate** tab, in the **View** group, choose **Applied Entries**. The **View Applied Entries – Applied Entries** window opens to show the item ledger entry or entries that are currently applied to the selected entry.  
  
5.  Select the item ledger entry for which you want to remove the application.  
  
6.  On the **Actions** tab, in the **General** group, choose **Remove Application**. This removes the item application entry that links the two item ledger entries and moves it to the **View Applied Entries – Unapplied Entries** window.  
  
7.  Close the **View Applied Entries – Applied Entries** window.  
  
 The **Remaining Quantity** field of the two item ledger entries are increased by the quantity that has been unapplied. The removed item ledger entry is now available for reapplication in the **View Applied Entries – Unapplied Entries** window.  
  
> [!IMPORTANT]  
>  You should not leave application entries unapplied for longer periods of time because other users cannot process the affected items until you reapply the application entries or close the **Application Worksheet** window. The following error message is displayed if you try to perform actions that involve a manually unapplied application entry:  
>   
>  **You cannot perform this action because entries for item \<item\> are unapplied in the Application Worksheet by user \<user\>.**  
  
### To reapply an item application by using the Application Worksheet  
  
1.  In the **Search** box, enter **Application Worksheet**, and then choose the related link.  
  
2.  The **Application Worksheet** window opens displaying existing item ledger entries for all items.  
  
3.  To reapply entries that were removed since the worksheet was opened, select the item ledger entry that you want to reapply. On the **Actions** tab, in the **Functions** group, choose **Reapply**.  
  
    > [!NOTE]  
    >  This reapplication to the original balance also occurs automatically when you close the **Application Worksheet** window.  
  
4.  To apply an available open item ledger entry to another entry, select the item ledger entry that you want to apply. On the **Navigate** tab, in the **View** group, choose **Unapplied Entries**. The **View Applied Entries – Unapplied Entries** window opens.  
  
5.  Select one or more item ledger entries that you want to apply to the entry selected in the **Application Worksheet** window, and then choose the **OK** button.  
  
     An item application entry is created between the two item ledger entries. The **Remaining Quantity** fields of the two entries are reduced by the applied quantity.  
  
    > [!NOTE]  
    >  If you have chosen to make an application that would create an infinite loop in the cost adjustment process, then the application that you proposed is not made. This can occur when the original entries created negative stock. The application is not made. Therefore, you must select a different entry for the application.  
  
6.  If the **Automatic Cost Adjustment** field in the **Inventory Setup** is set to **Always**, then the cost adjustment batch job is automatically run after you make a reapplication. Otherwise, run the **Adjust Cost \- Item Entries** batch job to make sure that all costs are up to date.  
  
## See Also  
 [Application Worksheet](../Topic/\($%20N_521%20Application%20Worksheet%20$\).md)   
 [Design Details: Item Application](../ApplicationDesign/design-details-item-application.md)   
 [Automatic Cost Adjustment](../Topic/\($%20T_313_30%20Automatic%20Cost%20Adjustment%20$\).md)   
 [Item Application Entry](../Topic/\($%20T_339%20Item%20Application%20Entry%20$\).md)   
 [Item Application Entry History](../Topic/\($%20T_343%20Item%20Application%20Entry%20History%20$\).md)   
 [Automatic Cost Adjustment](../Topic/\($%20T_313_30%20Automatic%20Cost%20Adjustment%20$\).md)   
 [Adjust Cost \- Item Entries](../Finance/-$-b_795-adjust-cost-item-entries-$-.md)