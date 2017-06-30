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
# How to: Create Purchase Credit Memos
You usually receive purchase credit memos when you return items to a vendor, but you can also receive them as compensation, such as a purchase allowance. In addition, you can use a credit memo to correct an incorrect purchase invoice.  
  
 When you post the credit memo, [!INCLUDE[d365fin](includes/d365fin_md.md)] creates a posted credit memo. If you have selected the **Return Shipment on Credit Memo** field, posting the credit memo will also create a posted return shipment.  
  
 From the credit memo, you can copy all types of purchase documents, quotes, orders, invoices, receipts, and return shipments.  
  
 If you use the invoicing facilities, it is a good idea to use purchase credit memos too. They make it easier for you to manage your payables.  
  
### To create a purchase credit memo  
  
1.  In the **Search** box, enter **Purchase Credit Memos**, and then choose the related link.  
  
2.  In the **Purchase Credit Memos** window, on the **Home** tab, in the **New** group, choose **New**.  
  
3.  On the **Purchase Credit Memo Card**, fill in the **No.** field. In the **Buy-from Vendor No.** field, enter the number of the vendor to whom you returned the items.  
  
4.  If you want to post the credit memo to a different vendor than the one specified on the **General** FastTab, enter the number of that vendor in the **Pay-to Vendor No.** field on the **Invoicing** FastTab.  
  
5.  In the **Posting Date** field, enter the posting date.  
  
6.  In the **Vendor Cr. Memo No.** field, enter the number that the vendor uses for the credit memo you are creating.  
  
7.  If the purchase credit memo will be applied to an invoice that has already been posted, fill in the **Applies-to Doc. Type** field and the **Applies-to Doc. No.** field on the **Application** FastTab.  
  
8.  On the credit memo lines, enter information about the items that you have returned. You can either fill in the lines manually, or, if you want to copy information from other documents, you have two options for filling in the lines automatically:  
  
    -   You can use the **Copy Document** batch job to copy an existing document to the credit memo. Use this function to copy the entire document. It can be either a posted document or a document that is not yet posted. This function only reverses costs exactly when exact cost reversing is set up as mandatory in the purchases and payables setup.  
  
    -   You can use the **Get Posted Document Lines to Reverse** function to copy one or more posted document lines from one or more posted documents to the new credit memo document. This function’s purpose is to allow you to exactly reverse the costs from the posted document line. This function always exactly reverses the costs from the posted document line, regardless of whether exact cost reversing is set up as required in the purchases and payables setup.   
        When you use either of these functions, and, in the case of the **Copy Document** batch job, when you have also set up exact cost reversing as mandatory in the purchases and payables setup, the original item ledger entries in the **Appl.-to Item Entry** field are linked to ensure that the costs are copied from the original posted document.  
  
         If the line has item tracking, [!INCLUDE[d365fin](includes/d365fin_md.md)] cannot provide exact cost reversing, because the reservation is not available from the purchase credit memo document. You can use the purchase return order for exact cost reversing of an item-tracked line.  
  
9. If the credit memo will be applied to a specific posted invoice, you can open that invoice in the **Posted Purchase Invoices** window.  
  
 If a vendor is also recorded as a contact in Sales and Marketing, and if you have specified an interaction template code for purchase credit memos in the **Marketing Setup** window, when you choose **Print** to print the credit memo, an interaction is automatically recorded in the **Interaction Log Entry** table.  
  
> [!NOTE]  
>  Exact cost reversing of item tracking lines is not available from the Purchase Credit Memo document. If you want to use exact cost reversing with item tracking lines, use the Purchase Order or Purchase Return Order document instead.  
  
## See Also  
 [Correction of Incorrect Posted Documents](../correction-of-incorrect-posted-documents.md)   
 [How to: Copy Information from Purchase Documents to Purchase Credit Memos](../how-to-copy-information-from-purchase-documents-to-purchase-credit-memos.md)   
 [How to: View Purchase Credit Memo Statistics](../how-to-view-purchase-credit-memo-statistics.md)   
 [How to: Assign Item Charges to Purchase Documents](../How%20to:%20Assign%20Item%20Charges%20to%20Purchase%20Documents.md)