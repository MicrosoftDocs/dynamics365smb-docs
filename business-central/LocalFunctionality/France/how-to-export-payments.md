---
title: How to Export Payments
description: Use the Payment Management module to export your payments electronically via a text file or XMLport.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: payment management module, payment export, French version
ms.date: 10/08/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Export payments

The Payment Management module allows you to export your payments electronically via a text file or XMLport.  

## Process to export payments  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Slip Setup**, and then choose the relevant link.  
1. On the **Payment Class** page, select a payment class, and then choose the **Steps** action.  
1. On the **Payment Step** page, fill in the **Name** field.  
1. Choose the **Edit** action to open.  
1. On the **Payment Step Card** page, fill in the fields.  
1. In the **Action Type** field, select the **File** option, and then in the **Export Type** field, select the **Report** or the **XMLport** action.  
1. In the **Export No.** field, specify the object that will export the payments.  

The next time you make a payment that's based on this payment step, the payments will be exported to a file as specified.  

## Related information

- [Set up payment classes](how-to-set-up-payment-classes.md)  
- [Set up payment steps for a payment class](how-to-set-up-payment-classes.md#set-up-payment-steps-for-a-payment-class)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
