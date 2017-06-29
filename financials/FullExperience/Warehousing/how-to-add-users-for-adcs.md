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
# How to: Add Users for ADCS
You can add any user as a user of an Automated Data Capture System \(ADCS\). When you do this, the user must also provide a password. Optionally, you can also provide a connection that identifies the ADCS user as a warehouse employee. The ADCS user password can be different from the Windows logon password of the user.  
  
### To add an ADCS user  
  
1.  In the **Search** box, enter **ADCS Users**, and then choose the related link.  
  
2.  On the **Home** tab, choose **New** to add a new user.  
  
3.  In the **Name** field, enter a name for the user. The name cannot contain more than 20 characters, including spaces.  
  
4.  In the **Password** field, enter a password. The password is masked.  
  
### To indicate that a warehouse employee is an ADCS user  
  
1.  In the **Search** box, enter **Warehouse Employees**, and then choose the related link.  
  
2.  If needed, add a new warehouse employee. For more information, see [How to: Set Up Warehouse Employees](../FullExperience/how-to-set-up-warehouse-employees.md).  
  
3.  On the **Home** tab, in the **Manage** group, choose **Edit List**.  
  
4.  Select a warehouse employee from the list. In the **ADCS User** field, choose the drop-down arrow, and then select the name of an ADCS user from the list.  
  
    > [!NOTE]  
    >  The default warehouse for the employee should be one that uses ADCS. For more information, see [How to: Set Up a Warehouse to Use ADCS](../FullExperience/how-to-set-up-a-warehouse-to-use-adcs.md).  
  
## See Also  
 ADCS Users   
 ADCS User   
 [How to: Test the ADCS Connection](../FullExperience/How%20to:%20Test%20the%20ADCS%20Connection.md)   
 [How to: Create Microsoft Dynamics NAV Users](../FullExperience/How%20to:%20Create%20Microsoft%20Dynamics%20NAV%20Users.md)