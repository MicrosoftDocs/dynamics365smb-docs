---
title: Set Up Payment Classes [FR]
description: Learn how to configure payment classes, payment steps, statuses, and ledger information to manage operation types, such as bills of exchange, electronic payments, or checks.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: payment classes, payment steps, payment status, operation types, exchange bills, bills of exchange, ledger information, French version
ms.search.form: 10868, 10870, 10860, 10861, 10864, 10865, 10866, 10871, 10872, 10873, 10874, 10877, 10878, 10879, 10869, 10867, 10882, 10880
ms.date: 04/16/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up payment classes

To use payment management in the French version of [!INCLUDE [prod_short](../../includes/prod_short.md)], you must set up payment classes to define operation types, such as bills of exchange, electronic payments, or checks. Payment classes are defined in the **Payment Slip Setup** page.  

For each operation type, you then define the various statuses that the operation type can have, and you associate each status with steps to define how the payment changes from one status to another.  

## Steps to set up a payment class  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Slip Setup**, and then choose the relevant link.  
1. On the **Payment Slip Setup** page, choose the **New** action.  
1. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Enable**|Select to enable usage of the payment class.|  
    |**Code**|The unique identification code for the payment class.|  
    |**Name**|The payment class description.|  
    |**Header No. Series**|The number series code for the payment slip header.|  
    |**Line No. Series**|The number series code for the payment slip lines. If you leave this field blank, the number for each payment line is created based on the payment header number.|  
    |**Suggestions**|The type of payment proposals that can be created automatically on a payment slip.|  
    |**Unrealized VAT Reversal**|Specify the method to handle unrealized VAT.<br><br/> If you select **Application**, VAT is realized when you post the invoice application and payment application.<br><br/> If you select **Delayed**, you must define the payment step during which VAT must be realized, by selecting the **Realize VAT** field on the **Payment Step Card** page.|  
    |**SEPA Transfer Type**|Specify the SEPA export format, either **Credit Transfer** or **Direct Debit**. You specify the export format for SEPA transfers in payment steps for the payment class.|  

## Set up payment statuses for a payment class  

1. In the **Payment Slip Setup** page, select a payment class, and then choose the **Status** action.  
1. On the **Payment Status** page, choose the **New** action.  
1. Fill in the fields. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]  

    For example, the **RIB** field indicates that information about the Relevé d'Identité Bancaire (RIB) statement for the customer or vendor must be displayed in the payment lines. The RIB information includes the bank branch number, agency code, bank account number, bank name, RIB key, and key verification.

1. After defining the statuses you want for this payment class, return to the **Payment Slip Setup** page.  

Next, you must define steps for each payment class. The payment steps define how the payment moves from one state to the next, such as *Creation of documents*, *Documents created*, and *Creation of payments*.  

## Set up payment steps for a payment class

1. In the **Payment Slip Setup** page, select a payment class, and then choose the **Steps** action.  
1. In the **Payment Step** list, add the relevant steps for this payment class. For each step, you can enter a maximum of 50 alphanumeric characters.  
1. Choose the first step, and then choose the **Edit** action.  
1. On the **Payment Step Card** page, fill in the fields. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

> [!TIP]
> The **Previous Status** field defines the previous status, from which the step was last executed. The default value is 0, and the first step has 0 as the value of the **Previous Status** field.
>
> To make a step optional and potentially repeatable, set the previous status to be equal to the next status.
>
> The **Action Type**, **Export Type**, and **Export No.** fields play together. For example, for SEPA credit transfer files, set **Export Type** to **XMLport**, and then set the **Export No.** field to 1000. For SEPA direct debit files, specify **XMLport**, and then set the **Export No.** field to 1010.

If the action type of the payment step is **Ledger**, you must set up extra ledger information for the payment step.  

### Set up ledger information for a payment step  

1. On the **Payment Step Card** page for the payment step, choose the **Ledger** action.  
1. On the **Payment Step Ledger** page, choose the **New** action.  
1. Fill in the fields as appropriate. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

## Related information

- [Payment Management](payment-management.md)  
- [Set Up Payment Addresses](how-to-set-up-payment-addresses.md)  
- [Export or Import Payment Management Setup Parameters](how-to-export-or-import-payment-management-setup-parameters.md)  
- [Create Payment Slips](how-to-create-payment-slips.md)  
- [Post Payment Slips](how-to-post-payment-slips.md)  
- [Archive Payment Slips](how-to-archive-payment-slips.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
