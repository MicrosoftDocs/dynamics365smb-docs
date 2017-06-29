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
# How to: Set Up Warehouse Employees
Each user who performs warehouse activities must be set up as a warehouse employee assigned to one default location and potentially more non-default locations. This user setup filters all warehouse activities across the database to the employee's location so that the employee can only perform the warehouse activities at the default location. A user can be assigned to additional non-default locations for which the employee can view activity lines but not perform the activities.  
  
### To set up warehouse employees  
  
1.  In the **Search** box, enter **Administration**, and then choose the related link.  
  
2.  In the Administration department, in the **Application Setup** area, choose **Warehouse**.  
  
3.  Choose **Warehouse**, and then choose **Warehouse Employees**.  
  
4.  On the **Home** tab, in the **New** group, choose **New**.  
  
5.  Select the **User ID** field, and then select the user to be added as a warehouse employee. Choose the **OK** button.  
  
6.  In the **Location Code** field, enter the code of the location where the user will be working.  
  
7.  Select the **Default** check box to define the location as the only location where the employee can perform warehouse activities.  
  
8.  Repeat these steps to assign other employees to locations or assign non-default locations to existing warehouse employees.  
  
## See Also  
 [Configure Warehouse Processes](../FullExperience/configure-warehouse-processes.md)   
 [How to: Set Up Warehouse Management](../FullExperience/how-to-set-up-warehouse-management.md)   
 [How to: Convert Existing Locations to Warehouse Locations](../FullExperience/how-to-convert-existing-locations-to-warehouse-locations.md)