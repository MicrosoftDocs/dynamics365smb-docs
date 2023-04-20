---
title: How to use Non-deductible VAT
description: Business Central supports non-deductible VAT and you can find details how to use and report it here.
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

# How to use non-deductible VAT  

## To create purchase invoice with non-deductible VAT  

1.	Choose the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices** and then choose the related link. 
2.	Create new **Purchase Invoice** using the **New** action and populate information in document header.   
3.	In the **Lines**, create a new line with any **Type** based on **VAT Business Posting Group** and **VAT Product Posting Group** where you have configured non-deductible VAT. 
4.	Fill in the **Quantity** and **Direct Unit Cost**.  
5.	If you selected the **Show Non-Ded. VAT In Lines** field in the **VAT Setup** page, you will see amounts in **Non-Deductible VAT Base** and **Non-Deductible VAT Amount** in the **Lines**, calculated based on the **Non-Deductible VAT %** field in the **VAT Posting Setup** page.  
6.	Post the document.    

## To create purchase order with non-deductible VAT  

1.	Choose the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders** and then choose the related link. 
2.	Create new **Purchase Order** using the **New** action and populate information in document header.   
3.	In the **Lines**, create a new line with any **Type** based on **VAT Business Posting Group** and **VAT Product Posting Group** where you have configured non-deductible VAT.  
4.	Fill in the **Quantity** and **Direct Unit Cost**.   
5.	If you selected the **Show Non-Ded. VAT In Lines** field in the **VAT Setup** page, you will see amounts in **Non-Deductible VAT Base** and **Non-Deductible VAT Amount** in the **Lines**, calculated based on the **Non-Deductible VAT %** field in the **VAT Posting Setup** page. 
6.	Post the document.   

## Rounding VAT Amounts before posting documents  

If VAT amounts are not rounded the same way as in the external accounting system (the original invoice document), you can adjust VAT amount before posting document. To do this, before posting document:

1.	Select the **Statistic** action from ribbon.  
2.	If you are working with the **Purchase Invoice**, 
    1.	Select the **VAT Amount** or **Non-Deductible VAT Amount** in the **Lines** FastTab, 
    2.	Populate the values you need from your original document,   
    3.	Close the **Purchase Invoice Statistics** page.  
3.	If you are working with the **Purchase Order**,   
    1.	Expand the **Invoicing** FastTab,  
    2.	Select the **No. of Tax Lines** field on the **Invoicing** FastTab to open the **VAT Amounts Lines** page,  
    3.	Select the **VAT Amount** or **Non-Deductible VAT Amount** you want to correct, 
    4.	Populate the values you need from your original document, 
    5.	Close the **VAT Amount Lines** page,   
    6.	Close the **Purchase Order Statistics** page. 

> [!NOTE]  
> If you want to use adjustments of VAT amounts, you must enable it entering the value in the **Max. VAT Difference Allowed** field as maximum allowed VAT amount for correction on the **General Ledger Setup** page and select the **Allow VAT Difference** field on the **Purchases & Payables Setup** page.  

> [!NOTE]  
> You can adjust the **VAT Amount** and **Non-Deductible VAT Amount**; the **Deductible VAT Amount** field will be the result of these two values. You cannot enter a bigger amount in the **Non-Deductible VAT Amount** from **VAT Amount**. Amount entered in the **Max. VAT Difference Allowed** field on the **General Ledger Setup** page works independently for deductible and non-deductible VAT amounts on statistic pages when you want to adjust VAT amounts. 

> [!IMPORTANT]  
> You cannot use non-deductible VAT on the prepayment invoices.   


## See also

[Financial Management](finance.md)  
[Set Up Calculations and Posting Methods for Value-Added Tax](finance-setup-vat.md)  
[Set up Non-deductible VAT](finance-setup-nondeductible-vat.md) 
[Report VAT to Tax Authorities](finance-how-report-vat.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)   

[!INCLUDE[footer-include](includes/footer-banner.md)]  
