---
title: Set up Non-deductible VAT
description: Business Central supports non-deductible VAT and you can find details how to configure it here.
author: altotovi
ms.author: altotovi
ms.reviewer: 
ms.service: dynamics365-business-central
ms.topic: how-to
ms.topic: conceptual
ms.search.keywords: VAT, non-deductible, setup
ms.search.form: 187, 472, 473
ms.date: 04/13/2023
ms.custom: bap-template

---

# Set up Non-deductible VAT  

Non-deductible VAT (value added tax) is the VAT payable by a purchaser which is not deductible from his own VAT liability, if any. Companies can usually recover VAT on the purchase of goods and services relating to their business activities. However, there are some situations where a business incurs VAT which is not deductible. These situations are in general related to the local regulations and may differ from country to country, but the model of using non-deductible or partly deducible VAT is similar. 
Business Central allows you to use proportional VAT to calculate VAT when there is both deductible and non-deductible VAT. In general, VAT cannot be deducted for some purchases because of: 

- The type of goods or services purchased – VAT is fully or partially non-deductible by provision of the law on goods like cars, mobile phones, food purchased at restaurants, and so on.  
- Partially deductible pro-rated VAT – VAT is pro-rated according to the ratio between sales operations for which VAT is owed, and all operations performed. VAT exceeding this ratio cannot be deducted.  

But because it is difficult to know where and how an item is used, you will have to contact the local tax authorities in your country to determine whether a specified percentage of the VAT is deductible based on historical data.  


## To set up usage of the non-deductible VAT  

1.	Choose the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Setup**, and then choose the related link.  
2.	Select the **Enable Non-Deductible VAT** field to specify if the Non-Deductible VAT feature is enabled.    

    > [!IMPORTANT]  
    > Keep in mind after you enable non-deductible VAT, you cannot turn it off again because the feature may include changes to data ana may initiate an upgrade of some database tables. Microsoft strongly recommends that you first enable and test this feature on the sandbox before doing this on the production environment.  

3.	You can additionally configure how the system will treat non-deductible VAT values:  
    1. Select the **Use For Item Cost** field, to specify if the non-deductible VAT must be added to the item cost when you purchase items. Otherwise, the non-deductible VAT will not have an influence on the item cost, and the full amount will be recorded on the general ledger level only. 
    2. Select the **Use For Fixed Asset Cost** field, to specify if the non-deductible VAT must be added to the fixed asset cost when you purchase new fixed assets. Otherwise, the non-deductible VAT will not have an influence on the fixed asset cost, and the full amount will be recorded on the general ledger level only.  
    3. Select the **Use For Job Cost** field, to specify if the non-deductible VAT must be added to the job cost when you purchase item for the job. Otherwise, the non-deductible VAT will not have an influence on the job cost, and the full amount will be recorded on the general ledger level only.  
    4. Select the **Show Non-Ded. VAT In Lines** field, to specify if the non-deductible VAT must be shown in document lines pages for easier manipulation with VAT amounts.   

## To set up the non-deductible VAT percentage  

1.	Choose the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Posting Setup**, and then choose the related link.   
2.	On the **VAT Posting Setup** page, fill in the fields as described in the following table:  

    |Field|Description|  
    |---------------------------------|---------------------------------------|   
    |**Allow Non-Deductible VAT**| Specifies whether the Non-Deductible VAT is considered for this particular combination of VAT business posting group and VAT product posting group. | 
    |**Non-Deductible VAT %**| Specifies the percentage of the transaction amount to which VAT is not applied. | 
    |**Non- Deductible Purchase VAT Account**| Specifies the account associated with the VAT amount that is not deducted due to the type of goods or services purchased. | 

    > [!NOTE]  
    > You can either keep **Non-Deductible Purchase VAT Account** blank or set **G/L Account** to have G/L entries with the dedicated account instead of the sales/purchase account.  

3.	Choose the **OK** button.  

> [!NOTE]  
> You cannot configure to use **Unrealized VAT** together with the **Non-deductible VAT**.   

> [!NOTE]  
> It is not possible to use the same **VAT identifier** for **Normal VAT** with zero **Non-Deductible VAT %** and **Normal VAT** with non-zero **Non-Deductible VAT %** because it will lead to incorrect calculation of the total **Non-Deductible VAT Amount**.  


## See also

[Financial Management](finance.md)  
[Set Up Calculations and Posting Methods for Value-Added Tax](finance-setup-vat.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
