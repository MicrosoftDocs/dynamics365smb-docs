---
title: Set up OCR payments [NO]
description: You can process electronic payments from customers according to a predefined payment ID in the Norwegian version. This is often referred to as an optical character recognition (OCR) payment.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.form: 15000100
ms.date: 12/07/2023
ms.author: bholtorf
---
# Set up OCR payments
You can process electronic payments from customers according to a predefined payment ID. This is often referred to as an optical character recognition (OCR) payment. The payment ID is used with electronic payment transactions. Customers can refer to this ID when they make payments. The payment ID is also used to identify imported payment transactions and automatically apply imported payment data.  

## To set up OCR payments  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **OCR Setup**, and then choose the related link.  
2.  On the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Format**|Select an OCR payment file format. Formats include **BBS** and **Data Dialog**.|  
    |**FileName**|Enter the full path of the OCR payment file.|  
    |**Delete Return File**|Select to rename the file after import and prevent the file from being imported more than one time.|  

3.  On the **Gen. Ledger** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Bal. Account Type**|Select a balance account type. Balance account types include **Gen. Ledg. Account** and **Bank Account**.|  
    |**Bal. Account No.**|Select a balance account number.|  
    |**Max. Divergence**|Enter a maximum divergence value. If the divergence on a payment is less than or equal to the value entered, the divergence amount is automatically posted. Otherwise, the divergence isn't automatically posted. In both situations, a warning is displayed in the cash receipt journal when importing OCR Giro payments.|  
    |**Divergence Account No.**|Enter the divergence account number that receives posting.|  
    |**Journal Template Name**|Select the name of the journal template that should receive the imported OCR Giro payments.|  
    |**Journal Name**|Select the name of the journal that should receive the imported OCR Giro payments.<br /><br /> If the **Journal Template Name** and **Journal Name** fields are blank, you can import OCR Giro payments in any journal. Otherwise, you must import OCR Giro payments in the journal that is specified.|  

4.  Choose the **OK** button.  

> [!NOTE]  
>  OCR payments can only be posted to cash receipt journals when the **Force Doc. Balance** field has been cleared in the **Gen. Journal Template** table. For more information, see Gen. Journal Template.  

## See also  
 [Electronic Banking in Norway](electronic-banking-in-norway.md)   
 [Set Up KID Numbers on Sales Documents](how-to-set-up-kid-numbers-on-sales-documents.md)   
 [Import and Post OCR Payments](how-to-import-and-post-ocr-payments.md)   
 [Print the OCR Journal - Test Report](how-to-print-the-ocr-journal-test-report.md)   
 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]