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
# How to: Clean Up and Process Data
In some cases, you may want to clean up customer data and process it before you apply it to the database. To do that, you can customize report 8621 to fix issues, such as:  
  
-   Convert dates and decimals to the format required by the regional settings on a user's computer.  
  
-   Remove leading/trailing spaces or special characters.  
  
 After you modify the batch job, use the following procedure to process the data.  
  
### To clean up and process data before applying data  
  
1.  Open the configuration package for the company.  
  
2.  On the **Tables** FastTab, choose **Functions**, and then choose **Process Data**.  
  
3.  To apply the mapping that you have set up, on the **Tables** FastTab, choose **Functions** group, and then choose **Apply Data**.  
  
## See Also  
 [How to: Map Customer Data](../how-to-map-customer-data.md)   
 [How to: Apply Customer Data](../how-to-apply-customer-data.md)   
 Config. Package - Process