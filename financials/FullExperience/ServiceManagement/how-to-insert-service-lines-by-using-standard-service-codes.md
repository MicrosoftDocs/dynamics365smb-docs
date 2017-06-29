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
# How to: Insert Service Lines by Using Standard Service Codes
If you have set up standard service codes and assigned them to service item groups, you can insert the standard lines linked to the standard service codes on service documents.  
  
### To insert a standard service line  
  
1.  In the **Search** box, enter **Service Orders**, and then choose the related link.  
  
2.  Create a new service order.  
  
3.  Fill in the fields on the **General** FastTab.  
  
4.  Fill in the service item lines with the required information.  
  
5.  Select the line with the service item that you want to create service lines for, and choose **Actions**![Action Menu icon](../FullExperience/media/actionmenuicon.png "actionMenuIcon"), choose **Functions**, and then choose **Get Std. Service Codes**. The **Standard Serv. Item Gr. Codes** window opens with the standard codes for the service item group specified on the line.  
  
6.  Select the appropriate code, and choose the **OK** button to enter standard service lines.  
  
> [!NOTE]  
>  If the **Service Item Group Code** field on the service item line of the document is blank, this means that the service item does not belong to any service item group. In this case, the **Standard Serv. Item Gr. Codes** window will contain a list of all standard service codes. You should select from the list to insert standard service lines in the document. You may also select from the list of standard service codes assigned to a specific service item group. To view the list, select the relevant code in the **Service Item Group Code** field in the **Standard Serv. Item Gr. Codes** window.  
  
## See Also  
 [How to: Assign Standard Service Codes to Service Item Groups](../FullExperience/how-to-assign-standard-service-codes-to-service-item-groups.md)   
 [How to: Set Up Standard Service Codes](../FullExperience/how-to-set-up-standard-service-codes.md)