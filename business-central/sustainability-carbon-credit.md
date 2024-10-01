---
title: Work with carbon credits
description: Learn how to set up and purchase carbon credit.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, ESG, emission, GHG, CSRD, carbon, credit, CO2
ms.search.form: 
ms.date: 08/20/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: solsen
---

# Work with carbon credit  

When companies can't reduce their emissions for various reasons, they can purchase carbon credits to offset their emissions. By buying carbon credits, a company can still emit the equivalent amount of gases while remaining carbon neutral. These credits are purchased from specialized providers, incentivizing emission reductions.  

In general, carbon credits are permits that allow the owner to emit a certain amount of carbon dioxide (CO₂) or other greenhouse gases (GHGs). One carbon credit typically represents the right to emit one metric ton of CO₂ or an equivalent amount of another GHG, so it's important to enable this option for some organizations.  

## Set up the carbon credit  

Carbon Credit in [!INCLUDE[prod_short](includes/prod_short.md)] can be set as the **Item**. To set up the **Item** as a carbon credit, follow the steps:
  
1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then select the related link. 
2. [Create new item as explained](inventory-how-register-new-items.md).   
3. Once the item is created, select the **GHG Credit** field on the **Sustainability** FastTab and add the value of carbon credit using the **Carbon Credit Per UOM** field.

> [!NOTE]
> **Carbon Credit Per UOM** represents the amount of CO₂ in the unit of measure configured in the **Emission Unit of Measure Code** in the **Sustainability Setup**. So, this means the total value of carbon credit as the amount of credited CO₂ per one **Base Unit of Measure** of used item.  

> [!NOTE]
> You can set up any type of item, whether it's inventory, service, or non-inventory, as a carbon credit.  

## To purchase carbon credit 

### Purchase documents 

To work with any purchase-related documents, follow the steps:

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon and:  
   1. Enter **Purchase Invoices** if you want invoice as a **Document Type**, and then select the related link.  
   2. Enter **Purchase Orders** if you want order as a **Document Type**, and then select the related link.   
2. Populate document header based on the following instruction [how to work with purchase invoices and orders](purchasing-how-record-purchases.md). 
3. Choose the item configure as a carbon credit in the **No.** field in the purchase document lines, and add appropriate **Quantity** and **Direct Unit Cost**. 
4. Add the **Sustainability Account No.** you would use for decreasing your carbon dioxide (CO₂) value. System will automatically populate the value in the **Emission CO2** field based on the value you have configured in the **Carbon Credit Per UOM** field on the **Item** card.
5. Post the document.

> [!NOTE]
> Although carbon credit will decrease the value of entries, you'll see a positive amount of value in the **Emission CO2**. But once you post the document, you'll see a value with a negative sign in the **Sustainability Ledger Entry** with the **GHG Credit** as a **Document Type**.  

### Sustainability journals 

To work with **Sustainability Journal** follow the steps:  

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Journal**, and then select the related link. 
2. On the **Sustainability Journal** page, enter as many lines as you intend to post in the same batch.  
3. Choose the **GHG Credit** in the **Document Type** field.    
4. In the **Account No.** field, you can select only non-blocked sustainability accounts where the **Direct Posting** field is selected and the **Accounting Type** field is set to **Posting**. The accounts must also be configured with a category and a subcategory. Choose the appropriate account to post carbon credits.
5. Select **Manual Input** and enter the value you want to post as a carbon credit to the **Emission CO2** field.  
6. Post the journal.   

## See also

[Finance](finance.md)    
[Record sustainability entries](finance-sustainability-journal.md)    
[Sustainability management overview](finance-manage-sustainability.md)    
[Sustainability Setup](finance-sustainability-setup.md)   
[Chart of Sustainability Accounts and Ledger](finance-sustainability-accounts-ledger.md)  
[Ad-hoc analysis of sustainability data](ad-hoc-analysis-sustainability.md)    
[Sustainability reports and analytics in [!INCLUDE[prod_short](includes/prod_short.md)]](sustainability-reports.md)   
[Sustainability API](/dynamics365/business-central/dev-itpro/api-sustainability/sustainability-api?toc=/dynamics365/business-central/toc.json)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    

[!INCLUDE[footer-include](includes/footer-banner.md)]
