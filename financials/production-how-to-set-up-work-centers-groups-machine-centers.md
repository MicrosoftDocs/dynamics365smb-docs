---
    title: How to Set Up Work Centers | Microsoft Docs
    description: A **Work Center** card organizes the fixed values and requirements of the production resource, and thus governs the output of production performed in that work center.
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
# How to: Set Up Work Centers, Work Center Groups, and Machine Centers

The program distinguishes between three types of capacities. These are arranged hierarchically. Each level contains the subordinate levels.  

 The top level is the work center group.  

 Work centers are assigned to the work center groups. Every work center can only belong to one work center group.  

 You can assign various machine centers to every work center. A machine center may only belong to one work center.  

 Planned capacity of a work center consists of the availability of the corresponding machine centers and the additional planned availability of the work center.  

 The planned availability of the work center group is thus the sum of all corresponding availabilities of the machine centers and work centers.  

 The availability is stored in calendar entries.  

A **Work Center** card organizes the fixed values and requirements of the production resource, and thus governs the output of production performed in that work center.  

 **Prerequisites**  

-   Capacity units of measure are set up.  

-   At least one work center group is set up.  

-   A shop calendar is created. For more information, see [How to: Create Work Center Calendars](../how-to-create-work-center-calendars.md).  

 Before you can set up a work center, you must gather all data about your production resources.  

### To fill in the General FastTab  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Work Centers**, and then choose the related link.  

2.  Create a new work center card. On the **Home** tab, in the **New** group, choose **New**.  

3.  In the **No.** field, enter a work center number.  

4.  In the **Description** field, name the work center.  

5.  In the **Work Center Group** field, select the higher-level resource grouping that the work center is organized under.  

6.  Select the **Blocked** field if you want to prevent the work center from being used in any processing. This means, among others, that an item produced at the work center can not be posted from a production journal. For more information, see [How to: Register Consumption and Output](../how-to-register-consumption-and-output.md).  

### To fill in the Posting FastTab  

1.  In the **Direct Unit Cost** field, enter the cost of producing one unit of measure at this work center, excluding any other cost elements. This cost is often referred to as the *direct labor rate*.  

2.  In the **Indirect Cost %** field, enter the general operation costs of using the work center as a percentage of the direct unit cost. This percentage amount is added to the direct cost in the calculation of the unit cost.  

3.  In the **Overhead Rate** field, enter any non-operational costs, for example maintenance expenses, of the work center as an absolute amount.  

4.  The **Unit Cost** field contains the calculated unit cost of producing one unit of measure at this work center, including all cost elements.  

     Unit Cost = Direct Unit Cost + (Direct Unit Cost x Indirect Cost %) + Overhead Rate.  

5.  In the **Unit Cost Calculation** field, define whether the above calculation should be based on the amount of time used:  **Time**, or on the number of produced units:  **Units**.  

6.  Select the **Specific Unit Cost** field if you want to define the work center’s unit cost on the routing line where it is being used. This may be relevant for operations with dramatically different capacity costs than what would normally be processed at that work center.  

7.  In the **Flushing Method** field, select whether output posting at this work center should be calculated and posted manually or automatically, using either of the following methods.  

    |ADD INCLUDE<!--[!INCLUDE[bp_tableoption](../../includes/bp_tabledescription_md.md)]-->|  
    |----------------------------------|---------------------------------------|  
    |**Forward**|Calculate and post output consumption automatically when the production order is released.|  
    |**Backward**|Calculate and post consumption automatically when the released production order is finished.|  

> [!NOTE]  
>  If necessary, the flushing method selected here and on the **Item** card, can be overridden for individual operations by changing the setting on routing lines.  

 The **Department Code** and **Project Code** fields relate to the use of dimensions.  

### To fill in the Scheduling FastTab  

1.  In the **Unit of Measure Code** field, enter the time unit in which this work center’s cost calculation and capacity planning are made.  

2.  In the **Capacity** field, define whether the work center has more than one machine or person working at the same time. If your **Product Name** installation does not include the Machine Center functionality, then the value in this field must be **1**).  

3.  In the **Efficiency** field, enter the percentage of the expected standard output that this work center actually outputs. If you enter **100**, it means that the work center has an actual output that is the same as the standard output.  

    > [!NOTE]  
    >  The **Consolidated Calendar** field is only relevant if the installation includes the Machine Center granule.  

4.  In the **Shop Calendar Code** field, select a shop calendar. For more information, see [How to: Create Work Center Calendars](../how-to-create-work-center-calendars.md).  

5.  In the **Queue Time** field, specify a fixed time span that must pass before assigned work can begin at this work center. Note that Queue Time is added to other non-productive time elements such as Wait Time and Move Time that you may define on routing lines using this work center.  

6.  If you use the **Queue Time** field above then you must define a time unit of measure in the **Queue Time Unit of Meas. Code** field.

# How to: Set Up Work Center Groups
The work center groups offer you the possibility for classifying work groups. Setting up work center groups and the assigning work centers does not influence capacity planning.  

### To set up work center groups  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Work Center Groups**, and then choose the related link.  

2.  Create a new work center group, and fill in a code and name for the new work center group.  

3.  Close the window.

# How to: Set Up Machine Centers
The machine centers are used as the lowest capacity level. No further subdivision is possible. You must therefore use machine centers for either single machines or a number of identical machines that do not need to be distinguished any further.  

### To set up a machine center  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Machine Centers**, and then choose the related link.  

2.  Create a new **Machine Center** card. On the **Home** tab, in the **New** group, choose **New**.  

3.  Enter a new machine center number. If you have set up a default machine center number series, press the Enter key to fill in this field with the next number in the series.  

4.  Fill in the other fields. The **No.** and **Work Center No.** fields are required.  

5.  Close the window.  

> [!NOTE]  
>  The **Work Center No.** field is used to link the machine center to a work center.  

# How to: Enter Master Data for Output Posting
To post work progress automatically, you must assign a flushing method to the machine center or the work center.  

### To enter master data for output posting  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Machine Centers**, and then choose the related link.  

2.  Open the relevant machine center card from the list.  

3.  On the **Posting** FastTab, fill in the **Flushing Method** field. You can choose from the following options.  

    |Flushing Method|Description|  
    |---------------------|-----------------|  
    |**Manual**|Manual posting of consumption in the output journal.|  
    |**Forward**|Automatic posting of planned run time and output quantity upon releasing the production order.|  
    |**Backward**|Automatic posting of planned run time and output quantity upon finishing the production order.|  

4.  Repeat these steps on the **Posting** FastTab of the **Work Center** card.  


## See Also  
 Work Center Card   
 Machine Center Card   
 [Shop Calendars](../shop-calendars.md)
