---
title: "How to: Set Up Tolerances"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "tolerance, setting up"
  - "payment tolerance, setting up"
  - "payment discounts, setting up tolerance"
ms.assetid: 8c6bb111-7466-42e4-9297-157c5c4380fe
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
  - "en-my"
  - "en-nz"
  - "en-ph"
  - "en-sg"
  - "en-zw"
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
# How to: Set Up Tolerances
Tolerance on days and amounts allows you to close an invoice even though the payment does not fully cover the amount on the invoice, whether this is because the due date for the payment discount has been exceeded, goods have been deducted or because of a minor error. This also applies to refunds and credit memos.  
  
 To set up tolerance you have to set up various tolerance accounts, specify both payment discount tolerance and payment tolerance posting methods and then run the **\($ B\_34 Change Payment Tolerance $\)** batch job.  
  
### To set up tolerances  
  
1.  In the **Search** box, enter **General Posting Setup**, and then choose the related link.  
  
2.  In the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**[\($ N\_314 General Posting Setup $\)](DynamicsNAV:////runpage?Page=314)** window, set up a debit and a credit sales payment tolerance account and a debit and a credit purchase payment tolerance account.  
  
3.  In the **Search** box, enter **Customer Posting Setup**, and then choose the related link.  
  
4.  In the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**[\($ N\_110 Customer Posting Groups $\)](DynamicsNAV:////runpage?Page=110)** window, set up a debit and a credit payment tolerance account.  
  
5.  In the **Search** box, enter **Vendor Posting Setup**, and then choose the related link.  
  
6.  In the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**[\($ N\_111 Vendor Posting Groups $\)](DynamicsNAV:////runpage?Page=111)** window, set up a debit and a credit payment tolerance account.  
  
7.  In the **Search** box, enter **General Ledger Setup**, and then choose the related link.  
  
8.  Open the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**[\($ N\_118 General Ledger Setup $\)](DynamicsNAV:////runpage?Page=118)** window.  
  
9. On the **Application** FastTab, fill in the **Pmt. Disc. Tolerance Posting**, **Payment Discount Grace Period** and **Payment Tolerance Posting** fields. For Help about a specific field, click the field and press F1.  
  
10. On the **Actions** tab, in the **Functions** group, choose **Change Payment Tolerance**.  
  
11. To run the **Change Payment Tolerance** batch job, fill in the **Payment Tolerance %** and **Max Payment Tolerance Amount** fields, and then choose the **OK** button. For Help about a specific field, click the field and press F1.  
  
> [!IMPORTANT]  
>  You have now set up tolerance for local currency only. If you want [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] to handle tolerance on payments, credit memos, and refunds in a foreign currency, you must run the **\($ B\_34 Change Payment Tolerance $\)** batch job. You must enter a currency in the **Currency Code** field.  
  
> [!NOTE]  
>  To deactivate tolerance for a customer or vendor, you must block tolerance on the relevant customer or vendor card.  
>   
>  If you want to get a payment tolerance warning every time that you post an application in the tolerance, you must activate the payment tolerance warning.  
>   
>  When you set up tolerance, [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] also checks if there are any open entries and calculates the tolerance for these entries.  
>   
>  For more information about how to block tolerances, see [How to: Block Payment Tolerances for a Customer or a Vendor](../Finance/how-to-block-payment-tolerances-for-a-customer-or-a-vendor.md). For more about how to activate the payment tolerance warning, see [How to: Enable or Disable Payment Tolerance Warnings](../Finance/how-to-enable-or-disable-payment-tolerance-warnings.md).  
  
## See Also  
 [Payment Tolerance and Payment Discount Tolerance](../Finance/payment-tolerance-and-payment-discount-tolerance.md)   
 [How to: Block Payment Tolerances for a Customer or a Vendor](../Finance/how-to-block-payment-tolerances-for-a-customer-or-a-vendor.md)   
 [How to: Enable or Disable Payment Tolerance Warnings](../Finance/how-to-enable-or-disable-payment-tolerance-warnings.md)   
 [\($ B\_34 Change Payment Tolerance $\)](../Topic/\($%20B_34%20Change%20Payment%20Tolerance%20$\).md)