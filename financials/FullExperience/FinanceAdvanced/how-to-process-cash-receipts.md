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
# How to: Process Cash Receipts
Cash receipts or deposits are registered using a cash receipt journal. A cash receipt journal is a type of general journal, so you can use it to post transactions to general ledger, bank, customer, vendor, and fixed assets accounts. You can apply the payment to one or more debit entries when you post the payment, or you can apply the posted entries later.  
  
### To fill in and post a cash receipt journal  
  
1.  In the **Search** box, enter **Cash Receipt Journal**, and then choose the related link.  
  
2.  Select the relevant batch in the **Batch Name** field.  
  
3.  Fill in the **Posting Date** field.  
  
4.  In the **Document Type** field, select **Payment**..  
  
5.  The **Document No.** field is filled in by the number series assigned to the batch.  
  
6.  Use the **External Document No.** field to store an identifier such as the customer's check number. ADD INCLUDE<!--[!INCLUDE[bp_choose_columns](../DesignAndEngineering/includes/bp_choose_columns_md.md)]-->  
  
7.  In the **Account Type** field, select **Customer**.  
  
8.  Select the proper **Account No.**  
  
9. If you want to post the application at the same time as you post the journal, do one of the following.  
  
    |**Posting option**|**Process**|  
    |------------------------|-----------------|  
    |To record a full invoice payment.|In the **Applies-to Doc. No.** field, select the line to which payment should be applied.|  
    |To record a partial invoice payment.|1.  In the **Amount** field, enter the amount you wish to apply as a negative number.<br />2.  In the **Applies-to Doc. No.** field, select the line, and choose the **OK** button.|  
    |If you are recording full payment for multiple invoices.|1.  On the **Actions** tab, in the **Functions** group, choose **Apply Entries**.<br />2.  For each line to which the payment is to be applied, select the line, and on the **Navigate** tab, in the **Application** group, choose **Set Applies-to ID**.<br />3.  When you have finished all the lines, choose the **OK** button.|  
    |If you are recording a partial payment for multiple invoices.|1.  On the **Actions** tab, in the **Functions** group, choose **Apply Entries**.<br />2.  On each line to which the payment is to be applied, on the **Navigate** tab, in the **Application** group, choose **Set Applies-to ID**.<br />3.  Enter a value in the **Amount to Apply** field. Enter the partial amount as a positive number, and then choose the **OK** button.|  
  
10. In the **Balancing Account Type** field, select **G\/L Account** for cash payments, and **Bank Account** for other payments.  
  
11. In the **Balancing Account No.** field, select the cash account for cash payments, or the relevant bank account for other payments.  
  
12. Post the journal.  
  
## See Also  
 Cash Receipt Journal   
 [How to: Fill and Post General Journals](../Finance/how-to-fill-and-post-general-journals.md)   
 [Apply Sales Transactions](../Finance/apply-sales-transactions.md)