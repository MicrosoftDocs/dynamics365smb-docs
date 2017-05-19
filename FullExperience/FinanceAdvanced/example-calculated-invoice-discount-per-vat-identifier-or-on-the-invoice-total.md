---
title: "Example - Calculated Invoice Discount per VAT Identifier or on the  Invoice Total"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 30f83ea4-bdd1-4f86-9c28-3d5ceceb9253
caps.latest.revision: 3
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
---
# Example - Calculated Invoice Discount per VAT Identifier or on the  Invoice Total
The following example is based on an invoice with two lines with different VAT Prod. Posting Groups, but with the same amount. The VAT Prod. Posting Groups are 10% and 25%, the line amounts are 1.10 LCY and the invoice discount is 5 %.  
  
 Without a check mark in the Cal. Inv. Disc. per VAT ID field, the program calculates the invoice discount on the basis of the subtotal:  
  
||||||  
|-|-|-|-|-|  
|Subtotal|5 % Invoice Discount|Total Excl. VAT|VAT|Total Incl. VAT|  
|2.20|0.11|2.09|0.36|2.45|  
  
 The VAT specifications are:  
  
||||||  
|-|-|-|-|-|  
|VAT %|Line Amount|Invoice Discount Amount|VAT Base|VAT Amount|  
|10|1.10|0.06|1.04|0.10|  
|25|1.10|0.05|1.05|0.26|  
  
 This method results in one line being posted to the invoice discount account in the chart of accounts.  
  
 With a check mark in the Cal. Inv. Disc. per VAT ID field, the program calculates the invoice discount on the basis of each VAT specification line:  
  
||||||  
|-|-|-|-|-|  
|Subtotal|5 % Invoice Discount|Total Excl. VAT|VAT|Total Incl. VAT|  
|2.20|0.12|2.08|0.36|2.44|  
  
 The VAT specifications are:  
  
||||||  
|-|-|-|-|-|  
|VAT %|Line Amount|Invoice Discount Amount|VAT Base|VAT Amount|  
|10|1.10|0.06|1.04|0.10|  
|25|1.10|0.06|1.04|0.26|  
  
 This method results in two lines being posted to the invoice discount account in the chart of accounts.  
  
 Note that in this case the different methods only led to different invoice discounts, but in other cases the different invoice discounts may cause the VAT amount to change.