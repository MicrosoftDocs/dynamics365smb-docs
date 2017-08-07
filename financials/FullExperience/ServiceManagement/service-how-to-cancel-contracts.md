---
    title: How to: Cancel Contracts | Microsoft Docs
    description: You may need to cancel a service contract when the contract has expired or has been canceled by you or the customer.
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
# How to: Cancel Contracts
You may need to cancel a service contract when the contract has expired or has been canceled by you or the customer.  
  
### To cancel a service contract  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Contracts**, and then choose the related link.  
  
2.  Open the relevant service contract you want to cancel.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Open Contract** to open the service contract for modification.  
  
4.  On the **Details** FastTab, in the **Cancel Reason Code** field, select the relevant reason code. If you want to add more reason codes, choose **Advanced** to open in the **Reason Codes** window and add more codes.  
  
     If the check box in the **Use Contract Cancel Reason** field in the **Service Mgt. Setup** window is selected, you have to specify a cancel reason code when canceling contracts.  
  
5.  On the **General** FastTab, in the **Status** field, select **Canceled**.  
  
6.  If there are any unposted invoices or credit memos for the contract that you want to cancel, a confirmation message will appear. In the message box, choose the **No** button to return back to the contract and post the documents, or **Yes** to continue the contract cancellation process.  
  
7.  If there are any opened prepaid entries for the contract you want to cancel, a confirmation message will appear. In the message box, choose the **No** button to return back to the contract and create a credit memo, or **Yes** to continue the contract cancellation process.  
  
> [!NOTE]  
>  After the contract is canceled, it is not possible to return to its previous status.  
  
## See Also  
 [How to: Create Contract Service Credit Memos](../how-to-create-contract-service-credit-memos.md)   
 [How to: Remove Contract Lines](../how-to-remove-contract-lines.md)