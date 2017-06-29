---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
  
 Tax group codes must be assigned on the **Resource**, **Item**, and **G\/L Account** cards. Tax area codes must be assigned on the **Customer**, **Location**, and **Company Information** cards. For more information, see [How to: Enter Company Information](../../Finance/how-to-enter-company-information.md).  
  
### To set up a sales tax group  
  
1.  In the **Search** box, enter **Tax Groups**, and then choose the related link.  
  
2.  In the **Tax Groups** window, on the **Home** tab, in the **New** group, choose **New**.  
  
3.  In the **New - Tax Groups** window, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Code**|The code that you want to assign to the tax group. You can enter up to 10 alphanumeric characters. For example, you can enter the tax group code MEDICINE for medicines and medical supplies.|  
    |**Description**|The description of the tax group.|  
  
4.  Choose the **OK** button.  
  
 The tax group is assigned on the **Invoicing** FastTab on the **Item** and **Resource** cards. In general ledger accounts, the tax group is assigned on the **Posting** FastTab. For more information, see [How to: Register New Products](../../DesignAndEngineering/how-to-register-new-products.md), [How to: Set Up a Resource](../../ResourcePlanning/how-to-set-up-a-resource.md), and [How to: Set Up General Ledger Accounts in the Chart of Accounts Window](../../Finance/how-to-set-up-general-ledger-accounts-in-the-chart-of-accounts-window.md).  
  
## See Also  
 Sales Tax Group List   
 [How to: Register New Products](../../DesignAndEngineering/how-to-register-new-products.md)   
 [How to: Set Up a Resource](../../ResourcePlanning/how-to-set-up-a-resource.md)   
 [How to: Set Up General Ledger Accounts in the Chart of Accounts Window](../../Finance/how-to-set-up-general-ledger-accounts-in-the-chart-of-accounts-window.md)   
 [How to: Enter Company Information](../../Finance/how-to-enter-company-information.md)   
 [How to: Set Up Sales Tax](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-set-up-sales-tax.md)   
 [How to: Set Up Sales Tax Details](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-set-up-sales-tax-details.md)   
 [How to: Set Up Sales Tax Jurisdictions](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-set-up-sales-tax-jurisdictions.md)   
 [How to: Set Up Unrealized Sales Tax and Sales Payment Discounts](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-set-up-unrealized-sales-tax-and-sales-payment-discounts.md)   
 [How to: Set Up Use Tax and Purchase Tax](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-set-up-use-tax-and-purchase-tax.md)