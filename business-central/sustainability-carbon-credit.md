---
title: Working with Carbon Credits
description: Learn how to set up and purchase carbon credit.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, ESG, emission, GHG, CSRD, carbon, credit, CO2
ms.search.form: 
ms.date: 16/08/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: 
---

# Working with carbon credit  

When companies cannot reduce their emissions for various reasons, they can purchase carbon credits to offset their emissions. By buying carbon credits, a company can still emit the equivalent amount of gases while remaining carbon neutral. These credits are purchased from specialized providers, incentivizing emission reductions.  

In general, carbon credits are permits that allow the owner to emit a certain amount of carbon dioxide (CO₂) or other greenhouse gases (GHGs). One carbon credit typically represents the right to emit one metric ton of CO₂ or an equivalent amount of another GHG, so it is important to enable this option for some of organizations.  

## Set up the carbon credit  

Carbon Credit in Business Central can be set as the **Item**. To set upa the **Item** as a carbon credit, follow the steps:  
1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then select the related link. 
2. [Create new item as explanied](inventory-how-register-new-items.md).   
3. Once you have created item, select the **GHG Credit** field on the **Sustainability** FastTab and add the value of this carbon credit using the **Carbon Credit Per UOM** field.

> [!NOTE]
> **Carbon Credit Per UOM** represents the amount of CO₂ in the unit of measure configured in the **Emission Unit of Measure Code** in the **Sustainability Setup**. So, that means this is total value of carbon credit as amount of credited CO₂ per one **Base Unit of Measure** of used item.  

> [!NOTE]
> You can set up any type of item, whether it's inventory, service, or non-inventory, as a carbon credit.  

## Purchasing carbon credit 

### Purchase documents 

To start to work with purchase documents, follow these steps:

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon and:  
   1. Enter **Purchase Invoices** if you want to start with the invoice as a document type, and then select the related link.  
   2. Enter **Purchase Orders** if you want to start with the order as a document type, and then select the related link.   
2. Populate document header based on the following instruction [how to work with purchase documents](purchasing-how-record-purchases.md). 
3. Choose the item configure as a carbon credit in the **No.** field in the purchase document lines, and add appropriate **Quantity** and **Direct Unit Cost**. 
4. Add the **Sustanability Account No.** you would use for decreasing your carbon dioxide (CO₂) value. System will automatically populate the value in the **Emission CO2** field based on value you have configured in the **Carbon Credit Per UOM** field on the **Item** card.
5. Post the document.

> [!NOTE]
> Although carbon credit will decrease value in entries, you will see value in the **Emission CO2** as a positive amount. But, once when you post the document you will see value with the negative sign in the **Sustainability Ledger Entry** with the **GHG Credit** as a **Document Type**.  

### Sustainability journals 

To start to work with **Sustainability Journal** follow these steps:  

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Journal**, and then select the related link. 
2. On the **Sustainability Journal** page, enter as many lines as you plan to post in the same batch.  
3. Choose the **GHG Credit** in the **Document Type** field.    
4. In the **Account No.** field, you can select only non-blocked sustainability accounts where the **Direct Posting** field is selected and the **Accounting Type** field is set to **Posting**. The accounts must also be configured with a category and a subcategory. Choose appropriate account you will use for posting carbon credit.
5. Select **Manual Input** and enter value you want to poste as a carbon credit to the **Emission CO2** field.  
6. Post the journal.   

## See also

[Finance](finance.md)  
[Record sustainability entries](finance-sustainability-journal.md)  
[Sustainability management overview](finance-manage-sustainability.md)  
[Sustainability Setup](finance-sustainability-setup.md)   
[Chart of Sustainability Accounts and Ledger](finance-sustainability-accounts-ledger.md)  
[Ad-hoc analysis of sustainability data](ad-hoc-analysis-sustainability.md)    
[Sustainability reports and analytics in Business Central](sustainability-reports.md)   
[Sustainability API](/dynamics365/business-central/dev-itpro/api-sustainability/sustainability-api?toc=/dynamics365/business-central/toc.json)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
