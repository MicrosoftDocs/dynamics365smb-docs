---
    title: How to: Calculate Subcontracting Worksheets and Create Subcontract Purchase Orders | Microsoft Docs
    description: The **Subcontracting Worksheet** window functions like the **Planning Worksheet** by calculating the needed supply, in this case purchase orders, which you review in the worksheet and then create with the **Carry Out Action Message** function.
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
# How to: Calculate Subcontracting Worksheets and Create Subcontract Purchase Orders
The **Subcontracting Worksheet** window functions like the **Planning Worksheet** by calculating the needed supply, in this case purchase orders, which you review in the worksheet and then create with the **Carry Out Action Message** function.  
  
> [!NOTE]  
>  Only production orders with status **Released** can be accessed and used from a subcontracting worksheet.  
  
### To calculate the subcontracting worksheet  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Subcontracting Worksheet**, and then choose the related link.  
  
2.  To calculate the worksheet, on the **Actions** tab, in the **Functions** group, choose **Calculate Subcontracts**.  
  
3.  In the **Calculate Subcontracts** window, set filters for the subcontracted operations, or the work centers where they are performed, to calculate only the relevant production orders.  
  
4.  Choose the **OK** button.  
  
     Review the lines in the **Subcontracting Worksheet** window. The information in this worksheet comes from the production order and production order routing lines and flows to the purchase order when that document is created. You can delete a row from the worksheet without affecting the original information, just as you can with the other worksheets. The information will reappear the next time you run the **Calculate Subcontracts** function.  
  
### To create the subcontract purchase order  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Subcontracting Worksheet**, and then choose the related link.  
  
2.  On the **Actions** tab, in the **Process** group, choose **Carry Out Action Message**.  
  
3.  Select the **Print Orders** field to print the purchase order as it is created.  
  
4.  Choose the **OK** button.  
  
 If all subcontraced operations are sent to the same vendor location, then only one purchase order is created.  
  
 The worksheet line that was turned into a purchase order is deleted from the worksheet. Once a purchase order is created, it will not appear in the worksheet again.  
  
## See Also  
 [About Subcontracting](../about-subcontracting.md)   
 [How to: Post Subcontract Purchase Orders](../how-to-post-subcontract-purchase-orders.md)