---
    title: How to: Set Up In-Transit Codes | Microsoft Docs
    description: Before you transfer items between locations using transfer routes, you need to set up in-transit codes.
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
# How to: Set Up In-Transit Codes
Before you transfer items between locations using transfer routes, you need to set up in-transit codes.  
  
 When the transfer order is posted, the items on the line are no longer available at one of your locations but are in transit. The items on the line are in a temporary, fictive location described by one of your in-transit codes.  
  
 You set up in-transit codes on the location card. You can set up as many or as few in-transit codes as you like.  
  
### To set up in-transit codes  
  
1.  In the **Search** box, enter **Locations**, and then choose the related link.  
  
2.  Create a new Location card. You must fill in the **Code** and **Name** fields.  
  
3.  Select the **Use As In-Transit** field.  
  
 Repeat this procedure to set up as many in-transit codes as you want.  
  
> [!TIP]  
>  One or two codes might be enough for your purposes, for example, simply “InTransit”, or two related codes: “OwnVhcl” for items being transported in your own vehicles, and “OtherCarr” for items being transported by other carriers. You can also set up in-transit codes that indicate something about the in-transit arrangement, for example, ExtrInsur for extra insurance.  
  
## See Also  
 [How to: Set Up Transfer Routes](../how-to-set-up-transfer-routes.md)