---
title: Set Up Bank Reference Files (FI)
description: To process electronic payments in the Finnish version, you must first set up bank reference files to determine how payment data should be imported or exported.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.form: 32000000, 32000001, 32000002, 32000004, 32000005, 32000006
ms.date: 04/01/2021
ms.author: bholtorf

---
# Set Up Bank Reference Files in the Finnish Version
To process electronic payments, you must first set up bank reference files to determine how payment data should be imported or exported.  

## To set up a bank reference file  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Reference File Setup**, and then choose the related link.  
2.  On the **General** FastTab, fill in the fields as described in the following table.  

|Field|Description|  
|---------------------------------|---------------------------------------|  
|**No.**|Specifies a bank account code.|  
|**Inform. of Appl. Cr. Memos**|Select to display credits applied to invoices on the payment recipient's account statement.|  

3.  On the **Foreign Payments** FastTab, fill in the fields as described in the following table.  

|Field|Description|  
|---------------------------------|---------------------------------------|  
|**Due Date Handling**|Select how due date processing should be applied to foreign payments.<br /><br /> **Batch** – All payments in the file receive the same payment date.<br /><br /> –or–<br /><br /> **Transaction** – Each payment in the file receives a transaction-specific payment date. Contact your bank to determine whether this setting should be used.|  
|**Default Service Fee Code**|Select a default service fee code for foreign banks.|  
|**Default Payment Method**|Select a default payment method for foreign payments.|  
|**Exchange Rate Contract No.**|Enter the exchange rate contract number.|  
|**Allow Comb. Foreign Pmts.**|Select to combine all foreign payments made to one recipient in one day from the same bank account.|  

4.  On the **SEPA** FastTab, fill in the fields as described in the following table.  

|Field|Description|  
|---------------------------------|---------------------------------------|  
|**Bank Party ID**|Enter a SEPA bank party ID. **Note:**  This field is only used for the SEPA pain.001.001.02 standard.|  
|**File Name**|Enter the full path of the SEPA payment file. **Note:**  This field is only used for the SEPA pain.001.001.02 standard.|  

> [!IMPORTANT]  
>  To export vendor payments using the SEPA standard, you must fill the **Payment Export Format** field on the **Bank Account Card** page.  

5.  Choose the **OK** button.  

## See Also  
 [Electronic Banking in Finland](electronic-banking-in-finland.md)   
 [Generate Payment Files](how-to-generate-payment-files.md)   
 [Disregard Payment Discounts](how-to-disregard-payment-discounts.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]