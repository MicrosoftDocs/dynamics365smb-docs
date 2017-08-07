---
    title: How to: Set Up Sales Tax Groups | Microsoft Docs
    description: A tax group represents a group of inventory items or resources that are subject to identical tax terms. Examples of typical tax groups include food items, medicine and medical supplies, and automobile fuel. These groups are usually determined by criteria set up by tax authorities.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# How to: Set Up Sales Tax Groups
A tax group represents a group of inventory items or resources that are subject to identical tax terms. Examples of typical tax groups include food items, medicine and medical supplies, and automobile fuel. These groups are usually determined by criteria set up by tax authorities.  
  
 Tax group codes must be assigned on the **Resource**, **Item**, and **G/L Account** cards. Tax area codes must be assigned on the **Customer**, **Location**, and **Company Information** cards. For more information, see [How to: Enter Company Information](how-to-enter-company-information.md).  
  
### To set up a sales tax group  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Tax Groups**, and then choose the related link.  
  
2.  In the **Tax Groups** window, on the **Home** tab, in the **New** group, choose **New**.  
  
3.  In the **New - Tax Groups** window, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|The code that you want to assign to the tax group. You can enter up to 10 alphanumeric characters. For example, you can enter the tax group code MEDICINE for medicines and medical supplies.|  
    |**Description**|The description of the tax group.|  
  
4.  Choose the **OK** button.  
  
 The tax group is assigned on the **Invoicing** FastTab on the **Item** and **Resource** cards. In general ledger accounts, the tax group is assigned on the **Posting** FastTab. For more information, see [How to: Register New Products](how-to-set-up-general-ledger-accounts-in-the-chart-of-accounts-window.md).  
  
## See Also  
 Sales Tax Group List   
 [How to: Register New Products](how-to-register-new-products.md)   
 [How to: Set Up a Resource](how-to-set-up-a-resource.md)   
 [How to: Set Up General Ledger Accounts in the Chart of Accounts Window](how-to-set-up-general-ledger-accounts-in-the-chart-of-accounts-window.md)   
 [How to: Enter Company Information](how-to-enter-company-information.md)   
 [How to: Set Up Sales Tax](how-to-set-up-sales-tax.md)   
 [How to: Set Up Sales Tax Details](how-to-set-up-sales-tax-details.md)   
 [How to: Set Up Sales Tax Jurisdictions](how-to-set-up-sales-tax-jurisdictions.md)   
 [How to: Set Up Unrealized Sales Tax and Sales Payment Discounts](how-to-set-up-unrealized-sales-tax-and-sales-payment-discounts.md)   
 [How to: Set Up Use Tax and Purchase Tax](how-to-set-up-use-tax-and-purchase-tax.md)