---
title: How to Make Manual Corrections to VAT [BE]
description: You can make corrections to posted VAT entries without posting the correction into the VAT or general ledger entries. 
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: VAT correction, VAT manual correction, Belgian version
ms.date: 04/02/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Make manual corrections to VAT in the Belgian version

You can make corrections to posted VAT entries without posting the correction into the VAT or general ledger entries. This is useful if you need to make a change to the total sales or purchases VAT amounts without changing the VAT base. For example, you can manually correct VAT if you receive an invoice from a vendor who has calculated VAT incorrectly.  

## Make manual corrections to VAT  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Statement Preview**, and then choose the related link.  
1. Select the line that needs to be corrected. You can make the VAT correction on both the **Row Totaling** and **VAT Entry Totaling** row **Type**.  
1. To make the correction, choose the **Correction Amount** field. The **Manual VAT Correction List** page opens.  
1. Choose the **Edit List** action. On the **Manual VAT Correction List** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Posting Date**|Enter the posting date of the VAT correction.|  
    |**Amount**|Enter the amount of the VAT correction. You must enter the correction amount, not the new amount. For example, if the amount is 1,000.00 and should be 1,200.00, enter 200.00.|  
    |**Additional-Currency Amount**|This field displays the amount of the VAT correction in the additional reporting currency.<br><br/> The field is automatically calculated, based on the contents of the **Amount** field and the current exchange rate.|  

1. Choose the **OK** button.  
1. Refresh the **VAT Statement Preview** page to see your corrections.  
1. To view a report related to the preview of the VAT information, choose one of the following actions:  

    |Action|Description|  
    |------------|---------------------------------------|  
    |**Detailed Report**|Opens the **VAT Statement** report. Learn more in VAT Statement.|  
    |**Form/Intervat Declaration**|Opens the **VAT – Form** report.<br><br/> The **Form/Intervat Declaration** report is based on the VAT Statement template that is defined in the general ledger setup. Therefore, it might export data that isn't the same as what is shown on the **VAT Statement Preview** page.|  
    |**Declaration Summary Report**|Opens the **VAT Statement Summary** report.|  

## Related information

- [Belgian VAT](belgian-vat.md)
- [Print Periodic VAT Reports](how-to-print-periodic-vat-reports.md)
- [Set Up Non-Deductible VAT](how-to-set-up-non-deductible-vat.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
