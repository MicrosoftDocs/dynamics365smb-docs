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
# How to: Create Put-aways from Posted Receipts
If your location uses both put-away processing and receive processing and you have deleted put-away lines, or if you use directed put-away and pick and have decided not to use the put-away worksheet, you can create or recreate put-away instructions for posted receipt lines as follows.  
  
### To create a put-away from a posted receipt  
  
1.  In the **Search** box, enter **Posted Whse. Receipts**, and then choose the related link.  
  
2.  Select a posted receipt that might need to be put away.  
  
3.  On the **Navigation** tab, in the **Line** group, choose **Card**.  
  
     If the **Document Status** field is blank, the receipt has not been put away at all. Otherwise, the field indicates the receipt is partially put-away or completely put-away.  
  
4.  If the receipt is partially put away or not put away at all, on the **Actions** tab, in the **Functions** group, choose **Create Put-away**.  
  
5.  Fill in the batch job request window to create the put-away, and then choose the **OK** button.  
  
## See Also  
 [Put Items Away](../put-items-away.md)   
 [Design Details: Inbound Warehouse Flow](design-details-inbound-warehouse-flow.md)