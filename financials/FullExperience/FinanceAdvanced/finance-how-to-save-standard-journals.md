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
# How to: Save Standard Journals
When you have created journal lines which you know you are likely to create again later, you can save them as a standard journal before you post the journal.  
  
> [!NOTE]  
>  The following procedure refers to the item journal, but the information also applies to the general journal.  
  
### To save a standard journal  
  
1.  In the **Search** box, enter **Item Journal**, and then choose the related link.  
  
2.  Enter one or more journal lines.  
  
3.  Select the journal lines that you want to reuse.  
  
4.  On the **Actions** tab, in the **Functions** group, choose **Save as Standard Journal**.  
  
     In the **Save as Standard Item Journal** request window you must define a new or existing standard item journal that the lines should be saved in:  
  
    1.  In the **Code** field, enter a code to identify the standard item journal that you are about to save.  
  
         If you have already created one or more standard item journals and you want to replace one of these with the new set of item journal lines, in the **Code** field, select the code you want.  
  
    2.  Choose the **OK** button to verify that you want to overwrite the existing standard item journal and replace all its content.  
  
5.  In the **Description** field, enter a text that indicates the purpose of the standard item journal.  
  
6.  Select the **Save Unit Amount** field if you want to save the values in the **Unit Amount** field of the standard item journal.  
  
7.  Select the **Save Quantity** field if you want the program to save the values in the **Quantity** field.  
  
8.  Choose the **OK** button to save the standard item journal.  
  
 When you have finished saving the standard item journal, the **Item Journal** window is displayed so you can proceed to post it, knowing that it can easily be recreated next time you need to post the same or similar lines.  
  
## See Also  
 [How to: Reuse Standard Journals](../how-to-reuse-standard-journals.md)