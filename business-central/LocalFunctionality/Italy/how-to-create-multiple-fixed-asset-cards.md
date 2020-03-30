---
    title: How to Create Multiple Fixed Asset Cards
    description: You can create multiple fixed asset cards automatically during purchase invoice posting.

    services: project-madeira 
    documentationcenter: ''
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
# Create Multiple Fixed Asset Cards
You can create multiple fixed asset cards automatically during purchase invoice posting. For example, if your company purchases 200 computers of the same kind from the same vendor, you do not have to manually create a fixed asset card for each computer; the fixed asset cards can be created automatically.  

## To create multiple fixed asset cards  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Fixed Assets**, and then choose the related link.  
2.  Choose the **Lists** action, and then choose the **Fixed Assets** action.  
3.  On the **Fixed Asset List** page, choose the **New** action.  
4.  On the **Fixed Asset Card** page, fill in the relevant fields.  

    You will use the value of the **No.** field when you generate the remaining fixed assets later.  

5.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Purchase Orders**, and then choose the related link.  
6.  Create a new purchase order, or open the existing purchase order.  
7.  Expand the **Lines** FastTab.  
8.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Type**|Select **Fixed Asset**.|  
    |**No.**|Specify the fixed asset number.<br /><br /> **NOTE:** This should be the same fixed asset number that you entered in the **Fixed Asset** list.|  
    |**No. of Fixed Asset Cards**|Specify the relevant number of duplicates for your fixed asset.<br /><br /> **NOTE:** During invoice posting, duplicate fixed asset cards are automatically generated and added to the fixed asset list. The only difference between the duplicate fixed asset cards is the number assigned to each fixed asset.|  

9. Choose the **OK** button.  

## See Also  
 [Fixed Assets](../../fa-manage.md)  
 [Italian Fixed Assets](italian-fixed-assets.md)
