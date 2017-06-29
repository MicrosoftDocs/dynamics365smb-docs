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
# How to: Set Up Repair Statuses
You use the **Repair Status Setup** window to set up repair status options that identify the progress of repair and maintenance of service items in service orders. You are required to set up at least nine repair status options that identify situations or actions taken when servicing service items.  
  
### To set up a repair status  
  
1.  In the **Search** box, enter **Repair Status**, and then choose the related link.  
  
2.  Create a new repair status. On the **Home** tab, in the **New** group, choose **New**.  
  
3.  Fill in the **Code** and **Description** fields.  
  
4.  In the **Service Order Status** field, select to which one of the four service order status options you want to link the repair status to. Status options are **Pending**, **In Process**, **Finished** or **On Hold**. The **Priority** field is filled in with the priority of the service order status you have selected.  
  
5.  Select only one of the following repair status options: **Initial**, **In Process**, **Finished**, **Partly Serviced**, **Referred**, **Spare Part Ordered**, **Spare Part Received**, **Waiting for Customer**, or **Quote Finished**. A repair status cannot be linked more than one repair status options.  
  
6.  Select the **Posting Allowed** field if you want to be able to post service orders, including service items, with this repair status.  
  
7.  Select the **Pending Status Allowed** field to be able to manually change the service order status option to **Pending** in service orders including service items with this repair status.  
  
8.  Select the **In Process Status Allowed**, **Finished Status Allowed**, and **On Hold Status Allowed** fields in the same way.  
  
 Repeat these steps for each of the repair status options you want to create.  
  
## See Also  
 [How to: Work on Service Tasks](../FullExperience/how-to-work-on-service-tasks.md)   
 [How to: Set Up Service Status Priorities](../FullExperience/how-to-set-up-service-status-priorities.md)