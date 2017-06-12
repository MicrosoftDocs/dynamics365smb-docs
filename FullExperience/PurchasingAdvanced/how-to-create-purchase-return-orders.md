---
title: "How to: Create Purchase Return Orders"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "return orders, creating"
  - "purchase returns, creating"
ms.assetid: e7397d79-0fc6-4454-9dda-febdc6155147
caps.latest.revision: 7
ms.author: "sgroespe"
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
# How to: Create Purchase Return Orders
If you have agreed with your vendor to return a purchased item that you are dissatisfied with, create a purchase return order to record the return.  
  
 The following procedure describes how to create the return order, beginning at the point where you have received the item.  
  
### To create a purchase return order  
  
1.  In the **Search** box, enter **Purchase Return Orders**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**.  
  
3.  Leave the **No.** field to automatically insert the next number from the default number series. Alternatively, choose the field to select from an alternative series.  
  
4.  In the **Buy\-from Vendor No.** field, enter the number of the vendor that you originally bought the item from.  
  
     The **General** FastTab and all other FastTabs are now filled with master data from the vendor card.  
  
5.  Fill in the **Vendor Authorization No.** field if you have received a return materials authorization \(RMA\) number from your vendor.  
  
6.  Fill in the lines manually, or use one of the following functions to copy information from other documents.  
  
    |**Function**|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |------------------|---------------------------------------|  
    |**Get Posted Document Lines to Reverse**|Copies lines of one or more posted documents to be reversed.|  
    |**Copy Document**|Copies both the header and lines of one posted or open document to be reversed.<br /><br /> Requires that the **Exact Cost Reversing Mandatory** check box is selected in the **Purchases & Payables Setup** window.|  
  
     When you post the purchase return order, a link is created through the **Appl.\-to Item Entry** field to the original item ledger entry to ensure that the costs are copied from the original posted purchase order.  
  
7.  Choose the **Return Reason Code** field to select a relevant code to describe the reason why you are returning the item.  
  
## See Also  
 [Appl.\-to Item Entry](../Topic/\($%20T_39_38%20Appl.-to%20Item%20Entry%20$\).md)   
 [How to: Assign Exact Cost Reversing in Purchases](../Finance/how-to-assign-exact-cost-reversing-in-purchases.md)   
 [How to: Create and Post Purchase Allowances](../Finance/how-to-create-and-post-purchase-allowances.md)   
 [How to: Create Replacement Purchase Orders](../Purchasing/how-to-create-replacement-purchase-orders.md)   
 [How to: Create Corrective Purchase Invoices](../Finance/how-to-create-corrective-purchase-invoices.md)   
 [About Returns Management](../Purchasing/about-returns-management.md)