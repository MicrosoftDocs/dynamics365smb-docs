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
# How to: Customize a Package or Worksheet
Use the configuration worksheet to gather together and categorize the information that you want to use to configure a new company, and arrange tables in a logical way. Formatting in the worksheet is based on a simple hierarchy: areas contain groups, which in turn contain tables. Areas and groups are optional, but are necessary if you want to be able to see an overview of the configuration process on the ADD INCLUDE<!--[!INCLUDE[rim](../../includes/how-to-use-the-rapidstart-services-role-center-to-track-progress.md).  
  
 Make sure that you are on the ADD INCLUDE<!--[!INCLUDE[rim](../../includes/how-to-change-role-centers.md). Choose the RapidStart Profile ID.  
  
### To create an area or group for configuration  
  
1.  In the **Search** box, enter **Configuration Worksheet**, and then choose the related link.  
  
2.  In the **Line Type** field, choose **Area**. In the **Name** field, enter a descriptive name.  
  
3.  In the **Line Type** field, choose **Group**. In the **Name** field, enter a descriptive name.  
  
4.  In the **Line Type** field, choose **Table**. In the **Table ID** field, select the table you want to include in the worksheet.  
  
 Now you can assign the tables to specific configuration packages that you have created or plan to create. For more information, see [How to: Assign a Configuration Package](../how-to-assign-a-configuration-package.md).  
  
### To work with promoted tables  
  
1.  Select the **Promoted Table** check box to indicate a table that frequently will be used during the setup process by a typical customer, for example, the **G/L Account** table. When a table has this designation, a customer will be able to easily filter his worksheet to see just the list of promoted tables that require attention.  
  
2.  To see the filtered view, on the **Home** tab, in the **Show** group, choose **Promoted Only**. The list of tables contains only those tables that have the check box selected.  
  
## See Also  
 [How to: Create a Configuration Package](../how-to-create-a-configuration-package.md)