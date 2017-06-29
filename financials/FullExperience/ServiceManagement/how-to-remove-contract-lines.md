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
# How to: Remove Contract Lines
You may need to remove contract lines from the service contract as you remove corresponding service items from the service contract. Usually you remove a contract line that is expired or corresponds to the service item that has broken down.  
  
### To remove contract lines  
  
1.  In the **Search** box, enter **Service Contracts**, and then choose the related link.  
  
2.  Open the service contract from which you want to remove contract lines.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Open Contract** to open the service contract for modification.  
  
4.  On the **Lines** FastTab, select the contract line you want to remove. Fill in the **Contract Expiration Date** field with the date as of which you want to remove the line. For example, you could enter the date when the service item broke down.  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Remove Contract Lines**. The **Remove Lines from Contract** window opens.  
  
6.  On the **Service Contract Line** FastTab, fill in the default filters: **Contract No.**, **Service Item No.**, and **Contract Type**. If needed, you can apply more filters or change the existing ones.  
  
7.  On the **Options** FastTab, fill in the necessary fields. In the **Action** field, select **Delete Lines**.  
  
8.  Choose the **OK** button to remove the lines.  
  
> [!NOTE]  
>  If the contract is not detailed, you must update the value in the **Annual Amount** field on the **Invoice Details** FastTab in the **Service Contract** window, reflecting the loss of the service item from the contract.  
>   
>  If the contract is detailed and prepaid, and you have posted invoices for the contract, you can create a credit memo for the contract. On the **Actions** tab, in the **Functions** group, choose **Create Credit Memo**. This is unnecessary if the check box in the **Automatic Credit Memos** field on the **Invoice Details** FastTab is selected. In that case, a credit memo is created automatically when you remove a contract line.  
  
## See Also  
 [How to: Cancel Contracts](../how-to-cancel-contracts.md)   
 [How to: Create Contract Service Credit Memos](../how-to-create-contract-service-credit-memos.md)   
 Automatic Credit Memos