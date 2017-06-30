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
# How to: Print Checks
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can use the print check option to manage check payments to vendors or refunds to customers. This option lets you generate electronic payments.  
  
 For more information about check layouts, see [How to: Define Check Layouts](how-to-define-check-layouts.md).  
  
### To print checks  
  
1.  In the **Search** box, enter **Payment Journals**, and then choose the related link.  
  
2.  In the **Payment Journal** window, fill in the payment journal lines. Either enter the lines manually or on the **Navigate** tab, in the **Payments** groups, choose **Suggest Vendor Payments**. For more information, see [How to: Generate Electronic Payments](how-to-generate-electronic-payments.md).  
  
3.  In the payment journal line, select the **Bank Payment Type**. Use the following table to determine the bank payment type that you want to use to manage check payments.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_optionsheading](../../includes/bp_tabledescription_md.md)]-->|  
    |-------------------------------------|---------------------------------------|  
    |**\<Blank\>**|Select this option if you do not want to create a check. This is the default option.|  
    |**Computer Check**|Select this option if you want to print a check for the amount on the payment journal line. You must print the checks before you can post the journal lines. You can only select **Computer Check** if the **Bal. Account Type** or the **Account Type** is **Bank Account**.|  
    |**Manual Check**|Select this option if you have created a check manually and want to create a corresponding check ledger entry for this amount. By using this option, you cannot print checks from [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. You can only select **Manual Check** if the **Bal. Account Type** or the **Account Type** is **Bank Account**.|  
    |**Electronic Payment**|Select this option if you want to export this payment, together with other payments, to a file and then transmit that file to your bank. This will allow your bank to electronically transfer the payments from your bank account to the payee's bank account. By using this option, you must export and then transmit the journal lines before you can post. You can only select **Electronic Payment** if the **Bal. Account Type** or the **Account Type** is **Bank Account**, **Vendor**, or **Customer**.|  
    |**Electronic Payment-IAT**|Select this option to export electronic payments using the International ACH Transaction \(IAT\) file format. This file format is required if a payment transaction ../../includes financial agencies outside the United States. By using this option, you must export and then transmit the journal lines before you can post. You can only select **Electronic Payment-IAT** if the **Bal. Account Type** or the **Account Type** is **Bank Account**, **Vendor**, or **Customer**.|  
  
4.  Depending on the **Bank Payment Type** selection, do one the following:  
  
    -   If you selected **Computer Check**, to print checks, on the **Navigate** tab, in the **Payments** group, choose **Print Checks**. On the **Options** FastTab, select the bank account that matches the bank account on the lines of the payment journal.  
  
    -   If you selected **Electronic Payment** or **Electronic Payment-IAT**, to print checks, on the **Navigate** tab, in the **Payments** group, select **Electronic Payments**, and then choose **Export**. You can also use this function to print the remittance advice.  
  
5.  After the checks have been printed successfully, you can post the payment journal.  
  
6.  In the **Payment Journal** window, on the **Actions** tab, in the **Posting** group, choose **Post** or choose **Post and Print**. For more information, see Payment Journal.  
  
### To transfer payment information to the bank  
  
1.  If you selected a payment type of **Electronic Payment** or **Electronic Payment-IAT**, in the **Payment Journal** window, on the **Navigate** tab, in the **Payments** group, select **Electronic Payments**, and then choose **Transmit**.  
  
2.  After the electronic payments have transmitted successfully, you can post the payment journal. On the **Actions** tab, in the **Posting** group, choose **Post** or choose **Post and Print**. For more information, see Payment Journal.  
  
### To cancel printed checks  
  
1.  If you need to cancel the checks after they have been printed, in the **Payment Journal** window, on the **Navigate** tab, in the **Payments** group, choose **Void Check** or choose **Void All Checks**. This lets you void one check or void all checks.  
  
2.  After the journal lines have been printed, exported, transmitted, or posted, check ledger entries are created in the Check Ledger Entry table.  
  
## See Also  
 [Electronic Payments for United States, Canada, and Mexico](electronic-payments-for-united-states-canada-and-mexico.md)   
 Export Electronic Payments   
 [How to: Define Check Layouts](how-to-define-check-layouts.md)   
 [How to: Generate Electronic Payments](how-to-generate-electronic-payments.md)