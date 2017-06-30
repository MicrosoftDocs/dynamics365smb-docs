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
# How to: Batch Post Purchase Orders, Invoices, and Credit Memos
If you have set up a large number of purchase orders, it is an advantage to post them with a batch job in the program. You can have them posted at night or at another time when it is convenient.  
  
 Batch posting of invoices and credit memos works in the same way as for orders.  
  
### To batch post purchase orders, invoices, and credit memos  
  
1.  In the **Search** box, enter **Sales Orders**, and then choose the related link.  
  
2.  On the **Home** tab, in the **Process** group, choose **Post Batch**. The batch job request window opens.  
  
3.  Specify the conditions for the batch job.  
  
4.  On the **Purchase Order** FastTab, you can set a filter to select specific order numbers or an interval of order numbers for the batch job to process.  
  
5.  Choose the **OK** button.  
  
     When the batch job is finished, a message box displays how many orders have been posted. If some orders have not been posted, it is because of errors or missing information on the orders. You must then investigate why they have not been posted. You can do this by running the test report.  
  
> [!IMPORTANT]  
>  If the batch posting includes both orders to be received and orders to be invoiced, make sure that the **Qty. to Receive** and **Qty. to Invoice** fields on the orders contain the correct quantities, for example **0**, before you post. In the batch job request window, select the **Receive** and **Invoice** check boxes.  
>   
>  For example, if eight units have been received from an order of 25 units, then the eight units will be invoiced and an additional 12 units will be received.  
  
## See Also  
 Batch Post Purchase Orders   
 Batch Post Purchase Invoices   
 Batch Post Purch. Credit Memos