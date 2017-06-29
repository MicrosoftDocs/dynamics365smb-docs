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
# How to: Set Up Payment Days and Non-Payment Periods
Payment days and non-payment periods are used to calculate due dates. Due date calculation is used for sales and purchase documents.  
  
 A payment day is a day on which invoices are paid.  
  
 A non-payment period is a range of dates during which the company does not make payments. This functionality is often used for holiday periods.  
  
 For sales and purchase invoices, the customer and vendor payment days and non-payment periods are taken into account.  
  
### To set up payment days and non-payment periods for a company  
  
1.  In the **Search** box, enter **Company Information**, and then choose the related link.  
  
2.  Expand the **Payments** FastTab.  
  
3.  Fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Payment Days Code**|Enter the payment day code.|  
    |**Non-Paymt. Periods Code**|Enter the non-payment periods code.|  
  
4.  To open the **Payment Days** window, on the **Navigate** tab, in the **Payments** group, choose **Payment Days**.  
  
5.  In the **Payment Days** window, in the **Payment Day** field, enter the payment day for the company.  
  
6.  Choose the **OK** button.  
  
7.  To open the **Non-Payment Periods** window, on the **Navigate** tab, in the **Payments** group, choose **Non-Payment Periods**.  
  
8.  Enter information into the relevant fields.  
  
9. Choose the **OK** button.  
  
### To set up payment days for customers and vendors  
  
1.  In the **Search** box, enter **Customers** or enter **Vendors**, and then choose the related link.  
  
2.  Select the required customer or vendor, and then, on the **Navigate** tab, in the **Customers** or **Vendors** group, choose **Payment Days**.  
  
3.  In the **Payment Days** window, in the **Payment Day** field, enter the payment day for the customer or vendor.  
  
4.  Choose the **OK** button.  
  
### To set up non-payment periods for customers and vendors  
  
1.  In the **Search** box, enter **Customers** or enter **Vendors**, and then choose the related link.  
  
2.  Select the required customer or vendor, and then, on the **Navigate** tab, in the **Customers** or **Vendors** group, choose **Non-Payment Periods**.  
  
3.  Fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**From Date**|Enter the starting date for the non-payment period.|  
    |**To Date**|Enter the ending date for the non-payment period.|  
    |**Description**|Enter a description.|  
  
4.  Choose the **OK** button.  
  
## See Also  
 [Spain Local Functionality](../FullExperience/spain-local-functionality.md)   
 Payment Days   
 Non-Payment Periods