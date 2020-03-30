---
    title: Service Order Status and Repair Status | Microsoft Docs
    description: The Status field in the Service Order page and the service item repair status, which is represented by the Repair Status Code field in the Service Order page have a certain relationship in Service Management. The service order status reflects the repair status of all the service items in the service order.
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
# Service Order Status and Repair Status
The **Status** field on the **Service Order** page and the service item repair status, which is represented by the **Repair Status Code** field on the **Service Order** page have a certain relationship in Service Management. The service order status reflects the repair status of all the service items in the service order.  

> [!NOTE]  
>  These two status field are not related to the **Release Status** field on the service order header, which determines how the warehouse handles service items.  

 Each time the repair status of a service item is changed in a service order, the status of the order is updated. To display the status that reflects the overall repair status of the individual service items, you must specify the following:  

* The service order status that each repair status is linked to. For more information, see Service Order Status.  
* The level of priority of each service order status option. For more information, see Priority.  

 When you convert a service quote to a service order, the repair status of each service item is changed in the order to **Initial** and the service order status is changed to **Pending**.  

## Specifying Service Order Status for Repair Status  
Each repair status is linked to a particular service order status. The options for the service order status are as follows: **Pending**, **In Process**, **On Hold**, and **Finished**. The repair status options are as follows: **Initial**, **In Process**, **Referred**, **Partly Serviced**, **Quote Finished**, **Waiting for Customer**, **Spare Part Ordered**, **Spare Part Received**, and **Finished**.  

### Pending  
The service order status **Pending** indicates that the service can start or continue at any time. Therefore, the repair status options of **Initial**, **Referred**, **Partly Serviced**, and **Spare Part Received** can be linked to this service order status.  

### In Process  
The service order status **In Process** indicates that the service is in process. Therefore, the repair status options **In Process** and **Spare Part Ordered** can both be linked to this service order status. If you link the **Spare Part Ordered** status to an **In Process** service order status, you must also link the **Spare Part Received** status to this service order status.  

### On Hold  
The service order status **On Hold** indicates that the service is temporarily on hold because you are waiting for a customer response or spare parts before the service can start. Therefore, the repair status options of **Quote Finished**, **Spare Part Ordered**, and **Waiting for Customer** can be linked to this service order status.  

### Finished  
The service order status **Finished** indicates that the service has been completed. Therefore, the **Finished** repair status is linked to this status.  

## Assigning Priority to Service Order Status  
When a repair status of a service item is changed, the service order status options linked to the different repair status options of all the service items in the order are identified. If the service items are linked to two or more service order status options, the service order status option with the highest priority is selected.  

You must decide which service order status contains the most important information about the status of the service order and assign that status the highest priority, and so on.  

### Example  
A typical priority level assignment could be as follows:  

* In Process - High  
* Pending - Medium high  
* On Hold - Medium low  
* Finished - Low  

For example, if one service item has the repair status **Initial**, linked to the service order status **Pending**, another has the repair status **In Process**, linked to the service order status **In Process**, and a third has the repair status **Spare Part Ordered**, linked to the service order status **On Hold**, the resulting service order status will be **In Process** because this has the highest priority.  

## See Also  
[Set Up Statuses for Service Orders and Repairs](service-order-repair-status.md)  
[Setting Up Service Management](service-setup-service.md)  
