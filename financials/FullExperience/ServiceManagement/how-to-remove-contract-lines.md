---
title: "How to: Remove Contract Lines"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "service contracts, removing lines"
  - "removing, contract lines"
  - "contracts (service), removing lines"
ms.assetid: 812a5076-cd87-4f3f-9a9b-80c5cdc84a9c
caps.latest.revision: 7
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
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
 [How to: Cancel Contracts](../Service/how-to-cancel-contracts.md)   
 [How to: Create Contract Service Credit Memos](../Service/how-to-create-contract-service-credit-memos.md)   
 Automatic Credit Memos