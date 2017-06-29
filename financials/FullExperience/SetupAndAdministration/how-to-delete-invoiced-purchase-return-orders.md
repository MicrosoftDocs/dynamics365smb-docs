---
title: "How to: Delete Invoiced Purchase Return Orders"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "purchase returns, deleting"
ms.assetid: 11697285-327b-4453-b41a-9d5ce5d09703
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
# How to: Delete Invoiced Purchase Return Orders
Return orders are usually deleted after they are invoiced. When you post an invoice, it is transferred to the **Posted Purchase Credit Memo** window. If you selected the **Return Shipment on Credit Memo** check box in the **Purchases & Payable Setup** window, then the invoice is transferred to the **Posted Return Shipment** window.  
  
 In certain situations, you may need to delete invoiced purchase return orders that were not deleted or you may need to reduce the number of posted invoices. You can delete the documents using the **Delete Invd Purch. Ret. Orders** batch job.  
  
### To delete invoiced purchase return orders  
  
1.  In the **Search** box, enter **Delete Invoiced Purchase Return Orders**, and then choose the related link.  
  
2.  Set filters in the **No.**, **Buy\-from Vendor No.**, and **Pay\-to Vendor No.** fields to select the orders to be deleted.  
  
3.  Choose the **OK** button.  
  
 Before deleting, the batch job checks if the purchase return orders are fully shipped and invoiced  
  
## See Also  
 [How to: Combine Return Shipments](../Purchasing/how-to-combine-return-shipments.md)   
 [How to: Delete Invoiced Blanket Purchase Orders](../SetupAndAdministration/how-to-delete-invoiced-blanket-purchase-orders.md)   
 [How to: Delete Invoiced Purchase Orders](../Purchasing/how-to-delete-invoiced-purchase-orders.md)