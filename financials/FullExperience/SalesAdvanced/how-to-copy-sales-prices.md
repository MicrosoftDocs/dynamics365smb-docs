---
title: "How to: Copy Sales Prices"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "sales prices, copy"
ms.assetid: 74bb262c-3648-4e94-87c0-7c956d37c9a8
caps.latest.revision: 5
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
---
# How to: Copy Sales Prices
If you want to copy sales prices, such as an individual customer's sales prices to use for a customer price group, you must run the **Suggest Sales Price on Wksh.** batch job.  
  
 You find the batch job in the **Sales Price Worksheet** window.  
  
### To copy sales prices  
  
1.  In the **Search** box, enter **\($ N\_7023 Sales Price Worksheet $\)**, and then choose the related link.  
  
2.  On the **Actions** tab, in the **Functions** group, choose **Suggest Sales Price on Wksh.**  
  
3.  On the **Sales Prices** FastTab, fill in the **Sales Type** and **Sales Code** fields with the original sales prices you want to copy.  
  
4.  In the top section of the request window, fill in the **Sales Type** and **Sales Code** with the type and name you want the sales prices copied to.  
  
5.  If you want the batch job to create new prices, select the **Create New Prices** field.  
  
6.  Choose the **OK** button to fill in the lines on the **Sales Price Worksheet** window with the suggested new prices, indicating that they are valid for the selected **Sales Type**.  
  
> [!NOTE]  
>  This batch job only creates suggestions and it does not implement the suggested changes. If you are satisfied with the suggestions and want to implement them, that is insert them in the **Sales Prices** table, you can use the **Implement Price Changes** batch job, which is found on the **Actions** tab, in the **Functions** group, in the **Sales Price Worksheet** window.  
  
## See Also  
 [\($ N\_7002 Sales Prices $\)](../Topic/\($%20N_7002%20Sales%20Prices%20$\).md)   
 [\($ N\_7023 Sales Price Worksheet $\)](../Topic/\($%20N_7023%20Sales%20Price%20Worksheet%20$\).md)   
 [How to: Create Sales Prices for a Customer](../DesignAndEngineering/how-to-create-sales-prices-for-a-customer.md)