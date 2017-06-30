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
# How to: Export BACS Files
The following procedure describes how to export a BACS file, one of the payment options supported by ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]-->.  
  
### To export a BACS file  
  
1.  In the **Search** box, enter **Bank Accounts**, and then choose the related link.  
  
2.  Select the bank through which you will make the BACS payment, and on the **Home** tab, in the **Manage** group, choose **Edit**.  
  
3.  On the **Transfer** FastTab, set the **Payment Export Format** field to **BACS**.  
  
     Choose the **OK** button.  
  
4.  In the **Search** box, enter **Payment Journals**, and then choose the related link.  
  
5.  Select a batch in the **Batch Name** field. In the **General Journal Batches** window, for the batch, select the **Allow Payment Export** check box.  
  
     Choose the **OK** button.  
  
6.  In the **Payment Journal** window, create a payment line. For more information, see [How to: Create a Bankers' Automated Clearing Service File](../how-to-create-a-bankers-automated-clearing-service-file.md).  
  
7.  On the **Home** tab, in the **Process** group, choose **Export Payments to File**.  
  
     For information on specifying options in the **BACS Export** window, see BACS Export.  
  
    > [!NOTE]  
    >  When you open the **BACS Export** window for the first time, you may receive a message that asks for permission to create the file. Select the option that allows you to create the file.  
  
8.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  
  
     The BACS information is now exported, and you can either save the data to a file, or you can open the file in the appropriate format.  
  
 You can export a line again if needed. On the **Home** tab, in the Bank group, choose **Export Payments to File**, and then choose **Yes**.  
  
## See Also  
 [How to: Create a Bankers' Automated Clearing Service File](../how-to-create-a-bankers-automated-clearing-service-file.md)