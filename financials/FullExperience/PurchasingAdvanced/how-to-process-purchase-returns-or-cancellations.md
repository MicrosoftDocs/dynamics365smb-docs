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
# How to: Process Purchase Returns or Cancellations
If you want to return items to your vendor or cancel services that you have purchased, then you can create and post a purchase credit memo that specifies the requested change with regard to the original purchase invoice. You can use the **Copy Document** function to fill the purchase credit memo with the correct purchase invoice information.  
  
 Typically, you create a purchase credit memo in reaction to a credit memo sent to you by a vendor. The purchase credit memo functions as your internal documentation of the credit memo process for accounting purposes.  
  
 The change may relate to all the products on the original purchase invoice or only to some of the products. Accordingly, you can partially return received items or demand partial reimbursement of received services. In that case, you must edit the copied purchase invoice information.  
  
 You can apply the purchase credit memo to one or more posted purchase invoices. This reverses the ledger entries that are affected by the change and enables a refund collection from the vendor. If you want to apply the purchase credit memo to a specific posted purchase invoice, see step 4. If you want to apply the purchase credit memo to multiple posted purchase invoices, follow steps 14 through 18.  
  
> [!NOTE]  
>  If a posted purchase invoice has not yet been paid, then you can use the **Correct** or **Cancel** functions on the posted purchase invoice to automatically reverse the involved transactions. These functions only work for unpaid invoices, and they do not support partial returns or cancellations. For more information, see [How to: Correct or Cancel Unpaid Purchase Invoices](../how-to-correct-or-cancel-unpaid-purchase-invoices.md).  
  
### To create a purchase credit memo  
  
1.  In the **Search** box, enter  **Purchase Credit Memos**, and then choose the related link.  
  
2.  On the **Home** tab, in the **Manage** group, choose **New**.  
  
3.  In the **Vendor Name** field, enter the name of an existing vendor. This is a search-as-you-type field. **Name** is the default filter.  
  
    > [!NOTE]  
    >  If you prefer to find and enter vendors by number or telephone number, you can easily change the default filter. For more information, see [How to: Enter Data](../how-to-enter-data.md).  
  
     Other fields on the purchase credit memo header are now filled with the standard information about the selected customer. You can edit all the fields, such as the fields in the **Payment Details** group, to reflect the credit memo agreement.  
  
4.  To apply the purchase credit memo to one posted purchase invoice, fill in the fields in the **Application Details** group as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Applies-to Doc. Type**|Specify the type of document that the purchase credit memo is applied to.|  
    |**Applies-to Doc. No.**|Specify the purchase document that the purchase credit memo is applied to.|  
    |**Applies-to ID**|Specify if the purchase credit memo is applied to one or more posted purchase invoices using the **Apply Entries** function. For more information, see step 14.|  
  
     When you post the purchase credit memo, it will be applied to the specified posted purchase invoice.  
  
5.  On the **Home** tab, in the **New** group, choose **Copy Document**.  
  
6.  In the **Copy Purchase Document** window, in the **Document Type** field, select **Posted Invoice**.  
  
7.  Choose the **Document No.** field to open the **Posted Purchase Invoices** window, and then select the posted purchase invoice that you want to reverse.  
  
8.  Select the **Include Header** check box if you want to overwrite the current header on the purchase credit memo with the header information about the selected posted purchase invoice.  
  
    > [!NOTE]  
    >  The information that you defined in the **Application Details** group will not be overwritten.  
  
9. Select the **Recalculate Lines** check box if you want the copied posted purchase invoice lines to be updated with any changes in item price and unit cost since the invoice was posted.  
  
10. Choose the **OK** button. The copied invoice lines are inserted in the purchase credit memo.  
  
     If the full invoice quantity is returned or canceled for complete reimbursement, then go to step 19 to post the purchase credit memo.  
  
     In other scenarios, such as partial returns with reimbursement, or if you return additional products, proceed to fill or edit the purchase credit memo lines manually.  
  
11. On the **Lines** FastTab, in the **No.** field, enter the number of an inventory item or service. This is a search-as-you-type field. **No.** is the default filter.  
  
    > [!NOTE]  
    >  If you prefer to find and enter items by name, then you can easily change the default filter. For more information, see [How to: Enter Data](../how-to-enter-data.md).  
  
12. In the **Quantity** field, enter the number of items to be reversed.  
  
    > [!NOTE]  
    >  For items of type **Service**, the quantity is a time unit, such as hours, as indicated in the **Unit of Measure Code** field on the line.  
  
     The **Line Amount** field is updated to show the value in the **Direct Unit Cost** field multiplied by the value in the **Quantity** field.  
  
     The price and line amount are shown with or without VAT depending on what you selected in the **Prices Including VAT** field on the vendor card.  
  
13. Repeat steps 11 and 12 for every inventory item or service that you want to reverse.  
  
     The totals shown at the bottom of the purchase credit memo are automatically calculated as you modify the lines or create new lines. This allows you to verify that the credit memo that you are creating matches the one that you received from your vendor.  
  
14. To apply the purchase credit memo to multiple posted purchase invoices, on the **Home** tab, in the **Process** group, choose **Apply Entries**.  
  
15. In the **Apply Vendor Entries** window, select the lines with the entries that you want the applying entry to be applied to.  
  
16. On the **Navigate** tab, in the **Application** group, choose **Set Applies-to ID**. The number of the purchase credit memo is inserted on the selected lines.  
  
17. On each line, in the **Amount to Apply** field, enter the amount that you want to apply to the individual entry. If you do not enter an amount, the maximum amount is automatically applied. At the bottom of the **Apply Vendor Entries** window, you can see the specific amount in the **Applied Amount** field and verify if the application balances.  
  
18. Choose the **OK** button to close the **Apply Vendor Entries** window. When you post the purchase credit memo, it will be applied to the specified posted purchase invoices.  
  
     When you have created the needed purchase credit memo lines and the single or multiple applications are specified, you can proceed to post the purchase credit memo.  
  
19. On the **Home** tab, in the **Posting** group, choose **Post**.  
  
 The posted purchase invoices that you apply the credit memo to are now reversed. If you have already paid the original invoice, the vendor should now refund the payment to you. If the credit memo is only for part of the product on the original invoice, you may only pay the remaining amount on the original purchase invoice to close it.  
  
 The purchase credit memo is removed and replaced with a new document in the list of posted purchase credit memos, which you access from the Role Center.  
  
## See Also  
 [How to: Record Purchases](../how-to-record-purchases.md)   
 [How to: Register New Products](../how-to-register-new-products.md)   
 [How to: Register New Vendors](../how-to-register-new-vendors.md)   
 DEPARTMENTS Departments   
 [Business Functionality](../Business%20Functionality.md)   
 [Working with Product Name](../working-with-$-p_1-product-name-$-.md)