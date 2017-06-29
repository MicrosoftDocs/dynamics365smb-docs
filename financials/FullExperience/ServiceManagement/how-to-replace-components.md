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
# How to: Replace Components
When you service a service item that is composed of components, you may need to replace a faulty component with a new one. Every time that you enter a spare part for a service item with components, you have the option of replacing a component or creating a new one.  
  
### To replace a component  
  
1.  In the **Search** box, enter **Service Tasks**, and then choose the related link.  
  
2.  Select the line that includes the relevant service item. On the **Navigate** tab, in the **Service Tasks** group, choose **Item Worksheet**.  
  
3.  Enter a new service line.  
  
4.  In the **Type** field, select **Item**.  
  
5.  In the **No.** field, select the component that you want to replace.  
  
6.  Press Enter. A dialog box opens with three options: **Replace Component**, **New Component**, and **Ignore**.  
  
     The following table describes these options in more detail.  
  
    |FIX INCLUDE HERE<!--[!INCLUDE[bp_tableoption](../ApplicationDesign/includes/bp_tableoption_md.md)] -->|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
    |----------------------------------|---------------------------------------|  
    |**Replace Component**|Changes the status of the component you are replacing to not active, and it will appear on the replaced component list for the service item.|  
    |**New Component**|Enters the new component in the component list of the service item.|  
    |**Ignore**|Does nothing to the component list of the service item.|  
  
7.  Choose **Replace Component**. The **Service Item Component List** window opens.  
  
8.  Select the component that you want to replace, and then choose the **OK** button.  
  
 The new item is not registered as a component of the service item until you post this service line or the service order.  
  
## See Also  
 [How to: Register Spare Parts](../Service/how-to-register-spare-parts.md)   
 [How to: Set Up Service Item Components](../Service/how-to-set-up-service-item-components.md)   
 [How to: Replace Service Items](../Service/how-to-replace-service-items.md)