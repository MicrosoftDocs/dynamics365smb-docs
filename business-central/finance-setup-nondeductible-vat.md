---
title: Set up non-deductible VAT
description: This article provides information about how to configure non-deductible VAT in Dynamics 365 Business Centran.
author: altotovi
ms.author: altotovi
ms.reviewer: 
ms.service: dynamics365-business-central
ms.topic: how-to
ms.search.keywords: VAT, non-deductible, setup
ms.search.form: 187, 472, 473
ms.date: 04/26/2023
ms.custom: bap-template

---

# Set up non-deductible VAT  

Non-deductible Value added tax (VAT) is the VAT payable by a purchaser that isn't deductible from the purchaser's own VAT liability. Companies can usually recover VAT on the purchase of goods and services related to their business activities. However, there are some situations where a business incurs VAT that isn't deductible. These situations are generally related to the local regulations and may differ from country to country. However, the model of using non-deductible or partly deducible VAT is similar. 
You can use proportional VAT to calculate VAT when there is deductible and non-deductible VAT. In general, VAT can't be deducted for some purchases because of: 

- The type of goods or services purchased – VAT is fully or partially non-deductible by provision of the law on goods like cars, mobile phones, food purchased at restaurants, and more.  
- Partially deductible pro-rated VAT – VAT is pro-rated according to the ratio between the sales operations for which VAT is owed, and all operations performed. VAT exceeding this ratio can't be deducted.  

Because knowin where and how an item is used can be difficult, you must contact the local tax authorities in your country to determine whether a specified percentage of the VAT is deductible based on historical data.  


## Use non-deductible VAT  

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Setup**, and then select the related link.  
2. Mark the **Enable Non-Deductible VAT** check box.    

    > [!IMPORTANT]  
    > After you enable non-deductible VAT, you can't turn it off as the feature may include changes to data and may initiate an upgrade of some database tables. Microsoft strongly recommends that you first enable and test this feature on the sandbox before you enable this on the production environment.  

3. Next, configure how the system will treat non-deductible VAT values.  
    
    1. In the **Use For Item Cost** field, specify if the non-deductible VAT must be added to the item cost when you purchase items. Otherwise, the non-deductible VAT won't have an influence on the item cost, and the full amount will be recorded on the general ledger level only. 
    2. Select the **Use For Fixed Asset Cost** check box to add the non-deductible VAT to the fixed asset cost when you purchase new fixed assets. Otherwise, the non-deductible VAT won't have an influence on the fixed asset cost, and the full amount will be recorded on the general ledger level only.  
    3. Select the **Use For Job Cost** check box to specify that the non-deductible VAT must be added to the job cost when you purchase item for the job. Otherwise, the non-deductible VAT won't have an influence on the job cost, and the full amount will be recorded on the general ledger level only.  
    4. Select the **Show Non-Ded. VAT In Lines** check box to specify if the non-deductible VAT must be shown in document lines pages for easier manipulation with VAT amounts.   

## Use the non-deductible VAT percentage  

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Posting Setup**, and then select the related link.   
2. On the **VAT Posting Setup** page, fill in the fields as described in the following table:  

    |Field|Description|  
    |---------------------------------|---------------------------------------|   
    |**Allow Non-Deductible VAT**| Specify whether the non-deductible VAT is considered for this particular combination of VAT business posting group and the VAT product posting group. | 
    |**Non-Deductible VAT %**| Specify the percentage of the transaction amount to which VAT isn't applied. | 
    |**Non- Deductible Purchase VAT Account**| Specify the account associated with the VAT amount that isn't deducted because of the type of goods or services purchased. | 

    > [!NOTE]  
    > You can either keep **Non-Deductible Purchase VAT Account** blank or set **G/L Account** to have G/L entries with the dedicated account instead of the sales/purchase account.  

3. Select **OK**.  

> [!NOTE]  
> You can't use **Unrealized VAT** with **Non-deductible VAT**.   
> 
> Don't use the same **VAT identifier** for **Normal VAT** with zero **Non-Deductible VAT %** and **Normal VAT** with non-zero **Non-Deductible VAT %** because it will lead to an incorrect calculation of the total **Non-Deductible VAT Amount**.  


## See also

[Financial Management](finance.md)  
[Set Up Calculations and Posting Methods for Value-Added Tax](finance-setup-vat.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
