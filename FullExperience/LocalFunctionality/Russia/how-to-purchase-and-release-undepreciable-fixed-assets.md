---
title: "How to: Purchase and Release Undepreciable Fixed Assets"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "fixed assets, releasing"
ms.assetid: ebfdc652-8b98-4105-8607-8ba412912a06
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# How to: Purchase and Release Undepreciable Fixed Assets
After posting the fixed assets, you must create a fixed asset release act of the fixed asset and post it. If you open the **Fixed Asset Card** window for that fixed asset, you can see that in the corresponding lines, the depreciation for operation contains a zero, and the book value also contains a zero.  
  
 The posting of the fixed asset release act results in two fixed asset operations in the operation depreciation book. The first is the fixed asset operation with the acquisition cost and quantity posted. The second is the fixed asset operation with the acquisition on disposal posted with the same cost and quantity, but with the sign reversed for both. The fixed asset is released and disposed in amount and quantity in this depreciation book, which is integrated with the general ledger. The book value and quantity of the fixed asset are zero, and there is no depreciation operation. According to this depreciation book, the fixed asset is fully disposed without depreciation.  
  
 In the **Fixed Asset Card** window, a new line automatically opens with the quantity depreciation book. The quantity, acquisition cost, and book value in this fixed asset depreciation book are equal to the corresponding amount and quantity in the purchase order. This book shows the existence of this fixed asset in terms of the quantity and amount. It is not integrated with the general ledger, so future operations will not influence financial accounting.  
  
 The fixed asset is disposed financially in full at the time of release, but can be operated in quantities and amounts.  
  
 The following procedures show how to create a purchase order and a release order for undepreciable fixed assets.  
  
### To create a purchase order for an undepreciable fixed asset  
  
1.  In the **Search** box, enter **Purchase Order**, and then choose the related link.  
  
2.  In the **Purchase Order** window, on the **Home** tab, in the **Posting** group, choose **Post**.  
  
3.  Choose the **OK** button.  
  
### To create a release order for an undepreciable fixed asset  
  
1.  In the **Search** box, enter **FA Releases**, and then choose the related link.  
  
2.  Select a release, and in the **FA Release Act** window, and on the **Home** tab, in the **Posting** group, choose **Post**.  
  
3.  Choose the **OK** button.  
  
## See Also  
 [How to: Set Up a Quantity Book](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-set-up-a-quantity-book.md)   
 [Undepreciable Fixed Assets](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/undepreciable-fixed-assets.md)   
 [How to: Set Up Undepreciable Fixed Assets](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-set-up-undepreciable-fixed-assets.md)   
 [Purchase Order](../Topic/\($%20N_50%20Purchase%20Order%20$\).md)