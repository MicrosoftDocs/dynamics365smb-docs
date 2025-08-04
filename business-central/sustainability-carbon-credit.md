---
title: Work with carbon credits
description: Learn how to set up and purchase carbon credit.
author: altotovi
ms.topic: how-to
ms.devlang: al
ms.search.keywords: Sustainability, ESG, emission, GHG, CSRD, carbon, credit, CO2
ms.search.form: 
ms.date: 08/20/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: solsen
---

# Work with carbon credits  

When you can't reduce your emissions for some reason, you can purchase carbon credits to offset them. By buying carbon credits, you can still emit the equivalent amount of gases but remain carbon neutral. You can purchase carbon credits from specialized providers.  

In general, carbon credits are permits that allow the owner to emit a certain amount of carbon dioxide (CO₂) or other greenhouse gases (GHGs). One carbon credit typically represents the right to emit one metric ton of CO₂ or an equivalent amount of another GHG, so it's important for some organizations to enable this option.  

## Set up carbon credits

You set up carbon credits in [!INCLUDE[prod_short](includes/prod_short.md)] as items. A credit can be an inventory, service, or non-inventory type of item.

To set up an item as a carbon credit, follow these steps:
  
1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then select the related link.
2. Create a new item. To learn more about how to create an item, go to [Register new items](inventory-how-register-new-items.md).
3. On the **Sustainability** FastTab, turn on the **GHG Credit** toggle.
4. In the **Carbon Credit Per UOM** field, enter the value of the carbon credit.

> [!NOTE]
> The **Carbon Credit Per UOM** field represents the amount of CO₂ in the unit of measure configured in the **Emission Unit of Measure Code** field on the **Sustainability Setup** page. The total value of carbon credit is the amount of credited CO₂ per one **Base Unit of Measure** of the item.

## Purchase carbon credits

### Purchase documents

To work with any purchase-related documents, follow the steps:

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon and:  
   1. Enter **Purchase Invoices** if you want invoice as a **Document Type**, and then select the related link.  
   2. Enter **Purchase Orders** if you want order as a **Document Type**, and then select the related link.
2. Fill in the fields on the **General** FastTab. To learn more, go to [How to work with purchase invoices and orders](purchasing-how-record-purchases.md).
3. On the **Lines** FastTab, choose the item configured as a carbon credit in the **No.** field on a line. Then fill in the **Quantity** and **Direct Unit Cost** fields.
4. In the **Sustainability Account No.** field, choose the account to use for decreasing your carbon dioxide (CO₂) value. [!INCLUDE [prod_short](includes/prod_short.md)] automatically fills in the **Emission CO2** field based on the value you configured in the **Carbon Credit Per UOM** field on the **Item** card.
5. Post the document.

> [!NOTE]
> Although carbon credits decrease the value of entries, the **Emission CO2** field shows a positive amount. After you post the document, on the **Sustainability Ledger Entry** page, the entries have negative values and the **Document Type** field shows **GHG Credit**.  

### Sustainability journals

To work with sustainability journals, follow these steps:  

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Journal**, and then select the related link.
2. On the **Sustainability Journal** page, enter as many lines as you intend to post in the same batch.  
3. In the **Document Type** field, choose **GHG Credit**.
4. In the **Account No.** field, you can select only nonblocked sustainability accounts where the **Direct Posting** field is selected and the **Accounting Type** field is set to **Posting**. The accounts must also be configured with a category and a subcategory. Choose the account to which you post carbon credits.
5. Select the **Manual Input** checkbox, and then enter the value you want to post as a carbon credit to the **Emission CO2** field.  
6. Post the journal.

## Related information

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
