---
    title: Overview of Setups for Service Items and Service Item Components | Microsoft Docs
    description: Learn about the things you must set up before you can use service items, including default values such as response time, contract discount percent, and service price group.
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
# How to: Set Up Service Items and Service Item Components
Before you can work with service items, you must set up service items. 

## How to: Set Up Service Item Groups
You can set up groups of items that are related in terms of repair and maintenance. You can define default values for service items in a service item group, such as response time, contract discount percent, and service price group. For items in a service item group, you can select whether you want them to be automatically registered as service items when they are sold.  
  
You assign service item groups to items on the **Item** card, and to service items on the **Service Item** card.  
  
### To set up a service item group  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Item Groups**, and then choose the related link.  
2. Create a new service item group.  
3. Fill in the **Code** and **Description** fields.  
4. In the **Default Contract Discount %** field, enter the default contract discount percentage that you want the service items in the group to have.  
5. In the **Default Serv. Price Group Code** field, enter the default service price group code that you want the service items in the group to have.  
6. In the **Default Response Time (Hours)** field, enter the default response time in hours that you want the service items in the group to have.  
7. If you want to register the items in the group as service items when they are sold, select the **Create Service Item** field.  

## How to: Set Up Service Item Components
A service item can consist of several components, which can be replaced with spare parts when the item is serviced. These components are set up on the **Service Item Component List** page. Additionally, if you want to set up components for service items that are BOMs, you can copy the BOM items and create them as service item components. 
  
### To set up service item components  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Items**, and then choose the related link. 2. Open the service item for which you want to set up components.  
3. On the **Navigate** tab, in the **Serv. Item** group, choose **Components**. The **Service Item Component List** window opens.  
4. Add a new component. On the **Home** tab, in the **New** group, choose **New**.  
5. In the **Type** field, select **Service Item** if the component itself is a registered service item. Otherwise, select **Item**.  
6. In the **No.** field, select the item or service item that is a component of the service item.  

### To set up service item components from a BOM
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Items**, and then choose the related link.  
2. Open the service item for which you want to set up components from a BOM.  
3. On the **Navigate** tab, in the **Serv. Item** group, choose **Components**. The **Service Item Component List** window opens.  
4. On the **Navigate** tab, in the **Component** group, choose **Copy from BOM**.  
  
    If the item that the service item is linked to is a BOM, the components for all the items in the BOM are created automatically.  

## See Also
[How to: Set Up Codes for Standard Services](service-how-setup-service-coding.md)   
[How to: Set Up Troubleshooting](service-how-setup-troubleshooting.md)