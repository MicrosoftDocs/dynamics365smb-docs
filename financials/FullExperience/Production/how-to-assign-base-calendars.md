---
title: "How to: Assign Base Calendars"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "base calendars, assigning"
  - "shipping, calendars"
  - "calendars, base"
ms.assetid: 31c44e22-2531-4b2b-b4c9-7780b33ae7ff
caps.latest.revision: 11
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
# How to: Assign Base Calendars
You can assign a base calendar to your company and its business partners, such as customers, vendors, or locations. Delivery and receipt dates on future sales order, purchase order, transfer order, and production order lines are calculated according to the calendar’s specified working days.  
  
 The following procedure schedules delivery dates on sales order lines for a customer as an example. Note that at this point, you have already set up a base calendar.  
  
 Base calendars are assigned to your own company, customers, vendors, locations, and shipping agents as follows:  
  
-   On the **Company Information** and **Customer** cards, the base calendar is assigned on the **Shipping** FastTab.  
  
-   On the **Vendor** card, the base calendar is assigned on the **Receiving** FastTab.  
  
-   On the **Location** card, the base calendar is assigned on the **Warehouse** FastTab.  
  
-   In the **Shipping Agents** window, the base calendar is assigned in the **Shipping Agent Services** window.  
  
### To assign a base calendar  
  
1.  In the **Search** box, enter **Customers**, and then choose the related link.  
  
2.  Open the **Customer** card for whom you will assign a base calendar.  
  
3.  On the **Shipping** FastTab, in the **Base Calendar Code** field, select the base calendar that you want to assign.  
  
> [!IMPORTANT]  
>  -   If you do not assign a base calendar to a company, all dates are calculated as working days.  
> -   If you enter a blank location on an order line, all dates are calculated as working days.  
> -   Any base calendar defined for the vendor or the location affects how the dates are calculated and rounded to working days. adFor more information, see Lead Time Calculation.  
  
> [!NOTE]  
>  Before you can make customized calendar entries, you must first assign a base calendar to the company.  
  
## See Also  
 [How to: Set Up Base Calendars](../BusinessFunctionality/HowToSetUpBaseCalendars/how-to-set-up-base-calendars.md)   
 [How to: Customize a Calendar](../Production/how-to-customize-a-calendar.md)