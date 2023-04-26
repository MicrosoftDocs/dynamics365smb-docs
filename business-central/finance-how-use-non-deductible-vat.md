---
title: Use non-deductible VAT
description: This article explains how to use and report non-deductible VAT.
author: altotovi
ms.author: altotovi
ms.reviewer: 
ms.service: dynamics365-business-central
ms.topic: how-to
ms.topic: conceptual
ms.search.keywords: VAT, non-deductible, return, settlement
ms.search.form: 50, 51, 52, 161, 187, 317, 403, 6640, 9401
ms.date: 04/20/2023
ms.custom: bap-template

---

# Use non-deductible VAT  
This article provides information about how to use and report non-deductible VAT. 

## Create a purchase invoice with non-deductible VAT  

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and then select the related link. 
2. Select **New** to create a new purchase invoice and enter the appropriate information in the invoice header.   
3. In the **Lines** section, based on the VAT business posting group and the VAT product posting group where you configure non-deductible VAT, create a new line of any type. 
4. In the **Quantity** and **Direct Unit Cost** fields, enter the appropriate values.  
5. If you selected the **Show Non-Ded. VAT In Lines** check box on the **VAT Setup** page, the amounts in the **Non-Deductible VAT Base** and **Non-Deductible VAT Amount** fields are calculated based on the **Non-Deductible VAT %** field on the **VAT Posting Setup** page.  
6. Post the invoice.    

## To create purchase order with non-deductible VAT  

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders** and then select the related link. 
2. Select **New** to create a new purchase order and enter the appropriate information in the document header.   
3. In the **Lines** section, based on the VAT business posting group and the VAT product posting group where you configure non-deductible VAT, create a new line of any type.  
4.In the **Quantity** and **Direct Unit Cost** fields, enter the appropriate values.   
5. If you selected the **Show Non-Ded. VAT In Lines** check box on the **VAT Setup** page, the amounts in the **Non-Deductible VAT Base** and **Non-Deductible VAT Amount** fields are calculated based on the **Non-Deductible VAT %** field on the **VAT Posting Setup** page. 
6. Post the purchase order.   

## Rounding VAT amounts before posting documents  

If VAT amounts aren't rounded the same way in your environment as they are in the external accounting system (the original invoice document), you can adjust the VAT amount before you post the document. To do this, complete the following steps before posting.

1. On the ribbon, select **Statistic**.  
2. If you are working with the purchase invoice:

    1. Select the **VAT Amount** or **Non-Deductible VAT Amount** in the **Lines** FastTab. 
    2. Populate the values you need from your original document, and then close the **Purchase Invoice Statistics** page.  

3.	If you are working with the purchase order: 

    1. On the **Invoicing** FastTab, select **No. of Tax Lines** to open the **VAT Amounts Lines** page. 
    2. Select the **VAT Amount** or **Non-Deductible VAT Amount** you want to correct.
    3. Enter the values you need from your original document, close the **VAT Amount lines** page, and then close the **Purchase Order Statistics** page.

To use adjustments of VAT amounts, you must enable the adjustments by entering the value in the **Max. VAT Difference Allowed** field on the **General Ledger Setup** and then selecting **Allow VAT Difference**. The value you enter is the maximum allowed VAT amount for correction on the **General Ledger Setup** page and select the **Allow VAT Difference** field on the **Purchases & Payables Setup** page.  

You can adjust the values in the **VAT Amount** and **Non-Deductible VAT Amount** fields. The **Deductible VAT Amount** field is the result of these two values. You can't enter a bigger amount in the **Non-Deductible VAT Amount** field than the **VAT Amount** field. The amount entered in the **Max. VAT Difference Allowed** field on the **General Ledger Setup** page works independently for deductible and non-deductible VAT amounts on statistic pages when you want to adjust VAT amounts. 

> [!IMPORTANT]  
> You can't use non-deductible VAT on the prepayment invoices.   


## See also

[Financial Management](finance.md)  
[Set Up Calculations and Posting Methods for Value-Added Tax](finance-setup-vat.md)  
[Set up Non-deductible VAT](finance-setup-nondeductible-vat.md) 
[Report VAT to Tax Authorities](finance-how-report-vat.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)   

[!INCLUDE[footer-include](includes/footer-banner.md)]  
