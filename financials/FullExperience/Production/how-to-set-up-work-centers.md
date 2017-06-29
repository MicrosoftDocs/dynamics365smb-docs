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
# How to: Set Up Work Centers
A **Work Center** card organizes the fixed values and requirements of the production resource, and thus governs the output of production performed in that work center.  
  
 **Prerequisites**  
  
-   Capacity units of measure are set up.  
  
-   At least one work center group is set up.  
  
-   A shop calendar is created. For more information, see [How to: Create Work Center Calendars](../OperationsPlanning/how-to-create-work-center-calendars.md).  
  
 Before you can set up a work center, you must gather all data about your production resources.  
  
### To fill in the General FastTab  
  
1.  In the **Search** box, enter **Work Centers**, and then choose the related link.  
  
2.  Create a new work center card. On the **Home** tab, in the **New** group, choose **New**.  
  
3.  In the **No.** field, enter a work center number.  
  
4.  In the **Description** field, name the work center.  
  
5.  In the **Work Center Group** field, select the higher\-level resource grouping that the work center is organized under.  
  
6.  Select the **Blocked** field if you want to prevent the work center from being used in any processing. This means, among others, that an item produced at the work center can not be posted from a production journal. For more information, see [How to: Register Consumption and Output](../Production/how-to-register-consumption-and-output.md).  
  
### To fill in the Posting FastTab  
  
1.  In the **Direct Unit Cost** field, enter the cost of producing one unit of measure at this work center, excluding any other cost elements. This cost is often referred to as the *direct labor rate*.  
  
2.  In the **Indirect Cost %** field, enter the general operation costs of using the work center as a percentage of the direct unit cost. This percentage amount is added to the direct cost in the calculation of the unit cost.  
  
3.  In the **Overhead Rate** field, enter any non\-operational costs, for example maintenance expenses, of the work center as an absolute amount.  
  
4.  The **Unit Cost** field contains the calculated unit cost of producing one unit of measure at this work center, including all cost elements.  
  
     Unit Cost \= Direct Unit Cost \+ \(Direct Unit Cost x Indirect Cost %\) \+ Overhead Rate.  
  
5.  In the **Unit Cost Calculation** field, define whether the above calculation should be based on the amount of time used:  **Time**, or on the number of produced units:  **Units**.  
  
6.  Select the **Specific Unit Cost** field if you want to define the work center’s unit cost on the routing line where it is being used. This may be relevant for operations with dramatically different capacity costs than what would normally be processed at that work center.  
  
7.  In the **Flushing Method** field, select whether output posting at this work center should be calculated and posted manually or automatically, using either of the following methods.  
  
    |FIX INCLUDE HERE<!--[!INCLUDE[bp_tableoption](../ApplicationDesign/includes/bp_tableoption_md.md)] -->|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
    |----------------------------------|---------------------------------------|  
    |**Forward**|Calculate and post output consumption automatically when the production order is released.|  
    |**Backward**|Calculate and post consumption automatically when the released production order is finished.|  
  
> [!NOTE]  
>  If necessary, the flushing method selected here and on the **Item** card, can be overridden for individual operations by changing the setting on routing lines.  
  
 The **Department Code** and **Project Code** fields relate to the use of dimensions.  
  
### To fill in the Scheduling FastTab  
  
1.  In the **Unit of Measure Code** field, enter the time unit in which this work center’s cost calculation and capacity planning are made.  
  
2.  In the **Capacity** field, define whether the work center has more than one machine or person working at the same time. If your **Product Name** installation does not include the Machine Center functionality, then the value in this field must be **1**\).  
  
3.  In the **Efficiency** field, enter the percentage of the expected standard output that this work center actually outputs. If you enter **100**, it means that the work center has an actual output that is the same as the standard output.  
  
    > [!NOTE]  
    >  The **Consolidated Calendar** field is only relevant if the installation includes the Machine Center granule.  
  
4.  In the **Shop Calendar Code** field, select a shop calendar. For more information, see [How to: Create Work Center Calendars](../OperationsPlanning/how-to-create-work-center-calendars.md).  
  
5.  In the **Queue Time** field, specify a fixed time span that must pass before assigned work can begin at this work center. Note that Queue Time is added to other non\-productive time elements such as Wait Time and Move Time that you may define on routing lines using this work center.  
  
6.  If you use the **Queue Time** field above then you must define a time unit of measure in the **Queue Time Unit of Meas. Code** field.  
  
## See Also  
 Work Center Card   
 Machine Center Card   
 [Shop Calendars](../OperationsPlanning/shop-calendars.md)