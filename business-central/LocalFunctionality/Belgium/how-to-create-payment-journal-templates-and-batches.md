---
title: Payment Journal Templates and Batches [BE]
description: In the Belgian version payment suggestions are generated and posted in payment journals. The payment journal is similar to the structure of other journal types.
author: brentholtorf
ms.topic: conceptual
ms.search.form: 256, 11300, 2000000, 2000001, 2000003, 2000020, 2000021, 2000022
ms.date: 06/25/2021
ms.author: bholtorf

---
# Create Payment Journal Templates and Batches in the Belgian Version

In [!INCLUDE[prod_short](../../includes/prod_short.md)], payment suggestions are generated and posted in payment journals. The structure of the payment journal is similar to the structure of other journal types. However, the payment journal contains some fields that are specific for processing payments. Before you can start generating payment suggestions, you have to set up a payment journal template and a payment journal batch.  

You can assign a specific page and a test report to each journal template. This way, you can manage your domestic and international payments from this adjusted page. The specified *source code* will be copied to all the journal lines that are created based on the journal template. The code is also copied to the entries when they are posted. This way, you can always see where an entry has been posted from.

If you assign a bank account to the payment journal template, the bank account will be inserted on all payment journal batches and payment journal lines that are created by using this template. By specifying a bank account for the journal template, you can reduce the time that is required for checking the payment suggestions.  

## To create a payment journal template  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Journal Templates**, and then choose the related link.  
2. Choose the **New** action.  
3. On the **Payment Journal Templates** page, fill in the fields.  

    [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

    > [!IMPORTANT]
    > If the **Page ID** and **Test Report ID** fields are not shown, you must add them through personalization. The fields must be filled in before you continue. For more information, see [Personalize Your Workspace](../../ui-personalization-user.md).
4. Repeat step 2 for any additional templates.

5. Choose the **OK** button.  

You can create multiple journal batches under each journal template. Several journals, each with its own name, can display the same page. For example, this can be practical if every user must have a dedicated journal.

## To add payment journal batches to the journal template  

1. On the **Payment Journal Templates** page, choose the **Batches** action.  
2. On the **Paym. Journal Batch** page, fill in the fields.  

    [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

    > [!NOTE]
    > To have the journal name update numerically, include a number in the journal batch name. For example, the name KBC1 will increment by one number with every posting to KBC2, KBC3, and so on.  

    Next, you can test the configuration. For more information, see [Test Electronic Payments](how-to-test-electronic-payments.md).  

## See Also

[Belgian Electronic Payments](belgian-electronic-payments.md)  
[Set Up Electronic Banking](how-to-set-up-electronic-banking.md)  
[Set Up IBLC-BLWI Transaction Codes](how-to-set-up-iblc-blwi-transaction-codes.md)  
[Make Journal Templates Mandatory](specify-journal-template-mandatory.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]