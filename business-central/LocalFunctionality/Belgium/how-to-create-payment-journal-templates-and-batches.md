---
title: How to Create Payment Journal Templates and Batches
description: In the Belgian version of Business Central, payment suggestions are generated and posted in payment journals. The structure of the payment journal is similar to the structure of other journal types.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 04/01/2020
ms.author: sgroespe

---
# Create Payment Journal Templates and Batches
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], payment suggestions are generated and posted in payment journals. The structure of the payment journal is similar to the structure of other journal types. However, the payment journal contains some fields that are specific for processing payments. Before you can start generating payment suggestions, you have to set up a payment journal template and a payment journal batch.  

If you assign a bank account to the payment journal template, the bank account will be inserted on all payment journal batches and payment journal lines that are created by using this template. By specifying a bank account for the journal template, you can reduce the time that is required for checking the payment suggestions.  

## To create a payment journal template  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Journal Templates**, and then choose the related link.  
2.  Choose the **New** action.  
3.  On the **EB Payment Journal Templates** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Name**|Enter the unique name for the payment journal template that you are creating.|  
    |**Description**|Enter a description of the payment journal template.|  
    |**Bank Account**|Select the bank account that will be used when you create a payment suggestion.|  
    |**Reason Code**|Select the reason code that will be used on all the journal batches and lines that are created by using the journal template. If you want to use a different reason code on a journal line, you can manually change it.|  
    |**Source Code**|Select the source code that will be used on all the journal batches and lines that are created by using the journal template.|  

4.  Choose the **OK** button.  

## To add payment journal batches to the journal template  

1.  On the **Payment Journal Templates** page, choose the **Batches** action.  
2.  On the **Paym. Journal Batch** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Journal Template Name**|Specify a journal template name for the payment journal batch.|  
    |**Name**|Enter a unique name for the journal batch.<br /><br /> **NOTE:** To have the journal name update numerically, include a number in the journal batch name. For example, the name KBC1 will increment by one number with every posting to KBC2, KBC3, and so on.|  
    |**Description**|Enter a description for the journal batch.|  
    |**Reason Code**|Specifies the reason code that is linked to this journal batch.|  
    |**Status**|Specifies the status of the batch.|  

3.  Choose the **OK** button.  

## See Also  
 [Belgian Electronic Payments](belgian-electronic-payments.md)   
 [Set Up Electronic Banking](how-to-set-up-electronic-banking.md)   
 [Set Up IBLC-BLWI Transaction Codes](how-to-set-up-iblc-blwi-transaction-codes.md)
