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
# How to: Enter Inbound Warehouse Handling Time
If you want to include warehouse handling time in the order promising calculation on the purchase line, you can set it up as a default for the inventory and for your location.  
  
### To enter inbound warehouse handling time in the inventory setup window  
  
1.  In the **Search** box, enter **Inventory Setup**, and then choose the related link.  
  
2.  On the **General** FastTab, in the **Inbound Whse. Handling Time** field, enter the number of days that you want to include in the order promising calculation.  
  
> [!NOTE]  
>  If you have filled in the **Inbound Whse. Handling Time** field on the **Location Card** for your location this field is used as the default inbound warehouse handling time.  
  
### To enter inbound warehouse handling time on location cards  
  
1.  In the **Search** box, enter **Location**, and then choose the related link.  
  
2.  Open the relevant location card.  
  
3.  On the **Warehouse** FastTab, in the **Inbound Whse. Handling Time** field, enter the number of days that you want to be included in the order promising calculation.  
  
> [!NOTE]  
>  If you leave the **Inbound Whse. Handling Time** field blank, then the calculation uses the value in the **Inventory Setup**  window.  
  
## See Also  
 Location Card   
 Inventory Setup   
 [Date Calculation for Purchases](../Purchasing/date-calculation-for-purchases.md)   
 [Date Calculation for Purchases](../Purchasing/date-calculation-for-purchases.md)