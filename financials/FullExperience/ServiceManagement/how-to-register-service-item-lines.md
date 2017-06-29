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
# How to: Register Service Item Lines
When you have created a service order or service quote, you need to register the service item lines where you enter the information about the items you have received for service. This may include a description, service item number, item number, serial number, and service item group, along with fault comments, and so on.  
  
### To register service item lines  
  
1.  In the **Search** box, enter **Service Orders**, and then choose the related link.  
  
2.  Open the relevant service order.  
  
3.  On the **Lines** FastTab, enter a new service item line.  
  
4.  Fill in the **Service Item No.**, **Service Item Group**, **Serial No.**, **Item No.**, and **Description** fields as appropriate.  
  
    -   If the service item is already included in more than one active contract, in other words, signed and not expired, a list of related contracts opens from which you can choose the appropriate contract. Confirm the subsequent message if you want to assign a contract number to the service order line.  
  
    -   If the service item is included in one active contract, the appropriate contract number will be assigned automatically.  
  
    -   If the service item is not registered, you can either register it as a service item or fill in the **Description** field. You can fill in the **Serial No.** and **Item No.** fields if appropriate.  
  
    -   If the service item is registered, but included in a non\-active contract, it will be added to the service order line with the **Contract No.** field left blank.  
  
5.  On the **Lines** toolbar, on the **Line** menu, select **Comments**, and then choose **Faults** to, open the **Service Comments** window for the service item on the line. In the **Date** and **Comment** fields, enter the current date and whatever comments you or the customer may have on the faults of the service item.  
  
6.  You may need to fill in the **Fault Reason Code** field, depending on the settings on the **Mandatory Fields** FastTab in the **Service Mgt. Setup** window. If this field is not visible on the **Lines** FastTab, you can add it. ADD INCLUDE<!--[!INCLUDE[bp_choose_columns](../DesignAndEngineering/includes/bp_choose_columns_md.md)]-->  
  
     For more information, see Service Mgt. Setup.  
  
7.  You can select the **Warranty** field to automatically fill in the warranty related fields with the default warranty information specified in the **Service Mgt. Setup** window. The order date of the service order is used as the starting date of the warranty for spare parts and labor.  
  
8.  Fill in the rest of the fields as appropriate.  
  
     The repair status is set to **Initial** for the line and the response date and time is calculated using the appropriate default values.  
  
 Repeat these steps for each service item line you want to register.  
  
## See Also  
 [How to: Create Service Items](../Service/how-to-create-service-items.md)   
 [How to: Change Response Times for Service Item Lines](../Service/how-to-change-response-times-for-service-item-lines.md)   
 [How to: Lend Loaners](../Service/how-to-lend-loaners.md)   
 [How to: Register Service Item Loaner Comments](../Service/how-to-register-service-item-loaner-comments.md)   
 [How to: Register Accessory Comments](../Service/how-to-register-accessory-comments.md)   
 [How to: View Troubleshooting Guidelines](../Service/how-to-view-troubleshooting-guidelines.md)   
 [How to: Change Service Pricing for Service Items](../Service/how-to-change-service-pricing-for-service-items.md)