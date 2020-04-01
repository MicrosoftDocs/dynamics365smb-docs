---
    title: How to Set Up Put-away Templates | Microsoft Docs
    description: With directed put-away and pick functionality, the most appropriate bin for your items at any given time is suggested, according to the put-away template that you have set up for the warehouse, the bin rankings you have given to the bins, and the minimum and maximum quantities that you have set up for fixed bins.
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
# Set Up Put-away Templates
With directed put-away and pick functionality, the most appropriate bin for your items at any given time is suggested, according to the put-away template that you have set up for the warehouse, the bin rankings you have given to the bins, and the minimum and maximum quantities that you have set up for fixed bins.  

You can set up a number of put-away templates and select one of them to govern put-aways in general in your warehouse. You can also select a put-away template for any item or stockkeeping unit that might have special put-away requirements.  

## To set up put-away templates  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Put-away Templates**, and then choose the related link.  
2.  Choose the **New** action.  
3.  Enter a code that is the unique identifier of the template you are about to create.  
4.  Enter a short description, if you wish.  
5.  Fill in the first line with the bin requirements that you want fulfilled first and foremost when suggesting a put-away.  
6.  Fill in the second line with the bin requirements that would be your second choice to fulfill in finding a bin for put-away. The second line is used only if a bin that meets the requirements of the first line cannot be found.  
7.  Continue to fill in the lines until you have described all the acceptable bin placements that you want to use in the put-away process.  
8.  On the last line in the put-away template, select the **Find Floating Bin** check box.  

You can create various put-away templates and then apply them as you see fit. The put-away template that you selected for the item or stockkeeping unit, if any is used first. If these fields are not filled in, then the put-away template that you selected for the warehouse on the **Bin Policies** FastTab on the location card is used.  

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
