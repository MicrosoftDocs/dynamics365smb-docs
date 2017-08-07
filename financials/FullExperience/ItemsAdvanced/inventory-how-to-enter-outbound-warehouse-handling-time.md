---
    title: How to: Enter Outbound Warehouse Handling Time | Microsoft Docs
    description: If you want to set up an outbound warehouse handling time to be included in the order promising calculation on the sales line, you can set this up as a default for the inventory.
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
# How to: Enter Outbound Warehouse Handling Time
If you want to set up an outbound warehouse handling time to be included in the order promising calculation on the sales line, you can set this up as a default for the inventory.  
  
### To enter outbound warehouse handling time in the inventory setup window  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Inventory Setup**, and then choose the related link.  
  
2.  On the **General** FastTab, in the **Outbound Whse. Handling Time** field, enter the number of days you want to include in the order promising calculation.  
  
> [!NOTE]  
>  If you have filled in the **Outbound Whse. Handling Time** field on the Location card for your location, this field is used as the default outbound warehouse handling time.  
  
### To enter outbound warehouse handling time on location cards  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Locations**, and then choose the related link.  
  
2.  Open the relevant location card.  
  
3.  On the **Warehouse** FastTab, in the **Outbound Whse. Handling Time** field, enter the number of days that you want to include in the order promising calculation.  
  
> [!NOTE]  
>  If you leave the **Outbound Whse. Handling Time** field blank, then the calculation uses the value in the **Inventory Setup**  window.  
  
## See Also  
 Location Card   
 Inventory Setup   
 [Date Calculation for Sales](../date-calculation-for-sales.md)   
 [Date Calculation for Purchases](../date-calculation-for-purchases.md)