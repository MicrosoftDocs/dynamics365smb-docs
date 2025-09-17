---
title: Export positive pay files
description: You can ensure your bank only clears validated checks and amounts by exporting a positive pay file that contains vendor and payment information.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: check, clearing
ms.search.form: 1231, 1232, 1233, 1234
ms.date: 12/16/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---

# Export a positive pay file

To make sure that your bank only clears validated checks and amounts, you can export a positive pay file. The file contains vendor information, check number, and payment amount, that you send to the bank. The information is used for reference when you process payments.

[!INCLUDE[prod_short](includes/prod_short.md)] is preconfigured to support positive pay files for Bank of America and City Bank.

## To set up a bank account for positive pay

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Bank Accounts**, and then choose the related link.
2. Open the card for the bank that you want to use positive pay for.
3. In the **Positive Pay Export Format** field, choose the format for your bank.
4. Close the page.

## To export a positive pay file

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Bank Accounts**, and then choose the related link.
2. Select the bank account that you want to export a positive pay file for.
3. Choose **Positive Pay Export** action.

    The **Positive Pay Export** page displays payments that were made for the bank account since the last upload date and time.
4. In the **Cutoff Upload Date** field, specify a date before which payments aren't included in the exported file.
5. Choose the **Export** action.
6. On the **Export File** page, choose the **Save** button, and then save the file to a convenient location.
7. Upload the file to your electronic bank site.
8. Write down or copy the confirmation number that is displayed when the file upload is successful.

## To view exported positive pay records

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Bank Accounts**, and then choose the related link.
2. Select the bank account that you want to view positive pay export records for.
3. Choose the **Positive Pay Entries** action.

    On the **Positive Pay Entries** page, you can see all the positive pay export records for the bank account.
4. In the **Confirmation Number** field, enter, for each export record, the confirmation number that you receive when the file upload to the bank is successful.
5. To view the related payment lines, choose the **Positive Pay Entry Details** action.

## To reexport positive pay files

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Bank Accounts**, and then choose the related link.
2. Select the bank account that you want to reexport positive pay files for.
3. Choose the **Positive Pay Entries** action.
4. Select the line for the positive pay export file that you want to reexport.
5. On the **Positive Pay Entries** page, choose the **Reexport Positive Pay to File** action.

## Related information

[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Work with General Journals](ui-work-general-journals.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
