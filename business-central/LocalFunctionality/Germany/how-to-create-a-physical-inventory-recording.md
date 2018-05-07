---
    title: How to Create a Physical Inventory Recording
    description: After you have created a physical inventory order and its lines you can create a new physical inventory recording for taking the inventory.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Create a Physical Inventory Recording
After you have created a physical inventory order and its lines you can create a new physical inventory recording for taking the inventory.  

You can create a physical inventory recording manually if it is not necessary to use physical inventory lists or if the physical inventory data will be taken by a scanner. You can also create a physical inventory recording manually even if the related physical recording order does not contain any line. After finishing the physical inventory, the required physical inventory order lines are created automatically. This may be useful, for instance, in the case of a permanent physical inventory.  

However, in most cases, you use a batch job to record inventory. Based on the physical inventory recording, you can print a list for taking the inventory and writing the results down. After that, you can transfer the results from paper to the physical inventory recording lines.  

## To create a physical inventory recording  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Phys. Inventory Order**, and then choose the related link.  
2.  Select the physical inventory order that you want to create an inventory recording for, and then choose the **Edit** action.  
3.  To create a physical inventory recording, choose the **Make New Recording** action.  
4.  In the **Make New Phys. Invt. Recording** window, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Only Lines Not In Recordings**|Select to generate a new physical inventory recording line only if the data do not exist in any other physical inventory recording line.|  
    |**Recording Without Order Permit**|Select to generate a new physical inventory recording line.|  

5.  Choose the **OK** button to start the batch job.  
6.  Choose the **Recordings** action. The physical inventory recording window appears. Select the new created physical inventory recording.  

    You can now print a physical inventory list based on the data on the current physical inventory recording.  

7.  Choose the **Physical Inventory Recording** action.  
8.  In the **Phys. Invt. Recording** window, set the appropriate filters, and then choose the **Print** button or choose the **Preview** button.  

    Optionally, you can use the Copy Phys. Invt. Rec. Line batch job to record serial numbers or lot numbers.  

9. In the **Phys. Inventory Recording** window, select the physical inventory recording line, choose **Functions**, and then choose **Copy Line**.  
10. In the **Copy Phys. Invt. Rec. Line** window, specify the number of copies to make of the selected line, and then choose the **OK** button.  

You can use the printed physical inventory recording to update the actual quantity of the item available in the specified location. To complete the recording process, the **Recorded** check box must be selected for all physical inventory recording lines.  

To show that you have finished the physical inventory recording, you have to set the **Status** on the inventory recording header to **Finished**. For more information, see [Finish a Physical Inventory Recording](how-to-finish-a-physical-inventory-recording.md).  

## To complete a physical inventory recording  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Phys. Inventory Recording**, and then choose the related link.  
2.  Select the physical inventory recording that you want to complete, and then choose the **Edit** action.  
3.  In the **Phys. Invt. Recording** window, on the **Lines** FastTab, in the **Quantity** field for each line, enter the actual item quantity.  
4.  Select the **Recorded** check box for each line.  
5.  On the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Person Recorded**|The person who recorded the inventory.|  
    |**Date Recorded**|The date on which the physical inventory was recorded.|  
    |**Time Recorded**|The time at which the physical inventory was recorded.|  

 You can now finish the physical inventory recording. For more information, see [Finish a Physical Inventory Recording](how-to-finish-a-physical-inventory-recording.md).  

## See Also  
 [Physical Inventory Recording - Counting Physical Inventory](physical-inventory-recording-counting-physical-inventory.md)   
 [Enter Physical Inventory Orders](how-to-enter-physical-inventory-orders.md)   
 [Calculate Quantity On Hand for a Physical Inventory Order](how-to-calculate-quantity-on-hand-for-a-physical-inventory-order.md)   
 [Finish a Physical Inventory Recording](how-to-finish-a-physical-inventory-recording.md)
